# Exotec

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
