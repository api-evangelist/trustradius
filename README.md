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

TrustRadius is a B2B buyer intelligence and software review platform that helps technology buyers make confident purchasing decisions and enables vendors to turn verified customer reviews into demand generation. Founded in 2012 and headquartered in Austin, Texas, and now part of HG Insights, TrustRadius hosts in-depth verified reviews averaging 400+ words, and provides vendors with downstream intent data showing which accounts are actively researching their products, competitors, and categories. The TrustRadius Public API is a single read-only REST surface at https://api.trustradius.com/v1 with eleven GET operations across five areas — product identity and scores, downstream intent activity, profile traffic reporting, licensed TrustQuotes review excerpts, and a legacy visitor-insights family. Authentication is one opaque API key in the lowercase x-api-key header, issued per vendor account from the Vendor Portal; the published request budget is 10 requests per second. Intent data is designed to be activated in Salesforce, HubSpot, 6sense, Demandbase, LinkedIn, Marketo, and Snowflake.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Access:** 3rd-Party
- **Access model:** Paid vendor package · Sales-led · Public docs with a live mock (confidence: high)

## Provenance of the specifications in this repo

The OpenAPI in `openapi/_original/trustradius-api-openapi.yml` is **published by TrustRadius**. It was
exported on 2026-08-14 from the company's own Stoplight-hosted developer portal at
<https://apidocs.trustradius.com/> — OpenAPI 3.0.0, `info.version` 1.1, 11 operations,
`servers[0]` = `https://api.trustradius.com/v1`. The per-tag files in `openapi/` are splits of it;
the originals are never mutated (our additions live in `overlays/` as OpenAPI Overlay 1.0.0 documents).

`openapi/_scaffold/` holds six **quarantined, fabricated** OpenAPI documents written by an API
Evangelist scaffold pass in May 2026. They describe `/products`, `/categories`, `/companies` and
`/reviews` endpoints that **do not exist**. They are kept, not deleted, so the defect stays auditable —
see `openapi/_scaffold/README.md`. Every artifact that had been derived from them was rebuilt from the
real specification in the same pass.

## Not published by TrustRadius

Recorded absences, each measured rather than assumed:

- **No `/.well-known/` documents** on any host — every path 404s (403 at the API edge). See `well-known/`.
- **No A2A agent card** at either the canonical or the legacy path.
- **No MCP server.** `mcp/trustradius-mcp.yml` is an API Evangelist *candidate* tool set derived from the
  published OpenAPI, marked `deployment.mode: none`, and deliberately **not** wired as an `MCPServer`
  pointer in `apis.yml` — nobody ships a server, so nothing should score as if they did.
- **No client SDK** in any public package registry, and no CLI.
- **No changelog, no status page, no deprecation policy, no published SLA.**
- **No event or webhook surface** — the published OpenAPI declares a `Webhooks` tag with zero operations.
- **No `llms.txt`** — the one in `llms/` is generated by API Evangelist from the published contract.
- **Compliance certifications are unverified**: <https://www.trustradius.com/security> returned HTTP 403
  from a Cloudflare challenge on every attempt, and third-party aggregators are not accepted as evidence.

## Tags

- B2B Software Reviews
- Buyer Intelligence
- Intent Data
- Software Reviews
- Reviews
- Product Reviews
- Content Syndication
- Account Based Marketing
- Marketing
- Analytics

## Timestamps

- **Created:** 2026-05-03
- **Modified:** 2026-08-14

## APIs

### TrustRadius Product Data API

Product identity and scoring. GET /product-ids exchanges a TrustRadius product slug for the opaque product `_id` and owning `vendor._id` that every other TrustRadius operation requires, and called with no parameters returns every published product under the calling vendor's profile. GET /product-scores returns the TrustRadius (TR) Score and star score — each as a {score, max} object — plus review, rating and combined counts. This is the entry point for the whole API.

- **Human URL:** [https://apidocs.trustradius.com/docs/public-api/YXBpOjUxMzgzNjA-trust-radius-api](https://apidocs.trustradius.com/docs/public-api/YXBpOjUxMzgzNjA-trust-radius-api)
- **Base URL:** `https://api.trustradius.com/v1`

#### Tags

- Products
- Ratings
- B2B Software Reviews

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/openapi/trustradius-product-data-api-openapi.yml)
- [Overlay](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/overlays/trustradius-product-data-overlay.yaml)
- [APIReference](https://apidocs.trustradius.com/docs/public-api/YXBpOjUxMzgzNjA-trust-radius-api)
- [Documentation](https://apidocs.trustradius.com/docs/public-api/ZG9jOjQ1Mg-trust-radius-api)
- [Authentication](https://trustradius.freshdesk.com/support/solutions/articles/43000639047)

### TrustRadius Downstream Intent Data API

Downstream intent activity — which accounts are researching a vendor's products, competitor products, and software categories on TrustRadius. GET /intent returns account records with an activity stream whose `type` is a closed enum of click, download, like and view, filtered by ISO 8601 `start_time`/`stop_time`, account domains, and activity names. Designed for activation in Salesforce, HubSpot, 6sense, Demandbase, Marketo, LinkedIn Matched Audiences and Snowflake. Category intent data is a separately quoted add-on to the vendor package.

- **Human URL:** [https://solutions.trustradius.com/products/downstream-intent-data/](https://solutions.trustradius.com/products/downstream-intent-data/)
- **Base URL:** `https://api.trustradius.com/v1`

#### Tags

- Intent Data
- Buyer Intelligence
- B2B
- ABM

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/openapi/trustradius-intent-data-api-openapi.yml)
- [Overlay](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/overlays/trustradius-intent-data-overlay.yaml)
- [AgentSkill](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/skills/trustradius-pull-downstream-intent.md)
- [APIReference](https://apidocs.trustradius.com/docs/public-api/YXBpOjUxMzgzNjA-trust-radius-api)
- [Documentation](https://solutions.trustradius.com/products/downstream-intent-data/)
- [Documentation](https://solutions.trustradius.com/integrations/)
- [Authentication](https://trustradius.freshdesk.com/support/solutions/articles/43000639047)

### TrustRadius TrustQuotes Content Syndication API

Licensed review-quote syndication. GET /trustquotes returns review excerpts with the quote text, a link and rating for the source review, reviewer identity and firmographics, an isAnonymous flag, and the tags applied to the quote; GET /tags returns the tag vocabulary and its groups; GET /reports/syndication/tqw/pages reports how the TrustQuotes for Web widget is performing by page. Requires a Content Licensing entitlement. The self-serve TrustQuotes for Web JavaScript widget is the no-code alternative to this API.

- **Human URL:** [https://solutions.trustradius.com/products/content-licensing/](https://solutions.trustradius.com/products/content-licensing/)
- **Base URL:** `https://api.trustradius.com/v1`

#### Tags

- Content Licensing
- Reviews
- Marketing
- B2B

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/openapi/trustradius-trustquotes-api-openapi.yml)
- [Overlay](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/overlays/trustradius-trustquotes-overlay.yaml)
- [AgentSkill](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/skills/trustradius-syndicate-trustquotes.md)
- [APIReference](https://apidocs.trustradius.com/docs/public-api/YXBpOjUxMzgzNjA-trust-radius-api)
- [Documentation](https://solutions.trustradius.com/products/content-licensing/)
- [Authentication](https://trustradius.freshdesk.com/support/solutions/articles/43000639047)

### TrustRadius Traffic Data API

Profile traffic reporting. GET /reports/traffic/products returns page views, visits and visitors per product per day alongside the matching category-level totals, so share-of-category is computable client-side. GET /reports/traffic/pages breaks the same window down by page type, page title and URL. Both accept ISO 8601 start-date/end-date filters, comma-separated product ids, skip/limit paging, and a format parameter for JSON or CSV.

- **Human URL:** [https://apidocs.trustradius.com/docs/public-api/YXBpOjUxMzgzNjA-trust-radius-api](https://apidocs.trustradius.com/docs/public-api/YXBpOjUxMzgzNjA-trust-radius-api)
- **Base URL:** `https://api.trustradius.com/v1`

#### Tags

- Analytics
- Traffic
- Reporting

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/openapi/trustradius-traffic-data-api-openapi.yml)
- [Overlay](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/overlays/trustradius-traffic-data-overlay.yaml)
- [AgentSkill](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/skills/trustradius-report-profile-traffic.md)
- [APIReference](https://apidocs.trustradius.com/docs/public-api/YXBpOjUxMzgzNjA-trust-radius-api)
- [Documentation](https://apidocs.trustradius.com/docs/public-api/ZG9jOjQ1Mg-trust-radius-api)
- [Authentication](https://trustradius.freshdesk.com/support/solutions/articles/43000639047)

### TrustRadius Legacy Visitor Insights API

Identified-company reporting, tagged `Legacy` by TrustRadius in its own specification. GET /reports/visitor-insights/companies returns firmographics (name, SIC code, size, location, web and social handles) with visit counts; GET /reports/visitor-insights/pages adds page-level detail; GET /accounts/{account_id} drills into one company with its visitors and visits. Enabled per product — check isVisitorInsightsEnabled on the /product-ids response first. None of the three is marked deprecated and no replacement or Sunset date is published, so the Legacy label is a signal a machine cannot act on.

- **Human URL:** [https://apidocs.trustradius.com/docs/public-api/YXBpOjUxMzgzNjA-trust-radius-api](https://apidocs.trustradius.com/docs/public-api/YXBpOjUxMzgzNjA-trust-radius-api)
- **Base URL:** `https://api.trustradius.com/v1`

#### Tags

- Visitor Insights
- Firmographics
- Legacy

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/openapi/trustradius-legacy-api-openapi.yml)
- [Overlay](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/overlays/trustradius-legacy-overlay.yaml)
- [APIReference](https://apidocs.trustradius.com/docs/public-api/YXBpOjUxMzgzNjA-trust-radius-api)
- [Documentation](https://apidocs.trustradius.com/docs/public-api/ZG9jOjQ1Mg-trust-radius-api)
- [Authentication](https://trustradius.freshdesk.com/support/solutions/articles/43000639047)

## Common Properties

- **OpenAPI** — [TrustRadius Public API (provider-published, complete)](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/openapi/_original/trustradius-api-openapi.yml)
- **AgenticAccess** — [AgenticAccess](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/agentic-access/trustradius-agentic-access.yml)
- **DomainSecurity** — [DomainSecurity](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/security/trustradius-domain-security.yml)
- **Authentication** — [Authentication](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/authentication/trustradius-authentication.yml)
- **Conventions** — [Conventions](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/conventions/trustradius-conventions.yml)
- **ErrorCatalog** — [ErrorCatalog](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/errors/trustradius-problem-types.yml)
- **Lifecycle** — [Lifecycle](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/lifecycle/trustradius-lifecycle.yml)
- **Conformance** — [Conformance](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/conformance/trustradius-conformance.yml)
- **DataModel** — [DataModel](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/data-model/trustradius-data-model.yml)
- **Sandbox** — [Live Prism mock provisioned by the TrustRadius developer portal](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/sandbox/trustradius-sandbox.yml)
- **Components** — [Components](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/components/trustradius-components.yml)
- **Packages** — [Packages](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/packages/trustradius-packages.yml)
- **LLMsTxt** — [LLMsTxt](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/llms/trustradius-llms.txt)
- **AgentSkill** — [AgentSkill](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/skills/_index.yml)
- **Vocabulary** — [Vocabulary](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/vocabulary/trustradius-vocabulary.yml)
- **Examples** — [Request/response examples derived from the published OpenAPI (11, one per operation)](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/examples/trustradius-product-ids-get-example.json)
- **JSONSchema** — [JSON Schema extracted from the published OpenAPI components (17 schemas)](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/json-schema/trustradius-TrustQuotes.json)
- **JSONStructure** — [JSONStructure](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/json-structure/trustradius-trustquote-structure.json)
- **JSONLD** — [JSONLD](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/json-ld/trustradius-context.jsonld)
- **PostmanCollection** — [TrustRadius Public API (generated by API Evangelist from the published OpenAPI)](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/collections/trustradius-public-api.postman_collection.json)
- **Plans** — [Plans](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/plans/trustradius-plans-pricing.yml)
- **RateLimits** — [RateLimits](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/rate-limits/trustradius-rate-limits.yml)
- **FinOps** — [FinOps](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/finops/trustradius-finops.yml)
- **SpectralRules** — [Spectral Rules](https://raw.githubusercontent.com/api-evangelist/trustradius/refs/heads/main/rules/trustradius-rules.yml)
- **Website** — [TrustRadius Website](https://www.trustradius.com/)
- **DeveloperPortal** — [TrustRadius API Documentation](https://apidocs.trustradius.com/)
- **Documentation** — [API Documentation](https://apidocs.trustradius.com/)
- **APIReference** — [TrustRadius API Reference](https://apidocs.trustradius.com/docs/public-api/YXBpOjUxMzgzNjA-trust-radius-api)
- **GettingStarted** — [TrustRadius API Overview — base URL, authentication and how to test](https://apidocs.trustradius.com/docs/public-api/ZG9jOjQ1Mg-trust-radius-api)
- **FAQ** — [API FAQ — identifiers, rate limit, multi-id syntax](https://apidocs.trustradius.com/docs/public-api/ZG9jOjMzODE1NA-faq)
- **Authentication** — [Accessing your TrustRadius API key](https://trustradius.freshdesk.com/support/solutions/articles/43000639047)
- **Support** — [TrustRadius Help Center](https://trustradius.freshdesk.com/support/solutions)
- **Portal** — [TrustRadius for Vendors](https://solutions.trustradius.com/)
- **Login** — [TrustRadius Vendor Portal](https://vendor.trustradius.com/)
- **SignUp** — [Claim Your Profile](https://solutions.trustradius.com/claim-your-profile/)
- **Pricing** — [Pricing & Packaging](https://solutions.trustradius.com/pricing/)
- **Integrations** — [Integrations](https://solutions.trustradius.com/integrations/)
- **Products** — [Products](https://solutions.trustradius.com/products/)
- **Contact** — [Contact TrustRadius](https://about.trustradius.com/contact-us)
- **TermsOfService** — [Terms of Use](https://www.trustradius.com/legal/terms-of-use)
- **PrivacyPolicy** — [Privacy Policy](https://www.trustradius.com/legal/privacy-policy)
- **Blog** — [TrustRadius Vendor Blog](https://solutions.trustradius.com/feed/)
- **Resources** — [TrustRadius Resources](https://solutions.trustradius.com/resources-overview)
- **GitHubOrganization** — [TrustRadius on GitHub](https://github.com/trustradius)
- **LinkedIn** — [TrustRadius on LinkedIn](https://www.linkedin.com/company/trustradius)
- **X** — [TrustRadius on X (Twitter)](https://twitter.com/TrustRadius)

## Maintainers

**FN:** Kin Lane  
**Email:** kin@apievangelist.com
