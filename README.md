# OpenSSF (openssf)

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

The Open Source Security Foundation (OpenSSF) is a collaborative initiative under the Linux Foundation dedicated to improving the security of open source software. It brings together industry leaders, developers, and security experts to address vulnerabilities, enhance supply chain security, and develop security tools and best practices. OpenSSF stewards a number of projects with public REST APIs, including the OSV (Open Source Vulnerabilities) database, the Scorecard automated security health-check service, and Sigstore signing infrastructure.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/openssf/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/openssf/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- Linux Foundation
- Open Source
- Security
- Supply Chain
- Vulnerabilities

## Timestamps

- **Created:** 2026-03-16
- **Modified:** 2026-05-19

## APIs

### OSV (Open Source Vulnerabilities) API

OSV is an OpenSSF-hosted distributed vulnerability database and query infrastructure. The OSV API at api.osv.dev exposes vulnerability records keyed to specific package versions or commits across multiple ecosystems including npm, PyPI, Maven, Go, NuGet, RubyGems, Cargo, Packagist, Hex, OSS-Fuzz, Linux, Android, and GitHub Actions.

- **Human URL:** [https://osv.dev/](https://osv.dev/)
- **Base URL:** `https://api.osv.dev`

#### Tags

- Vulnerabilities
- Supply Chain
- Database
- Open Source

#### Properties

- [Documentation](https://google.github.io/osv.dev/api/)
- [Documentation](https://osv.dev/)
- [GitHub Repository](https://github.com/google/osv.dev)
- [GitHub Repository](https://github.com/ossf/osv-schema)
- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/openssf/refs/heads/main/openapi/openssf-osv-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [JSON Schema](https://raw.githubusercontent.com/api-evangelist/openssf/refs/heads/main/json-schema/openssf-osv-vulnerability-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [J S O N L D Context](https://raw.githubusercontent.com/api-evangelist/openssf/refs/heads/main/json-ld/openssf-context.jsonld)
- [Postman Collection](collections/openssf-osv.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openssf-osv.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/openssf-scorecard.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openssf-scorecard.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### OpenSSF Scorecard API

The OpenSSF Scorecard API returns automated security health metrics for public open source repositories. Scorecard runs a series of checks (e.g., Branch-Protection, Code-Review, Pinned-Dependencies, Signed-Releases, Token-Permissions, Vulnerabilities) and exposes per-check scores plus an aggregate 0-10 score via api.securityscorecards.dev.

- **Human URL:** [https://scorecard.dev/](https://scorecard.dev/)
- **Base URL:** `https://api.securityscorecards.dev`

#### Tags

- Security Health
- Repositories
- Supply Chain

#### Properties

- [Documentation](https://github.com/ossf/scorecard)
- [Documentation](https://scorecard.dev/)
- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/openssf/refs/heads/main/openapi/openssf-scorecard-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [J S O N L D Context](https://raw.githubusercontent.com/api-evangelist/openssf/refs/heads/main/json-ld/openssf-context.jsonld)
- [Postman Collection](collections/openssf-osv.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openssf-osv.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/openssf-scorecard.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openssf-scorecard.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Sigstore Public Good APIs

Sigstore is an OpenSSF-hosted standard and service for signing, verifying, and protecting software. The public-good Sigstore instance exposes Fulcio (code-signing certificate authority) and Rekor (transparency log) APIs that can be queried programmatically to inspect signing certificates and transparency log entries.

- **Human URL:** [https://www.sigstore.dev/](https://www.sigstore.dev/)
- **Base URL:** `https://rekor.sigstore.dev`

#### Tags

- Signing
- Transparency Log
- Supply Chain

#### Properties

- [Documentation](https://docs.sigstore.dev/)
- [Documentation](https://docs.sigstore.dev/logging/overview/)
- [GitHub Organization](https://github.com/sigstore)
- [Postman Collection](collections/openssf-osv.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openssf-osv.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/openssf-scorecard.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openssf-scorecard.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### GUAC (Graph for Understanding Artifact Composition)

GUAC aggregates software supply-chain security metadata (SBOMs, attestations, vulnerabilities, signatures) into a queryable graph. GUAC exposes a GraphQL API for supply-chain queries when self-hosted.

- **Human URL:** [https://guac.sh/](https://guac.sh/)
- **Base URL:** `https://guac.sh`

#### Tags

- SBOM
- Supply Chain
- GraphQL

#### Properties

- [Documentation](https://docs.guac.sh/)
- [GitHub Repository](https://github.com/guacsec/guac)
- [Postman Collection](collections/openssf-osv.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openssf-osv.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/openssf-scorecard.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/openssf-scorecard.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/openssf)
- [Website](https://openssf.org/)
- [Documentation](https://openssf.org/resources/)
- [Portal](https://openssf.org/projects/)
- [Blog](https://openssf.org/blog/)
- [GitHub Organization](https://github.com/ossf)
- [GitHub Repository](https://github.com/ossf/osv-schema)
- [GitHub Repository](https://github.com/ossf/scorecard)
- [GitHub Organization](https://github.com/sigstore)
- [License](https://www.apache.org/licenses/LICENSE-2.0)
- [Community](https://openssf.org/community/)
- [Slack](https://slack.openssf.org/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
