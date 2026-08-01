# Booksy

Booksy is a beauty, wellness and health services platform that pairs a consumer appointment marketplace (booksy.com) with **Booksy Biz**, a subscription business-management application for salons, barbershops, spas, nail studios, tattoo artists and other independent service providers — online booking, calendar and staff scheduling, client records, inventory, no-show protection, loyalty, marketing and integrated card payments.

Booksy also operates the **Booksy Public API**, a partner-facing REST API documented at [docs.booksy.com](https://docs.booksy.com/).

## API at a glance

| | |
|---|---|
| Base URL | `https://<country_code>.booksy.com/public-api/<country_code>/` (e.g. `https://us.booksy.com/public-api/us/`) |
| Style | REST / JSON, resource-oriented, trailing-slash paths |
| Versioning | `Accept: application/json; version=0.3` (0.1, 0.2, 0.3) |
| Auth | Partner RSA key pair signs an RS256 JWT assertion, exchanged at `/token/` for a 5-minute access token + 3-day refresh token, sent as `Authorization: Bearer` |
| Surface | 96 documented endpoints across 21 resources |
| Events | Appointment webhook (`CREATED` / `MODIFIED` / `CANCELLED`) with 5/10/20/40-minute backoff |
| Rate limits | 10 req/min unauthenticated, 200 req/min authenticated |
| Machine-readable spec | none published (no OpenAPI, GraphQL, AsyncAPI, MCP or A2A agent card) |
| Docs access | **HTTP Basic gated** — `docs.booksy.com` returns 401 to anonymous clients; credentials are issued to partners |

## Artifacts

- `authentication/` — auth profile (partner JWT assertion + bearer)
- `conventions/` — versioning, pagination, external identifiers, error envelope, rate-limit signalling
- `errors/` — error catalog and observed response envelopes
- `rate-limits/` — published request limits
- `asyncapi/` — appointment webhook catalog
- `data-model/` — entity graph and the full documented endpoint inventory
- `lifecycle/` — versioning and status page
- `changelog/` — Booksy Biz release notes
- `plans/` — published Booksy Biz pricing and processing rates
- `sandbox/` — sandbox vs production separation
- `conformance/` — standards conformance and negative spec-discovery results
- `security/` — domain security probe, trust center
- `well-known/` — `/.well-known/` probe results (all misses, recorded)
- `llms/` — llms.txt for agents

## Links

- Website — https://booksy.com/en-us/
- Booksy Biz — https://biz.booksy.com/
- API docs — https://docs.booksy.com/
- Pricing — https://biz.booksy.com/pricing
- What's new — https://biz.booksy.com/whats-new
- Help center — https://help.booksy.com/hc/en-us
- Blog — https://blog.booksy.com/us/
- Status — https://status.booksy.com/
- Trust center — https://trust.booksy.com/
