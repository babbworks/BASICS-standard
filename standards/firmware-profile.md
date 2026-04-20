# BASICS Firmware Profile v0.1.1

Status: Draft v0.1.1

## 1) External Reference Index

- `REF-NIST-800-193`: [NIST SP 800-193](https://csrc.nist.gov/publications/detail/sp/800-193/final)
- `REF-RFC-9019`: [RFC 9019 SUIT Architecture](https://datatracker.ietf.org/doc/rfc9019/)
- `REF-TUF-SPEC`: [TUF Specification](https://theupdateframework.github.io/specification/latest)
- `REF-UPTANE`: [Uptane Standard](https://uptane.org/docs/latest/standard/uptane-standard)
- `REF-NIST-SSDF`: [NIST SP 800-218](https://csrc.nist.gov/publications/detail/sp/800-218/final)
- `REF-NTIA-SBOM`: [NTIA SBOM Minimum Elements](https://www.ntia.gov/report/2021/minimum-elements-software-bill-materials-sbom)
- `REF-SLSA`: [SLSA v1.0](https://slsa.dev/spec/v1.0/onepage)

## 2) Firmware Rules

### 2.1 Trust, Integrity, and Recovery

- `BASICS-FW-001` (MUST): Platforms implement protect/detect/recover controls for unauthorized modification.
  Sources: `REF-NIST-800-193`
- `BASICS-FW-002` (MUST): Boot and activation verify firmware authenticity and integrity.
  Sources: `REF-NIST-800-193`, `REF-RFC-9019`
- `BASICS-FW-003` (MUST): Trusted recovery path is documented and tested.
  Sources: `REF-NIST-800-193`

### 2.2 Secure Update Architecture

- `BASICS-FW-010` (MUST): Updates include signed metadata/manifest with verification policy.
  Sources: `REF-RFC-9019`, `REF-TUF-SPEC`
- `BASICS-FW-011` (MUST): Update metadata includes freshness/expiration semantics.
  Sources: `REF-TUF-SPEC`
- `BASICS-FW-012` (MUST): Key rotation and revocation are supported.
  Sources: `REF-TUF-SPEC`, `REF-UPTANE`
- `BASICS-FW-013` (MUST): Update failure fails safely and preserves recoverability.
  Sources: `REF-NIST-800-193`, `REF-RFC-9019`
- `BASICS-FW-014` (MUST): Rollback policy is explicit and verifiable.
  Sources: `REF-TUF-SPEC`, `REF-UPTANE`

### 2.3 Role Separation

- `BASICS-FW-020` (MUST): Trust model separates root, targets/image authorization, snapshot/consistency, and timestamp/freshness roles.
  Sources: `REF-TUF-SPEC`, `REF-UPTANE`
- `BASICS-FW-021` (MUST): Single-role key compromise does not imply total trust collapse.
  Sources: `REF-TUF-SPEC`, `REF-UPTANE`

### 2.4 Constrained Delivery

- `BASICS-FW-030` (SHOULD): Update flow supports intermittent connectivity and delayed delivery.
  Sources: `REF-RFC-9019`
- `BASICS-FW-031` (MAY): Staged payload storage is allowed before verified application.
  Sources: `REF-RFC-9019`
- `BASICS-FW-032` (MUST): Minimal update/recovery path is maintained for the simplest supported profile.
  Sources: `REF-NIST-800-193`, `REF-RFC-9019`

### 2.5 Vulnerability and Supply Chain

- `BASICS-FW-040` (MUST): Patch policy, support window, and disclosure channel are published.
  Sources: `REF-NIST-SSDF`
- `BASICS-FW-041` (MUST): Security patches are traceable from advisory to deployed artifact.
  Sources: `REF-NIST-SSDF`
- `BASICS-FW-042` (MUST): Firmware artifacts include SBOM coverage and provenance attestations.
  Sources: `REF-NTIA-SBOM`, `REF-SLSA`

