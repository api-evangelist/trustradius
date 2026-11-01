# TrustRadius

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
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

**Areas:** B2B Software Reviews · Buyer Intelligence · Intent Data · Software Reviews · Reviews · Product Reviews · Content Syndication · Account Based Marketing · Marketing · Analytics

## TrustRadius on APIs.io

Everything profiled for TrustRadius is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/trustradius/](https://apis.io/providers/trustradius/)** — or go straight to one of the APIs or properties below.

### APIs (5)

- [TrustRadius Product Data API](https://apis.io/apis/trustradius/trustradius-product-data-api/) — Product identity and scoring. GET /product-ids exchanges a TrustRadius product slug for the opaque product `_id` and owning `vendor._id` that every other…
- [TrustRadius Downstream Intent Data API](https://apis.io/apis/trustradius/trustradius-intent-data-api/) — Downstream intent activity — which accounts are researching a vendor's products, competitor products, and software categories on TrustRadius. GET /intent…
- [TrustRadius TrustQuotes Content Syndication API](https://apis.io/apis/trustradius/trustradius-trustquotes-api/) — Licensed review-quote syndication. GET /trustquotes returns review excerpts with the quote text, a link and rating for the source review, reviewer identity…
- [TrustRadius Traffic Data API](https://apis.io/apis/trustradius/trustradius-traffic-data-api/) — Profile traffic reporting. GET /reports/traffic/products returns page views, visits and visitors per product per day alongside the matching category-level…
- [TrustRadius Legacy Visitor Insights API](https://apis.io/apis/trustradius/trustradius-legacy-visitor-insights-api/) — Identified-company reporting, tagged `Legacy` by TrustRadius in its own specification. GET /reports/visitor-insights/companies returns firmographics (name,…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [trustradius-mcp.yml](https://apis.io/servers/trustradius/trustradius-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Trustradius Agentic Access](https://apis.io/agentic-access/trustradius/trustradius-agentic-access/)

#### JSON Schema (17)

The data models the API reads and writes.

- [Account](https://apis.io/schemas/trustradius/trustradius-Account/)
- [AccountActivity](https://apis.io/schemas/trustradius/trustradius-AccountActivity/)
- [AccountDetail](https://apis.io/schemas/trustradius/trustradius-AccountDetail/)
- [Activity](https://apis.io/schemas/trustradius/trustradius-Activity/)
- [IntentRegistration](https://apis.io/schemas/trustradius/trustradius-IntentRegistration/)
- [NameValuePair](https://apis.io/schemas/trustradius/trustradius-NameValuePair/)
- [TrustRadius ProductScores](https://apis.io/schemas/trustradius/trustradius-ProductScores/)
- [Tags](https://apis.io/schemas/trustradius/trustradius-Tags/)
- [Traffic Page](https://apis.io/schemas/trustradius/trustradius-TrafficPage/)
- [Traffic Product](https://apis.io/schemas/trustradius/trustradius-TrafficProduct/)
- [Trust Quotes](https://apis.io/schemas/trustradius/trustradius-TrustQuotes/)
- [Visit](https://apis.io/schemas/trustradius/trustradius-Visit/)
- [VisitDetail](https://apis.io/schemas/trustradius/trustradius-VisitDetail/)
- [Visitor](https://apis.io/schemas/trustradius/trustradius-Visitor/)
- [VisitorDetail](https://apis.io/schemas/trustradius/trustradius-VisitorDetail/)
- [Visitor Insights Company](https://apis.io/schemas/trustradius/trustradius-VisitorInsightsCompany/)
- [Visitor Insights Pages](https://apis.io/schemas/trustradius/trustradius-VisitorInsightsPages/)

#### JSON Structure (2)

Data models expressed in JSON Structure.

- [Trustradius Product Scores Structure](https://apis.io/json-structure/trustradius/trustradius-product-scores-structure/)
- [Trustradius Trustquote Structure](https://apis.io/json-structure/trustradius/trustradius-trustquote-structure/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Trustradius Context](https://apis.io/jsonld/trustradius/trustradius-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [TrustRadius Vocabulary](https://apis.io/vocabularies/trustradius/trustradius-vocabulary/)

#### Examples (11)

Example requests and responses.

- [Trustradius Account Details Example](https://apis.io/examples/trustradius/trustradius-account-details-example/)
- [Trustradius Get Traffic Page Types Example](https://apis.io/examples/trustradius/trustradius-get-traffic-page-types-example/)
- [Trustradius Get Traffic Products Example](https://apis.io/examples/trustradius/trustradius-get-traffic-products-example/)
- [Trustradius Intent Data Example](https://apis.io/examples/trustradius/trustradius-intent-data-example/)
- [Trustradius Product Ids Get Example](https://apis.io/examples/trustradius/trustradius-product-ids-get-example/)
- [Trustradius Product Scores Example](https://apis.io/examples/trustradius/trustradius-product-scores-example/)
- [Trustradius Tags Get Example](https://apis.io/examples/trustradius/trustradius-tags-get-example/)
- [Trustradius Tqw Pages Get Example](https://apis.io/examples/trustradius/trustradius-tqw-pages-get-example/)
- [Trustradius Trustquotes Get Example](https://apis.io/examples/trustradius/trustradius-trustquotes-get-example/)
- [Trustradius Visitor Insights Report Example](https://apis.io/examples/trustradius/trustradius-visitor-insights-report-example/)
- [Trustradius Visitor Insights Report Pages Get Example](https://apis.io/examples/trustradius/trustradius-visitor-insights-report-pages-get-example/)

#### Overlays (5)

OpenAPI overlays, including conversational phrasing for each operation.

- [Trustradius Intent Data Overlay](https://apis.io/overlays/trustradius/trustradius-intent-data-overlay/)
- [Trustradius Legacy Overlay](https://apis.io/overlays/trustradius/trustradius-legacy-overlay/)
- [Trustradius Product Data Overlay](https://apis.io/overlays/trustradius/trustradius-product-data-overlay/)
- [Trustradius Traffic Data Overlay](https://apis.io/overlays/trustradius/trustradius-traffic-data-overlay/)
- [Trustradius Trustquotes Overlay](https://apis.io/overlays/trustradius/trustradius-trustquotes-overlay/)

#### Governance rules (2)

Spectral rulesets for the provider's contracts.

- [TrustRadius — jsonschema rules](https://apis.io/rules/trustradius/trustradius-jsonschema-spectral-rules/)
- [TrustRadius API Rules](https://apis.io/rules/trustradius/trustradius-rules/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Trustradius Authentication](https://apis.io/security/trustradius/trustradius-authentication/)
- [Trustradius Domain Security](https://apis.io/security/trustradius/trustradius-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Trustradius Plans Pricing](https://apis.io/plans/trustradius/trustradius-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Trustradius Rate Limits](https://apis.io/rate-limits/trustradius/trustradius-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Trustradius Finops](https://apis.io/finops/trustradius/trustradius-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.trustradius.com/)
- [Documentation](https://apidocs.trustradius.com/)
- [Getting started](https://apidocs.trustradius.com/docs/public-api/ZG9jOjQ1Mg-trust-radius-api)
- [API reference](https://apidocs.trustradius.com/docs/public-api/YXBpOjUxMzgzNjA-trust-radius-api)
- [Pricing](https://solutions.trustradius.com/pricing/)
- [Sign up](https://solutions.trustradius.com/claim-your-profile/)
- [Support](https://trustradius.freshdesk.com/support/solutions)
- [Blog](https://solutions.trustradius.com/feed/)
- [Terms of service](https://www.trustradius.com/legal/terms-of-use)
- [Privacy policy](https://www.trustradius.com/legal/privacy-policy)
- [GitHub](https://github.com/trustradius)

## API Evangelist rating

**Kin Score 56.5** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 66.1 |
| Contract quality | 58.4 |
| Contract governance | 31.8 |
| Operational transparency | 26.3 |
| Developer ergonomics | 67.3 |
| Access clarity | 65.8 |

**Agent readiness 28.9** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | na |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | na |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | documented (partial credit) |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | na |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | distinct |

**Regulatory alignment 24.5** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/trustradius/](https://apis.io/providers/trustradius/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for TrustRadius: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/trustradius/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
