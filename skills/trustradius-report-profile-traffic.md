---
name: trustradius-report-profile-traffic
description: Build product- and page-level traffic reporting for your TrustRadius profiles, and understand when to reach for the Legacy visitor-insights endpoints instead.
api: TrustRadius Public API
base_url: https://api.trustradius.com/v1
operations:
  - product_ids_get
  - get_traffic_products
  - get_traffic_page_types
  - visitor_insights_report
  - visitor_insights_report_pages_get
  - account_details
generated: '2026-08-14'
method: generated
source: openapi/_original/trustradius-api-openapi.yml, https://apidocs.trustradius.com/docs/public-api/ZG9jOjQ1Mg-trust-radius-api
---

# Report on TrustRadius profile traffic

## When to use this

To answer "how much attention is my product getting on TrustRadius, and how does that compare to my
category" — and, where the entitlement exists, "which identified companies were looking".

## Preconditions

- API key in the `x-api-key` header.
- Product ids from `trustradius-resolve-product-ids`. That call also returns
  `isVisitorInsightsEnabled` per product — check it before attempting step 3.

## Steps

1. **Product-level totals.** Call `get_traffic_products`:

   ```
   GET /reports/traffic/products?products=<id1>,<id2>&start-date=2026-07-01&end-date=2026-07-31
   x-api-key: YOUR_KEY
   ```

   Rows are one product per date, with `totalPageViews`, `totalVisits`, `totalVisitors` **and** the
   matching `totalCategoryPageViews`, `totalCategoryVisits`, `totalCategoryVisitors`. The category
   totals are the share-of-category denominator — compute the ratio yourself; the API does not.

2. **Page-level detail.** Call `get_traffic_page_types` for the same window. Rows add `pageType`,
   `pageTitle` and `url`, with `totalPageViews` and `totalVisitors`. Group by `pageType` to see
   whether attention is landing on your product page, comparison pages, or category pages.

3. **Identified companies — Legacy path.** If `isVisitorInsightsEnabled` is true:
   - `visitor_insights_report` (`GET /reports/visitor-insights/companies`) returns firmographics
     (name, category, SIC code, size, city/region/country, website, LinkedIn/Twitter/Facebook) plus
     `visits` per product per date.
   - `visitor_insights_report_pages_get` (`GET /reports/visitor-insights/pages`) adds `pageType`,
     `pageTitle`, `url` and a `visitors` measure.
   - `account_details` (`GET /accounts/{account_id}`) drills into one company.

   **All three carry the provider's `Legacy` tag.** They are not marked `deprecated` in the spec,
   they carry no `Sunset` header, and TrustRadius documents no replacement — but do not make them
   the foundation of a long-lived pipeline without asking your CSM what the path forward is.
   `/intent` is the modern account-signal surface; see `trustradius-pull-downstream-intent`.

4. **Page every report.** `skip`/`limit` with a `sort` for stable ordering; stop on a short page.

## Conventions that apply

- These report endpoints use `start-date` and `end-date` — ISO 8601 **dates**, hyphenated. Only
  `/intent` uses `start_time`/`stop_time` date-times.
- `products=` takes a comma-separated list of ids.
- `?format=csv` gives you a CSV straight into a warehouse load.
- `fields=` trims the wide firmographic rows down to what you actually store.
- 10 requests/second budget; a month of daily rows across many products is a lot of pages.

## Failure handling

- **403 `{"message":"Forbidden"}`** — bad key, or the account lacks the visitor-insights entitlement.
- **404** — a product id not published under your vendor profile, or an unknown `account_id`.
- **400** — a date outside ISO 8601 date format, or `limit`/`skip` below their minimums.
- No 429 and no rate-limit headers exist. Pace the pull yourself.
