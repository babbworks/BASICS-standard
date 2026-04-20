# BASICS Software Profile v0.1.1

Status: Draft v0.1.1

This profile extends Shared Core for software systems.

## 1) External Reference Index

- `REF-NIST-SSDF`: [NIST SP 800-218](https://csrc.nist.gov/publications/detail/sp/800-218/final)
- `REF-NIST-CSF2`: [NIST CSF 2.0](https://csrc.nist.gov/pubs/cswp/29/the-nist-cybersecurity-framework-csf-20/final)
- `REF-NTIA-SBOM`: [NTIA SBOM Minimum Elements](https://www.ntia.gov/report/2021/minimum-elements-software-bill-materials-sbom)
- `REF-SLSA`: [SLSA v1.0](https://slsa.dev/spec/v1.0/onepage)
- `REF-IN-TOTO`: [in-toto and SLSA](https://slsa.dev/blog/2023/05/in-toto-and-slsa)
- `REF-AIP-180`: [AIP-180 Backward Compatibility](https://google.aip.dev/180)
- `REF-CWE-2024`: [CWE Top 25 2024](https://cwe.mitre.org/top25/archive/2024/2024_top25_list.html)
- `REF-ANDROID-OFFLINE`: [Android Offline-First Guidance](https://developer.android.com/topic/architecture/data-layer/offline-first)

## 2) Software Rules

### 2.1 Architecture and Contracts

- `BASICS-SW-001` (MUST): Services define clear ownership boundaries and published contracts.
  Sources: `REF-AIP-180`
- `BASICS-SW-002` (MUST): Event and command contracts are versioned with compatibility notes.
  Sources: `REF-AIP-180`
- `BASICS-SW-003` (MUST): Breaking contract changes include migration guidance and compatibility signaling.
  Sources: `REF-AIP-180`
- `BASICS-SW-004` (MUST): Simplest maintained profile behavior is documented and supported.
  Sources: `REF-ANDROID-OFFLINE`

### 2.2 Local-First Operation

- `BASICS-SW-010` (MUST): Core record create/edit works without active network.
  Sources: `REF-ANDROID-OFFLINE`
- `BASICS-SW-011` (MUST): Deferred mutation handling is durable (queue/log/outbox equivalent).
  Sources: `REF-ANDROID-OFFLINE`
- `BASICS-SW-012` (MUST): Accepted local mutations are not silently lost across restart/power interruption.
  Sources: `REF-ANDROID-OFFLINE`
- `BASICS-SW-013` (MUST): Operator-visible sync status and failure reason are provided.
  Sources: `REF-ANDROID-OFFLINE`

### 2.3 Conflict Integrity

- `BASICS-SW-020` (MUST): Conflicting edits are detected deterministically.
  Sources: `REF-AIP-180`
- `BASICS-SW-021` (MUST): Operator compare views are provided for conflict resolution.
  Sources: `REF-AIP-180`
- `BASICS-SW-022` (MAY): Auto-merge is allowed only when outputs remain auditable.
  Sources: `REF-AIP-180`

### 2.4 Security and Vulnerability Practice

- `BASICS-SW-030` (MUST): Secure development lifecycle maps to SSDF practice groups.
  Sources: `REF-NIST-SSDF`
- `BASICS-SW-031` (MUST): Critical/high exploitable weaknesses are blocked from release unless time-bounded exception is approved.
  Sources: `REF-NIST-SSDF`, `REF-CWE-2024`
- `BASICS-SW-032` (MUST): Security defaults prioritize safe operation and least surprise.
  Sources: `REF-NIST-CSF2`
- `BASICS-SW-033` (SHOULD): Exceptions publish security notes with mitigation owner and remediation target date.
  Sources: `REF-NIST-CSF2`

### 2.5 Supply Chain Transparency

- `BASICS-SW-040` (MUST): Release artifacts include SBOM metadata.
  Sources: `REF-NTIA-SBOM`
- `BASICS-SW-041` (MUST): Build provenance attestations are published.
  Sources: `REF-SLSA`, `REF-IN-TOTO`
- `BASICS-SW-042` (SHOULD): Build integrity maturity increases over time.
  Sources: `REF-SLSA`

### 2.6 Quality and Evidence

- `BASICS-SW-050` (MUST): Software quality evidence includes reliability, maintainability, portability/flexibility, legibility, and performance indicators.
  Sources: `REF-NIST-CSF2`
- `BASICS-SW-051` (SHOULD): Reference behavior fixtures are provided in multiple languages where practical to validate adaptation consistency.
  Sources: `REF-AIP-180`

