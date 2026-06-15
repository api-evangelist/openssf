# OpenSSF (openssf)

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
