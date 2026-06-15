# TrustRadius (trustradius)

TrustRadius is a B2B buyer intelligence and software review platform that helps technology buyers make confident purchasing decisions and enables vendors to turn verified customer reviews into demand generation. Founded in 2012 and headquartered in Austin, Texas, TrustRadius hosts in-depth verified reviews averaging 400+ words, and provides vendors with downstream intent data showing who is actively researching their products, competitors, and categories. The platform offers REST APIs for accessing product review data, buyer intent signals, and content licensing capabilities, with integrations into Salesforce, HubSpot, 6sense, Demandbase, LinkedIn, Marketo, and Snowflake. Authentication uses API key access from the TrustRadius Vendor Portal.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Access:** 3rd-Party

## Tags

- B2B Software Reviews
- Buyer Intelligence
- Intent Data
- Software Reviews
- Reviews
- Product Reviews
- Categories

## Timestamps

- **Created:** 2026-05-03
- **Modified:** 2026-05-19

## APIs

### TrustRadius Public API

The TrustRadius Public API provides programmatic access to product data, verified user reviews, TrustRadius scores (trScores), software categories, and aggregate rating information. Vendors can retrieve their product profile, reviews written by customers, category information, and competitive comparison data. Authentication uses an API key obtained from the TrustRadius Vendor Portal Integrations section. The API is a REST-based service returning JSON responses.

- **Human URL:** [https://apidocs.trustradius.com/](https://apidocs.trustradius.com/)
- **Base URL:** `https://api.trustradius.com/v1`

#### Tags

- B2B Software Reviews
- Product Reviews
- Reviews
- Software Categories

#### Properties

- [Documentation](https://apidocs.trustradius.com/)
- [Documentation](https://apidocs.trustradius.com/docs/public-api/ZG9jOjQ1Mg-trust-radius-api)
- [Authentication](https://trustradius.freshdesk.com/support/solutions/articles/43000639047)
- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/openapi/trustradius-public-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/trustradius-public.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/trustradius-public.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### TrustRadius Downstream Intent Data API

The TrustRadius Downstream Intent Data API delivers buyer and deal intelligence, revealing which accounts are actively researching a vendor's products, competitor products, and software categories on TrustRadius. The API provides account-level intent signals that can be integrated with Salesforce, HubSpot, 6sense, Demandbase, Marketo, LinkedIn Matched Audiences, and Snowflake for account-based marketing and sales acceleration workflows.

- **Human URL:** [https://solutions.trustradius.com/intent-data/](https://solutions.trustradius.com/intent-data/)
- **Base URL:** `https://api.trustradius.com/v1`

#### Tags

- Intent Data
- Buyer Intelligence
- B2B
- ABM

#### Properties

- [Documentation](https://solutions.trustradius.com/intent-data/)
- [Documentation](https://solutions.trustradius.com/integrations/)
- [Documentation](https://apidocs.trustradius.com/)
- [Postman Collection](collections/trustradius-public.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/trustradius-public.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### TrustRadius Reviews API

The TrustRadius Reviews API provides access to verified user reviews for software products, including detailed review content (400+ words), ratings across multiple dimensions (usability, support, likelihood to recommend), reviewer information, and pros/cons data. Vendors can retrieve reviews for their own products and export review content for content licensing and syndication programs.

- **Human URL:** [https://apidocs.trustradius.com/](https://apidocs.trustradius.com/)
- **Base URL:** `https://api.trustradius.com/v1`

#### Tags

- Reviews
- B2B Software Reviews
- Product Reviews

#### Properties

- [Documentation](https://apidocs.trustradius.com/)
- [Authentication](https://trustradius.freshdesk.com/support/solutions/articles/43000639047)
- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/openapi/trustradius-reviews-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/trustradius-public.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/trustradius-public.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### TrustRadius Content Syndication API

The TrustRadius Content Syndication API (TrustQuotes) enables vendors to extract and embed customer review quotes across marketing channels. Businesses can retrieve licensed review excerpts, quotes, and ratings for use in digital advertising, landing pages, email campaigns, and sales collateral. Supports the Integrated Content Syndication Network for broad review distribution.

- **Human URL:** [https://solutions.trustradius.com/products/](https://solutions.trustradius.com/products/)
- **Base URL:** `https://api.trustradius.com/v1`

#### Tags

- Content Licensing
- Reviews
- Marketing
- B2B

#### Properties

- [Documentation](https://solutions.trustradius.com/products/)
- [Documentation](https://apidocs.trustradius.com/)
- [Postman Collection](collections/trustradius-public.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/trustradius-public.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Website](https://www.trustradius.com/)
- [Portal](https://solutions.trustradius.com/)
- [Documentation](https://apidocs.trustradius.com/)
- [Authentication](https://trustradius.freshdesk.com/support/solutions/articles/43000639047)
- [Integrations](https://solutions.trustradius.com/integrations/)
- [Products](https://solutions.trustradius.com/products/)
- [Terms of Service](https://www.trustradius.com/legal/terms-of-use)
- [Privacy Policy](https://www.trustradius.com/legal/privacy-policy)
- [LinkedIn](https://www.linkedin.com/company/trustradius)
- [X (Twitter)](https://twitter.com/TrustRadius)
- [Git Hub](https://github.com/trustradius)
- [Spectral Rules](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/rules/trustradius-rules.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
