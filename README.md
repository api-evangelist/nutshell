# Nutshell

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

Nutshell is a CRM and email-marketing platform for small and mid-sized B2B sales teams, combining pipeline management, contact and company records, activity tracking, reporting, sales automation and built-in outbound email campaigns in one workspace with mobile and desktop clients. For developers Nutshell publishes a documented REST API of 112 operations across 24 resource families at app.nutshell.com/rest, an authenticated GraphQL endpoint, a legacy JSON-RPC API kept alive for existing integrations, an outbound webhook firehose, read-only SQL access on the Enterprise plan, and a remote, OAuth-protected MCP server at app.nutshell.com/mcp that exposes read-only CRM context to AI assistants.

**Areas:** CRM · Sales · Pipeline Management · Email Marketing · Contact Management · Sales Automation · Lead Management · Marketing Automation · MCP · B2B

## Nutshell on APIs.io

Everything profiled for Nutshell is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/nutshell/](https://apis.io/providers/nutshell/)** — or go straight to one of the APIs or properties below.

### APIs (26)

- [Nutshell Legacy JSON-RPC API](https://apis.io/apis/nutshell/json-rpc/) — Nutshell's original JSON-RPC API, available since 2010. Nutshell states it is no longer adding new endpoints to this API but continues to support existing…
- [Nutshell GraphQL API](https://apis.io/apis/nutshell/graphql/) — A GraphQL endpoint served at https://app.nutshell.com/graphql. Nutshell's API authentication guide names GraphQL alongside REST and JSON-RPC as an…
- [Nutshell Activities API](https://apis.io/apis/nutshell/nutshell-activities-api/) — Meetings, calls and logged interactions attached to Nutshell records, plus the activity type reference. 5 operation(s) across 3 path(s).
- [Nutshell Audiences API](https://apis.io/apis/nutshell/nutshell-audiences-api/) — Email-marketing audiences — static lists of contacts used to organize people for marketing sends. 2 operation(s) across 1 path(s).
- [Nutshell Competitors API](https://apis.io/apis/nutshell/nutshell-competitors-api/) — Competitor records and the lead-to-competitor relationships (competitor maps) attached to a lead. 6 operation(s) across 4 path(s).
- [Nutshell Editions API](https://apis.io/apis/nutshell/nutshell-editions-api/) — Marketing email editions — individual email sends and their metadata. 2 operation(s) across 2 path(s).
- [Nutshell Emails API](https://apis.io/apis/nutshell/nutshell-emails-api/) — Individual email messages recorded against Nutshell records. 1 operation(s) across 1 path(s).
- [Nutshell Forms API](https://apis.io/apis/nutshell/nutshell-forms-api/) — Nutshell Forms and their fields, including the field IDs used in each published form. 3 operation(s) across 3 path(s).
- [Nutshell Industries API](https://apis.io/apis/nutshell/nutshell-industries-api/) — The industry reference list used to classify accounts. 1 operation(s) across 1 path(s).
- [Nutshell Invoices API](https://apis.io/apis/nutshell/nutshell-invoices-api/) — Invoice documents, their status transitions and payment/completion metadata. 3 operation(s) across 3 path(s).
- [Nutshell Leads API](https://apis.io/apis/nutshell/nutshell-leads-api/) — Sales opportunities: create, read, update, close, reopen, watch, stage and stageset assignment, installments, reports and lead custom fields. 25…
- [Nutshell Markets API](https://apis.io/apis/nutshell/nutshell-markets-api/) — Market records used to segment Nutshell data. 2 operation(s) across 2 path(s).
- [Nutshell Notes API](https://apis.io/apis/nutshell/nutshell-notes-api/) — Free-text notes attached to accounts, contacts and leads, with delete and undelete. 5 operation(s) across 3 path(s).
- [Nutshell Products API](https://apis.io/apis/nutshell/nutshell-products-api/) — The product catalog and product maps — instances of a product attached to a lead with quantity and custom pricing. 8 operation(s) across 6 path(s).
- [Nutshell Quotes API](https://apis.io/apis/nutshell/nutshell-quotes-api/) — Quote documents, their status transitions, and creating an invoice from a quote. 4 operation(s) across 4 path(s).
- [Nutshell Sources API](https://apis.io/apis/nutshell/nutshell-sources-api/) — Lead sources — how leads arrive at your website and learn about your business. 4 operation(s) across 3 path(s).
- [Nutshell Tags API](https://apis.io/apis/nutshell/nutshell-tags-api/) — Tags used to group leads, contacts and accounts, with delete and undelete. 4 operation(s) across 3 path(s).
- [Nutshell Tasks API](https://apis.io/apis/nutshell/nutshell-tasks-api/) — Tasks assigned to Nutshell users, including assignee updates. 5 operation(s) across 2 path(s).
- [Nutshell Territories API](https://apis.io/apis/nutshell/nutshell-territories-api/) — Sales territories used to scope ownership of Nutshell records. 1 operation(s) across 1 path(s).
- [Nutshell Users API](https://apis.io/apis/nutshell/nutshell-users-api/) — Nutshell users in the instance. 2 operation(s) across 2 path(s).
- [Nutshell Accounts (Companies) API](https://apis.io/apis/nutshell/nutshell-accounts-companies-api/) — The Accounts (Companies) API from Nutshell — 10 operation(s) for accounts (companies).
- [Nutshell Contacts (People) API](https://apis.io/apis/nutshell/nutshell-contacts-people-api/) — The Contacts (People) API from Nutshell — 8 operation(s) for contacts (people).
- [Nutshell Events (Timeline) API](https://apis.io/apis/nutshell/nutshell-events-timeline-api/) — The Events (Timeline) API from Nutshell — 2 operation(s) for events (timeline).
- [Nutshell Filter API](https://apis.io/apis/nutshell/nutshell-filter-api/) — The Filter API from Nutshell — 1 operation(s) for filter.
- [Nutshell Stagesets (Pipelines) API](https://apis.io/apis/nutshell/nutshell-stagesets-pipelines-api/) — The Stagesets (Pipelines) API from Nutshell — 3 operation(s) for stagesets (pipelines).
- [Nutshell Product Categories API](https://apis.io/apis/nutshell/nutshell-product-categories-api/) — ProductCategories

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Nutshell Webhooks](https://apis.io/asyncapis/nutshell/nutshell-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Nutshell MCP server](https://apis.io/servers/nutshell/nutshell-mcp-server/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Nutshell Agentic Access](https://apis.io/agentic-access/nutshell/nutshell-agentic-access/)

#### Collections (24)

Postman and Open Collection request collections.

- [Nutshell Accounts (Companies) API](https://apis.io/collections/nutshell/open-nutshell-accounts-api/)
- [Nutshell Activities API](https://apis.io/collections/nutshell/open-nutshell-activities-api/)
- [Nutshell Audiences API](https://apis.io/collections/nutshell/open-nutshell-audiences-api/)
- [Nutshell Competitors API](https://apis.io/collections/nutshell/open-nutshell-competitors-api/)
- [Nutshell Contacts (People) API](https://apis.io/collections/nutshell/open-nutshell-contacts-api/)
- [Nutshell Editions API](https://apis.io/collections/nutshell/open-nutshell-editions-api/)
- [Nutshell Emails API](https://apis.io/collections/nutshell/open-nutshell-emails-api/)
- [Nutshell Events (Timeline) API](https://apis.io/collections/nutshell/open-nutshell-events-api/)
- [Nutshell Filter API](https://apis.io/collections/nutshell/open-nutshell-filters-api/)
- [Nutshell Forms API](https://apis.io/collections/nutshell/open-nutshell-forms-api/)
- [Nutshell Industries API](https://apis.io/collections/nutshell/open-nutshell-industries-api/)
- [Nutshell Invoices API](https://apis.io/collections/nutshell/open-nutshell-invoices-api/)
- [Nutshell Leads API](https://apis.io/collections/nutshell/open-nutshell-leads-api/)
- [Nutshell Markets API](https://apis.io/collections/nutshell/open-nutshell-markets-api/)
- [Nutshell Notes API](https://apis.io/collections/nutshell/open-nutshell-notes-api/)
- [Nutshell Stagesets (Pipelines) API](https://apis.io/collections/nutshell/open-nutshell-pipelines-api/)
- [Nutshell ProductCategories API](https://apis.io/collections/nutshell/open-nutshell-product-categories-api/)
- [Nutshell Products API](https://apis.io/collections/nutshell/open-nutshell-products-api/)
- [Nutshell Quotes API](https://apis.io/collections/nutshell/open-nutshell-quotes-api/)
- [Nutshell Sources API](https://apis.io/collections/nutshell/open-nutshell-sources-api/)
- [Nutshell Tags API](https://apis.io/collections/nutshell/open-nutshell-tags-api/)
- [Nutshell Tasks API](https://apis.io/collections/nutshell/open-nutshell-tasks-api/)
- [Nutshell Territories API](https://apis.io/collections/nutshell/open-nutshell-territories-api/)
- [Nutshell Users API](https://apis.io/collections/nutshell/open-nutshell-users-api/)

#### Overlays (24)

OpenAPI overlays, including conversational phrasing for each operation.

- [Nutshell Accounts Overlay](https://apis.io/overlays/nutshell/nutshell-accounts-overlay/)
- [Nutshell Activities Overlay](https://apis.io/overlays/nutshell/nutshell-activities-overlay/)
- [Nutshell Audiences Overlay](https://apis.io/overlays/nutshell/nutshell-audiences-overlay/)
- [Nutshell Competitors Overlay](https://apis.io/overlays/nutshell/nutshell-competitors-overlay/)
- [Nutshell Contacts Overlay](https://apis.io/overlays/nutshell/nutshell-contacts-overlay/)
- [Nutshell Editions Overlay](https://apis.io/overlays/nutshell/nutshell-editions-overlay/)
- [Nutshell Emails Overlay](https://apis.io/overlays/nutshell/nutshell-emails-overlay/)
- [Nutshell Events Overlay](https://apis.io/overlays/nutshell/nutshell-events-overlay/)
- [Nutshell Filters Overlay](https://apis.io/overlays/nutshell/nutshell-filters-overlay/)
- [Nutshell Forms Overlay](https://apis.io/overlays/nutshell/nutshell-forms-overlay/)
- [Nutshell Industries Overlay](https://apis.io/overlays/nutshell/nutshell-industries-overlay/)
- [Nutshell Invoices Overlay](https://apis.io/overlays/nutshell/nutshell-invoices-overlay/)
- [Nutshell Leads Overlay](https://apis.io/overlays/nutshell/nutshell-leads-overlay/)
- [Nutshell Markets Overlay](https://apis.io/overlays/nutshell/nutshell-markets-overlay/)
- [Nutshell Notes Overlay](https://apis.io/overlays/nutshell/nutshell-notes-overlay/)
- [Nutshell Pipelines Overlay](https://apis.io/overlays/nutshell/nutshell-pipelines-overlay/)
- [Nutshell Product Categories Overlay](https://apis.io/overlays/nutshell/nutshell-product-categories-overlay/)
- [Nutshell Products Overlay](https://apis.io/overlays/nutshell/nutshell-products-overlay/)
- [Nutshell Quotes Overlay](https://apis.io/overlays/nutshell/nutshell-quotes-overlay/)
- [Nutshell Sources Overlay](https://apis.io/overlays/nutshell/nutshell-sources-overlay/)
- [Nutshell Tags Overlay](https://apis.io/overlays/nutshell/nutshell-tags-overlay/)
- [Nutshell Tasks Overlay](https://apis.io/overlays/nutshell/nutshell-tasks-overlay/)
- [Nutshell Territories Overlay](https://apis.io/overlays/nutshell/nutshell-territories-overlay/)
- [Nutshell Users Overlay](https://apis.io/overlays/nutshell/nutshell-users-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Nutshell Authentication](https://apis.io/security/nutshell/nutshell-authentication/)
- [Nutshell Domain Security](https://apis.io/security/nutshell/nutshell-domain-security/)
- [Nutshell Trust Center](https://apis.io/security/nutshell/nutshell-trust-center/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Nutshell Scopes](https://apis.io/scopes/nutshell/nutshell-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Nutshell Plans Pricing](https://apis.io/plans/nutshell/nutshell-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Nutshell Rate Limits](https://apis.io/rate-limits/nutshell/nutshell-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.nutshell.com)
- [Documentation](https://developers.nutshell.com/docs)
- [Getting started](https://developers.nutshell.com/docs/getting-started)
- [API reference](https://developers.nutshell.com/reference)
- [Pricing](https://www.nutshell.com/pricing)
- [Sign up](https://app.nutshell.com/signup)
- [Support](https://support.nutshell.com)
- [Blog](https://www.nutshell.com/blog)
- [Compliance](https://www.nutshell.com/security)
- [Terms of service](https://www.nutshell.com/legal/terms)
- [Privacy policy](https://www.nutshell.com/legal/privacy)
- [GitHub](https://github.com/nutshellcrm)
- [Status](https://status.nutshell.com)

## API Evangelist rating

**Kin Score 60.7** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 80.0 |
| Contract quality | 54.5 |
| Contract governance | 18.2 |
| Operational transparency | 38.2 |
| Developer ergonomics | 53.0 |
| Access clarity | 92.1 |

**Agent readiness 52.2** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 39.2** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/nutshell/](https://apis.io/providers/nutshell/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Nutshell: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/nutshell/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
