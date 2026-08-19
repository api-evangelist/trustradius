---
name: trustradius-pull-downstream-intent
description: Pull TrustRadius downstream intent activity — which accounts are researching your products, your competitors, and your category — and page through it safely for CRM or ABM activation.
api: TrustRadius Public API
base_url: https://api.trustradius.com/v1
operations:
  - product_ids_get
  - intent_data
generated: '2026-08-14'
method: generated
source: openapi/_original/trustradius-api-openapi.yml, https://apidocs.trustradius.com/docs/public-api/ZG9jOjMzODE1NA-faq
---

# Pull TrustRadius downstream intent data

## When to use this

To sync account-level buying signals into Salesforce, HubSpot, 6sense, Demandbase, Marketo,
LinkedIn Matched Audiences or Snowflake — the activation targets TrustRadius names on its
integrations page.

## Preconditions

- API key in the `x-api-key` header. Intent data is a paid package element; a key that works for
  `product_ids_get` will still 403 or return nothing here if the vendor account is not subscribed.
- Run `trustradius-resolve-product-ids` first if you need product context.

## Steps

1. **Choose an explicit time window.** `intent_data` uses `start_time` and `stop_time`, both ISO
   8601 **date-times**. This is different from the traffic and visitor-insights reports, which use
   `start-date` / `end-date` ISO 8601 **dates**. Do not reuse one family's parameter names on the
   other — they are genuinely different parameters.

2. **Call the endpoint.**

   ```
   GET /intent?start_time=2026-08-01T00:00:00Z&stop_time=2026-08-08T00:00:00Z&limit=500
   x-api-key: YOUR_KEY
   ```

3. **Narrow if you need to.**
   - `accounts=` — comma-separated account **domains**, to restrict to a target list.
   - `intent=` — comma-separated activity names, to restrict to specific signal types.
   - `fields=` — comma-separated field names, to trim the payload.
   - `sort=` — comma-separated fields; prefix with `-` for descending.

4. **Page with `skip` and `limit`.** There is no cursor, no total count and no `Link` header, so:
   - Hold `limit` constant.
   - Increment `skip` by `limit` each call.
   - **Stop when a page returns fewer rows than `limit`.** That short page is the only end-of-data
     signal this API gives you.
   - Always send `sort` when paging. Without an explicit order the page boundaries are not stable
     and you can silently duplicate or drop rows.

5. **Interpret the payload.** Intent records resolve to an account (`name`, `domain`) with an
   `activities` array. Each activity carries `date`, `type`, `label` and `human_readable` — use
   `human_readable` for display and `type` for routing logic. The `objects` array on an activity is
   declared as untyped in the spec; treat it as opaque and do not build rules on its shape.

## Conventions that apply

- `?format=csv` for a CSV pull instead of JSON — useful for the Snowflake path.
- GET only; retries are safe.
- Budget 10 requests/second (600/minute). A large window at `limit=500` is many pages — pace it.

## Failure handling

- **403 `{"message":"Forbidden"}`** — missing/invalid key, or the vendor account has no intent
  entitlement. This is the same body for both causes; the API does not distinguish them.
- **400** — almost always a malformed `start_time`/`stop_time`, or `limit` below 1 / `skip` below 0.
- **404** — an account domain or activity name that TrustRadius does not recognize.
- No `429` is documented and no `Retry-After` is returned. Back off on your own schedule.
- No request-id header exists, so if you need TrustRadius support to trace a failure
  (product@trustradius.com), capture the full request URL and timestamp yourself.
