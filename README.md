# Exotec

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

Exotec is a French warehouse automation manufacturer and integrator (founded 2015, headquartered in Croix, France) that builds the **Skypod** robotic automated storage and retrieval system (AS/RS) and the **Deepsky** warehouse execution system (WES) that orchestrates it. More than 10,000 robots are deployed across 200+ customer sites for 50+ brands.

- Website: https://www.exotec.com/
- Deepsky WES: https://www.exotec.com/system/warehouse-optimization-software/
- Support: https://www.exotec.com/warehouse-automation-support/
- Secondary market listing: https://forgeglobal.com/exotec_stock/

## API posture

Exotec's Deepsky WES / Astar WCS connects to a customer's WMS over a RESTful web-services
interface, but **that interface is not public**. It is delivered as customer-specific
functional documentation under a commercial deployment, so there is no developer portal,
no API reference, no OpenAPI/AsyncAPI/GraphQL/MCP surface, no SDK and no sandbox.

Contract discovery on 2026-07-31 probed every plausible host and path and found nothing:
`developer.`, `docs.`, `api.`, `portal.`, `my.`, `app.`, `status.` all NXDOMAIN;
`/openapi.json`, `/swagger.json` and every `/.well-known/*` path 404.
`api.exotec.com` still carries a **dangling CNAME** to a removed AWS API Gateway custom
domain (`dc50zvit13.execute-api.eu-west-3.amazonaws.com`, NXDOMAIN) — recorded in
`security/exotec-domain-security.yml`.

## Artifacts

| Artifact | Method | Notes |
|---|---|---|
| `llms/exotec-llms.txt` | searched | Real provider-published `llms.txt` from https://www.exotec.com/llms.txt, saved verbatim — includes Preferred Citations and Authoritative Sources guidance for AI consumers |
| `conformance/exotec-conformance.yml` | searched | ISO/IEC 27001:2022 + SOC 2 Type 2 confirmed; full contract-discovery negative record |
| `packages/exotec-packages.yml` | searched | No client SDK on any registry; one first-party npm test utility; two `@exotec/*` packages excluded as a different entity (exotec.de) |
| `lifecycle/exotec-lifecycle.yml` | searched | Product-generation lifecycle (First Gen / Next Gen Skypod) + 98% availability contractual benchmark; no API versioning or deprecation policy |
| `security/exotec-domain-security.yml` | probed | TLS 1.3, HSTS, SPF, DMARC quarantine; no DNSSEC, no CAA; dangling `api.` CNAME |
| `well-known/exotec-well-known.yml` | probed | All well-known paths 404 — honest negative index, no pointer wired |

No agent card, MCP server, AsyncAPI, webhooks, status page, security.txt, bug bounty,
CLI, components, changelog or sandbox exist — nothing was authored on Exotec's behalf.
