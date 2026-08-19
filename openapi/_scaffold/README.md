# Quarantined scaffold OpenAPIs — NOT published by TrustRadius

**Do not use these files. They describe an API that does not exist.**

The six OpenAPI documents in this directory were written by an API Evangelist scaffold pass
(the 2026-05-04 network sweep and the 2026-07-22 `refine-openapis` split of its output). They
were never harvested from TrustRadius.

On **2026-08-14** the enrichment pipeline recovered the **real, TrustRadius-published** OpenAPI
from the provider's own Stoplight-hosted developer portal at
`https://apidocs.trustradius.com/` — export URL
`https://stoplight.io/api/v1/projects/trustradius/public-api/nodes/reference/api.oas3.yml`
(project `cHJqOjc5NzU2` = `prj:79756`, service node `YXBpOjUxMzgzNjA` = `api:5138360`).
It is saved verbatim at `../\_original/trustradius-api-openapi.yml` and split by tag into the
files in `../`.

The two surfaces do not overlap at all:

| Scaffold (invented) | Real, published |
|---|---|
| `/products`, `/products/{productSlug}`, `/products/{productSlug}/reviews`, `/products/{productSlug}/ratings` | `/product-ids`, `/product-scores` |
| `/categories`, `/categories/{categorySlug}` | *(no category endpoint exists)* |
| `/companies/{companySlug}` | `/accounts/{account_id}` |
| `/reviews`, `/reviews/{reviewId}` | `/trustquotes`, `/tags`, `/reports/syndication/tqw/pages` |
| — | `/intent`, `/reports/traffic/pages`, `/reports/traffic/products`, `/reports/visitor-insights/companies`, `/reports/visitor-insights/pages` |
| security scheme `ApiKey` / `X-API-Key` | security scheme `x-api-key` (lowercase header, per the provider's own docs) |

Not one scaffold path or `operationId` appears in the published contract. Anything derived from
these files — the `collections/`, `examples/`, `json-schema/`, `json-structure/`, `json-ld/`,
`vocabulary/` and `rules/` artifacts dated before 2026-08-14 — inherits the same defect and is
being rebuilt from the real spec.

They are kept rather than deleted so the provenance defect stays auditable. See
`scaffold-fabrication-sweep` and roadmap#35.
