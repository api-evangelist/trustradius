# TrustRadius

TrustRadius is a B2B buyer intelligence and software review platform that helps technology buyers make confident purchasing decisions and enables vendors to turn verified customer reviews into demand generation. Founded in 2012 in Austin, Texas, TrustRadius hosts in-depth verified reviews averaging 400+ words across thousands of B2B software products.

The platform provides downstream intent data showing which accounts are actively researching products, and integrates with Salesforce, HubSpot, 6sense, Demandbase, LinkedIn, Marketo, and Snowflake.

**API Documentation:** [apidocs.trustradius.com](https://apidocs.trustradius.com/)
**Vendor Portal:** [solutions.trustradius.com](https://solutions.trustradius.com/)

---

## APIs

### TrustRadius Public API
Programmatic access to product profiles, TrustRadius scores, categories, and aggregate ratings.
- [Documentation](https://apidocs.trustradius.com/)
- [OpenAPI Spec](openapi/trustradius-public-openapi.yml)

### TrustRadius Reviews API
Verified B2B software reviews with detailed content, multi-dimensional ratings, and reviewer information.
- [Documentation](https://apidocs.trustradius.com/)
- [OpenAPI Spec](openapi/trustradius-reviews-openapi.yml)

### TrustRadius Downstream Intent Data API
Buyer intent signals identifying accounts researching your products, competitors, and categories.
- [Documentation](https://solutions.trustradius.com/intent-data/)

### TrustRadius Content Syndication API (TrustQuotes)
Licensed review excerpts and quotes for marketing channels and sales collateral.
- [Documentation](https://solutions.trustradius.com/products/)

---

## Artifacts

### OpenAPI Specifications
| Spec | Description |
|---|---|
| [trustradius-public-openapi.yml](openapi/trustradius-public-openapi.yml) | Products, categories, and ratings API |
| [trustradius-reviews-openapi.yml](openapi/trustradius-reviews-openapi.yml) | Verified reviews API |

### Spectral Rules
| File | Description |
|---|---|
| [trustradius-rules.yml](rules/trustradius-rules.yml) | Spectral ruleset for TrustRadius API conventions |

### Naftiko Capabilities

#### Shared Definitions
| File | API |
|---|---|
| [shared/products.yaml](capabilities/shared/products.yaml) | Products and Categories API |
| [shared/reviews.yaml](capabilities/shared/reviews.yaml) | Reviews API |

#### Workflow Capabilities
| File | Description | APIs |
|---|---|---|
| [buyer-intelligence.yaml](capabilities/buyer-intelligence.yaml) | B2B software research and competitive analysis | Products + Reviews |

### JSON Schema
| File | Description |
|---|---|
| [trustradius-review-schema.json](json-schema/trustradius-review-schema.json) | TrustRadius review object schema |
| [trustradius-product-schema.json](json-schema/trustradius-product-schema.json) | Software product profile schema |

### JSON Structure
| File | Description |
|---|---|
| [trustradius-review-structure.json](json-structure/trustradius-review-structure.json) | Review field structure documentation |

### JSON-LD Context
| File | Description |
|---|---|
| [trustradius-context.jsonld](json-ld/trustradius-context.jsonld) | JSON-LD context mapping TrustRadius vocabulary to schema.org |

### Examples
| File | Description |
|---|---|
| [trustradius-list-products-example.json](examples/trustradius-list-products-example.json) | List products by category |
| [trustradius-get-product-reviews-example.json](examples/trustradius-get-product-reviews-example.json) | Get product reviews with filters |

### Vocabulary
| File | Description |
|---|---|
| [trustradius-vocabulary.yml](vocabulary/trustradius-vocabulary.yml) | Domain vocabulary for TrustRadius buyer intelligence platform |

---

## Authentication

TrustRadius APIs use API key authentication:
- Obtain your API key from TrustRadius Vendor Portal > Integrations > Get API Key
- Pass the key as the `X-API-Key` HTTP header

[API Key Access Guide](https://trustradius.freshdesk.com/support/solutions/articles/43000639047)

---

## Integrations

TrustRadius integrates with:
- **CRM**: Salesforce, HubSpot
- **ABM**: 6sense, Demandbase, LinkedIn Matched Audiences
- **Marketing Automation**: Marketo
- **Data Warehouse**: Snowflake

[View All Integrations](https://solutions.trustradius.com/integrations/)

---

## Links

- [Website](https://www.trustradius.com/)
- [Vendor Portal](https://solutions.trustradius.com/)
- [API Documentation](https://apidocs.trustradius.com/)
- [Terms of Use](https://www.trustradius.com/legal/terms-of-use)
- [Privacy Policy](https://www.trustradius.com/legal/privacy-policy)
- [GitHub](https://github.com/trustradius)
- [LinkedIn](https://www.linkedin.com/company/trustradius)
- [X (Twitter)](https://twitter.com/TrustRadius)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
