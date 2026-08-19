---
name: trustradius-syndicate-trustquotes
description: Retrieve licensed TrustRadius review quotes and their tag vocabulary for syndication into vendor-owned channels, and measure how the TrustQuotes for Web widget is performing.
api: TrustRadius Public API
base_url: https://api.trustradius.com/v1
operations:
  - product_ids_get
  - tags_get
  - trustquotes_get
  - tqw_pages_get
generated: '2026-08-14'
method: generated
source: >-
  openapi/_original/trustradius-api-openapi.yml,
  https://trustradius.freshdesk.com/support/solutions/articles/43000676759-trustquotes-for-web-widget-and-trustquotes-api-which-should-i-use-for-syndication-
---

# Syndicate TrustRadius review quotes

## When to use this

To pull licensed customer-review excerpts into your own site, landing pages, email or ad creative
and store them in your own database. Use the **API** path when you need multiple products, your own
rendering, or your own storage. Use the **TrustQuotes for Web widget** instead when you want one
product per placement, automatic styling and automatic star ratings that Google can read — the
provider frames these as a choose-one decision, not a combination.

## Preconditions

- API key in the `x-api-key` header.
- A Content Licensing entitlement. The license to publish review content on your own channels is a
  paid package element; without it there is nothing to syndicate.
- Product ids from `trustradius-resolve-product-ids`.

## Steps

1. **Load the tag vocabulary first.** Call `tags_get`:

   ```
   GET /tags
   x-api-key: YOUR_KEY
   ```

   Each tag has `id`, `name`, `sequence`, plus embedded `vendor`, `products` and `tagGroup` objects.
   The `sequence` field is the vendor's own display order — respect it if you are rendering groups.
   Cache this; it changes far less often than the quotes do.

2. **Pull quotes.** Call `trustquotes_get` with `skip`/`limit` paging, and `sort` for a stable order:

   ```
   GET /trustquotes?limit=200&skip=0&sort=-created
   x-api-key: YOUR_KEY
   ```

3. **Filter and select.** Each quote carries:
   - `text` — the excerpt itself.
   - `created` — when the quote was published; use it to keep placements fresh.
   - `allTags` / `allTagNames` — the tag ids and names to match against step 1, so you can place a
     quote next to the page content it is actually about.
   - `isSummary` — whether this is a summary excerpt rather than a verbatim pull.
   - `isAnonymous` — **honor this.** If true, do not render reviewer identity anywhere.
   - `taggedreviewStatus` — the review's tagging state.
   - `vendor` `{id, name}` and `product` `{id, name}` — who the quote belongs to.
   - `review` `{id, editedDate, publishedDate, heading, url, rating}` — `url` links back to the
     published review on TrustRadius; attribute back to it. `rating` is the review's numeric score.
   - `user` `{id, pictureUrl, name, company{name, size, industry{name}}, position{title, jobType,
     department}}` — reviewer identity and firmographics. Render this **only** when `isAnonymous`
     is false.

4. **Page to the end.** Increment `skip` by `limit`; stop when a page returns fewer than `limit`
   rows. There is no total count and no cursor.

5. **Measure the widget, if you also run one.** Call `tqw_pages_get`:

   ```
   GET /reports/syndication/tqw/pages?start-date=2026-07-01&end-date=2026-07-31
   x-api-key: YOUR_KEY
   ```

   Note the parameter names here are hyphenated **dates** (`start-date`, `end-date`) — not the
   underscored date-times that `/intent` uses.

## Conventions that apply

- `?format=csv` for a bulk CSV export instead of JSON.
- `fields=` to trim large quote payloads.
- All GET; retries are safe. Budget 10 requests/second.

## Failure handling

- **403 `{"message":"Forbidden"}`** — missing/invalid key, or no Content Licensing entitlement.
- **400** — malformed `start-date`/`end-date`, or `limit` < 1 / `skip` < 0.
- **404** — an unknown product id; re-resolve with `product_ids_get`.
- No error body schema is published for 400/404, so do not parse the failure payload — branch on
  the status code alone.

## Compliance note

These are licensed excerpts of real customers' published reviews. Respect `isAnonymous`, do not
edit `text`, and do not syndicate beyond the channels your license covers.
