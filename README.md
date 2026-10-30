# AIScan

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

AIScan is an AI-visibility auditing service at getaiscan.app that scans any website in about 60 seconds and returns four 0-100 scores — AEO (AI search visibility), GEO (citation readiness), Agent Readiness and MCP Readiness — from 80+ checks, plus a Brand Visibility measurement of how often AI assistants actually name a brand across 30 realistic niche prompts. Humans buy a full report on the site for 60 USDC; software agents buy 19 individual capabilities pay-per-call (0.06-3.50 USDC) through the x402 protocol on Base (eip155:8453) with no API key and no account, via a 20-operation OpenAPI 3.1.0 REST contract served from api.getaiscan.app, an A2A 0.3.0 agent card with 18 skills at /.well-known/agent-card.json, an ai-plugin.json manifest and an MCP discovery descriptor at /.well-known/mcp.json. Every paid route answers an unpaid call with a real HTTP 402 x402 V2 challenge; the capability catalog at GET /api/agent/index is free.

**Areas:** AI Visibility · Website Auditing · SEO · Answer Engine Optimization · Generative Engine Optimization · Agents · Agentic Commerce · A2A · MCP · x402 · Agent-Native

## AIScan on APIs.io

Everything profiled for AIScan is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/getaiscan-app/](https://apis.io/providers/getaiscan-app/)** — or go straight to one of the APIs or properties below.

### APIs (3)

- [AIScan A2A Agent](https://apis.io/apis/getaiscan-app/aiscan-a2a-agent/) — Agent2Agent (A2A) protocol surface: an agent card served from https://getaiscan.app/.well-known/agent-card.json (protocolVersion 0.3.0, JSONRPC transport,…
- [AIScan Agent API](https://apis.io/apis/getaiscan-app/getaiscan-app-agent-api/) — The Agent API from AIScan — 2 operation(s) for agent.
- [AIScan AI Visibility API](https://apis.io/apis/getaiscan-app/getaiscan-app-ai-visibility-api/) — The AI Visibility API from AIScan — 19 operation(s) for ai visibility.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [getaiscan-app-mcp.yml](https://apis.io/servers/getaiscan-app/getaiscan-app-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Getaiscan App Agentic Access](https://apis.io/agentic-access/getaiscan-app/getaiscan-app-agentic-access/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Getaiscan App Openapi Overlay](https://apis.io/overlays/getaiscan-app/getaiscan-app-openapi-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Getaiscan App Authentication](https://apis.io/security/getaiscan-app/getaiscan-app-authentication/)
- [Getaiscan App Domain Security](https://apis.io/security/getaiscan-app/getaiscan-app-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Getaiscan App Plans Pricing](https://apis.io/plans/getaiscan-app/getaiscan-app-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Getaiscan App Rate Limits](https://apis.io/rate-limits/getaiscan-app/getaiscan-app-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://getaiscan.app/)
- [Documentation](https://getaiscan.app/llms.txt)
- [API reference](https://api.getaiscan.app/openapi.json)
- [Pricing](https://api.getaiscan.app/api/agent/index)
- [Blog](https://getaiscan.app/blog/)

## API Evangelist rating

**Kin Score 36.7** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 78.6 |
| Contract quality | 48.5 |
| Contract governance | 18.2 |
| Operational transparency | 0.0 |
| Developer ergonomics | 32.7 |
| Access clarity | 42.1 |

**Agent readiness 32.6** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | yes |
| Consent Identity | — |
| Agent Card | conformant |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 16.7** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/getaiscan-app/](https://apis.io/providers/getaiscan-app/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for AIScan: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/getaiscan-app/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
