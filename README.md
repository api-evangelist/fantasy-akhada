# Fantasy Akhada

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

Fantasy Akhada is an Indian daily-fantasy-sports platform operated by **Super Six Sports Gaming
Private Limited** (CIN `U72900HR2019PTC083570`) of Gurugram, Haryana. Founded in 2020 by Amit Purohit,
Sumit Kumar Jha, Sahil Ahuja, Amit Bhardwaj and Ankit Upreti, with cricket commentator Harsha Bhogle as
brand ambassador, it let users build virtual teams for real cricket, football, kabaddi, basketball and
hockey fixtures and enter free and cash contests, taking a commission on entry fees.

## API surface

**None.** Fantasy Akhada shipped only as a consumer product — an iOS app, a sideloaded Android APK, and
a React single-page web lobby. There is no developer program, public API, SDK, webhook surface, or
developer portal, and none has ever been published.

Contract discovery was run in full on 2026-08-12 and every probe missed:

| Probe | Result |
|---|---|
| `www.fantasyakhada.com`, `fantasyakhada.com` | **NXDOMAIN** — `www` is a dangling CNAME to `dualstack.supersix-alb-76454354.ap-south-1.elb.amazonaws.com`, a deleted AWS ap-south-1 load balancer; the apex carries no address record |
| `api.` / `u.` / `f.` / `gu.` / `gf.` / `scorecard.` / `prediction.` `.fantasyakhada.com` | **NXDOMAIN** — every backend service host named in the company's own JavaScript bundles has been withdrawn from DNS |
| `node.fantasyakhada.com:4000` | resolves (13.127.255.194) but the socket times out |
| OpenAPI / Swagger / GraphQL / MCP paths on every live host | HTTP 200, but the single-page-app catch-all HTML, not a spec |
| `/.well-known/*` (security.txt, openid-configuration, oauth-*, api-catalog, ai-plugin, agent-card, agent) | HTTP 200 catch-all HTML on all three live hosts — **no documents** |
| A2A agent card | no hit — nothing written, per pipeline policy |
| npm / PyPI / GitHub organization | no first-party packages, no organization |
| Google Play `com.fantasyakhada.akhada`, App Store `id1555409649` | HTTP 404 |

Only stale static CloudFront/S3 builds survive: `app.fantasyakhada.com` (last modified 2023-10-14),
`webview.fantasyakhada.com` (2024-07-11) and `affiliate.fantasyakhada.com`. India's Promotion and
Regulation of Online Gaming Act 2025 banned real-money online games nationwide in August 2025.

## What is in this repository

- `apis.yml` — company identity, references, and the `x-coverage` record of why this profile is thin
- `security/fantasy-akhada-domain-security.yml` — probed TLS/HSTS/DNSSEC/CAA/SPF/DMARC posture
- `well-known/fantasy-akhada-well-known.yml` — the `.well-known` probe, recording an absence

## Links

- Landing page: https://affiliate.fantasyakhada.com/
- Parent company: https://www.supersixsports.com/
- LinkedIn: https://in.linkedin.com/company/fantasyakhada
