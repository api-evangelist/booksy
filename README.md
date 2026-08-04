# Booksy

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
