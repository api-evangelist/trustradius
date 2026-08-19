---
name: trustradius-resolve-product-ids
description: Resolve TrustRadius product and vendor identifiers from product slugs before calling any other TrustRadius endpoint. Every other TrustRadius skill depends on this one.
api: TrustRadius Public API
base_url: https://api.trustradius.com/v1
operations:
  - product_ids_get
generated: '2026-08-14'
method: generated
source: openapi/_original/trustradius-api-openapi.yml, https://apidocs.trustradius.com/docs/public-api/ZG9jOjMzODE1NA-faq
---

# Resolve TrustRadius product and vendor ids

## When to use this

Always first. No other TrustRadius operation accepts a product name or slug — they all take the
opaque `_id`. If you do not have an id, you cannot call anything else.

## Preconditions

- An API key from Vendor Portal > Integrations > "Get API key", or from your TrustRadius Client
  Success Manager. Send it in the lowercase header `x-api-key`.
- The product slug, which is the string TrustRadius uses in its own product URLs
  (`https://www.trustradius.com/products/<slug>/reviews`).

## Steps

1. **Resolve a known product.** Call `product_ids_get`:

   ```
   GET /product-ids?products=<slug>
   x-api-key: YOUR_KEY
   ```

   Multiple slugs go in one comma-separated `products` value: `products=slug-a,slug-b,slug-c`.

2. **Or enumerate your own catalog.** Call `product_ids_get` with no parameters. As a vendor this
   returns every published product under your vendor profile — use this when you do not know the
   slugs, or to build a cache.

3. **Read the response.** It is a bare JSON array. Each element carries:
   - `_id` — the product id every other endpoint wants.
   - `vendor._id` and `vendor.name` — your vendor id.
   - `slug` — echoed back so you can map ids to the slugs you asked for.
   - `isVisitorInsightsEnabled` — tells you whether the Legacy visitor-insights endpoints will
     return anything for this product. Check it before calling `visitor_insights_report` or
     `visitor_insights_report_pages_get`.

4. **Cache the mapping.** Ids are stable and the endpoint costs a request against a 10 req/s budget.
   Resolve once per run, not per downstream call.

## Conventions that apply

- Add `?format=csv` if you want CSV instead of JSON. The `Accept` header is ignored by this API.
- All requests are GET, so retries are safe.

## Failure handling

- **403 `{"message":"Forbidden"}`** — the `x-api-key` header is missing or the key is invalid. The
  header name is lowercase; check for a proxy that is normalizing or stripping it.
- **404** — the slug does not exist or is not published under your vendor profile. Confirm the slug
  against the product's TrustRadius URL.
- **400** — a malformed parameter. The only parameters here are `products` and `format`.
- There is no `429` documented and no `RateLimit-*` response header. Budget 10 requests/second
  yourself; if calls start failing under load, back off on your own clock.
