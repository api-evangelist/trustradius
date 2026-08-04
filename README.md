# TrustRadius (trustradius)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
