# BASICS Shared Core Standard v0.1.1

Status: Draft v0.1.1

## 1) Purpose

BASICS exists to help real teams build real tools under real constraints.
It is a commitments framework and a conformance baseline.

## 2) Normative Language

- MUST: required for conformance.
- SHOULD: strongly recommended; deviations require rationale.
- MAY: optional behavior.

## 3) External Reference Index

- `REF-ISO-25010`: [ISO/IEC 25010:2023](https://www.iso.org/standard/78176.html)
- `REF-ISO-42030`: [ISO/IEC/IEEE 42030:2019](https://www.iso.org/standard/73436.html)
- `REF-ISO-15288`: [ISO/IEC/IEEE 15288:2023](https://www.iso.org/standard/81702.html)
- `REF-RFC-6709`: [RFC 6709](https://rfc-editor.org/rfc/rfc6709.html)
- `REF-RFC-9170`: [RFC 9170](https://rfc-editor.org/rfc/rfc9170.html)
- `REF-W3C-VERSIONING`: [W3C TAG Extensibility and Versioning](http://www.w3.org/2001/tag/doc/versioning-strategies-20070917.html)
- `REF-SEMVER`: [Semantic Versioning 2.0.0](https://semver.org/)
- `REF-ANDROID-OFFLINE`: [Android Offline-First Guidance](https://developer.android.com/topic/architecture/data-layer/offline-first)
- `REF-RFC-4838`: [RFC 4838 Delay-Tolerant Networking Architecture](https://rfc-editor.org/rfc/rfc4838.html)

## 4) Shared Core Rules

### 4.1 Command and Interface Durability

- `BASICS-SC-001` (MUST): Tools expose a documented command surface with stable semantics.  
  Sources: `REF-ISO-25010`, `REF-ISO-42030`
- `BASICS-SC-002` (MUST): Primary UI actions map to explicit command semantics.  
  Sources: `REF-ISO-42030`, `REF-ISO-15288`
- `BASICS-SC-003` (MUST): Tools provide machine-readable output mode for automation.  
  Sources: `REF-ISO-25010`, `REF-SEMVER`
- `BASICS-SC-004` (SHOULD): Command surfaces follow Unix durability patterns (small composable operations, explicit text contracts, mechanism-first design).  
  Sources: `REF-ISO-25010`, `REF-ISO-42030`

### 4.2 Typologies and Command Classes

- `BASICS-SC-010` (MUST): Universal typologies are required: `records`, `actions`, `times`, `profiles`, `events`.  
  Sources: `REF-ISO-25010`, `REF-ISO-15288`
- `BASICS-SC-011` (MUST): Domain typologies are required when relevant: `exchanges`, `journals`, `assets`, `policies`.  
  Sources: `REF-ISO-15288`
- `BASICS-SC-012` (MUST): Canonical command classes are required: `create`, `edit`, `view/render`, `list/query`, `share/export`, `import`, `sync`, `policy:get/set`, `status/health`.  
  Sources: `REF-ISO-42030`, `REF-ISO-25010`

### 4.3 Operator Control, Profiles, and Storage

- `BASICS-SC-020` (MUST): Tools support profile/context separation and prevent unintended cross-profile leakage.  
  Sources: `REF-ISO-25010`, `REF-ISO-15288`
- `BASICS-SC-021` (MUST): Storage behavior (local, synced, ephemeral) is operator-visible and documented.  
  Sources: `REF-ISO-25010`, `REF-ISO-15288`
- `BASICS-SC-022` (MUST): Destructive or irreversible operations are explicit and intentional.  
  Sources: `REF-ISO-25010`, `REF-ISO-42030`

### 4.4 Architecture Decision Transparency

- `BASICS-SC-030` (MUST): Material architecture decisions are recorded as ADRs.  
  Sources: `REF-ISO-42030`
- `BASICS-SC-031` (MUST): ADRs include context, options, decision, and consequences.  
  Sources: `REF-ISO-42030`

### 4.5 Degraded-Mode and Constrained Operation

- `BASICS-SC-040` (MUST): Degraded behavior is defined for network loss, low storage, dependency/service loss, and integrity lock state.  
  Sources: `REF-ANDROID-OFFLINE`, `REF-ISO-25010`
- `BASICS-SC-041` (MUST): Core record create/edit works locally without network dependency.  
  Sources: `REF-ANDROID-OFFLINE`, `REF-RFC-4838`
- `BASICS-SC-042` (MUST): Deferred sync paths preserve accepted local mutations durably.  
  Sources: `REF-ANDROID-OFFLINE`, `REF-RFC-4838`
- `BASICS-SC-043` (MUST): Conflict comparison header includes record id, source ids, timestamps, change summary, and comparison mode.  
  Sources: `REF-ISO-25010`, `REF-ISO-42030`
- `BASICS-SC-044` (MAY): Read-only mode is allowed only as controlled degraded state with cause and recovery guidance.  
  Sources: `REF-ANDROID-OFFLINE`, `REF-ISO-25010`

### 4.6 Interoperability and Extension Policy

- `BASICS-SC-050` (MUST): Event schema and command semantics are published as interoperability baselines.  
  Sources: `REF-RFC-6709`, `REF-ISO-25010`
- `BASICS-SC-051` (MUST): Additive evolution is default; breaking changes require explicit compatibility signaling.  
  Sources: `REF-SEMVER`, `REF-RFC-6709`
- `BASICS-SC-052` (MUST): Unknown non-critical extensions are safely ignored without data corruption.  
  Sources: `REF-RFC-6709`, `REF-W3C-VERSIONING`
- `BASICS-SC-053` (MUST): Unknown critical extensions fail explicitly and safely.  
  Sources: `REF-RFC-6709`, `REF-W3C-VERSIONING`
- `BASICS-SC-054` (MUST): Extension points are exercised in conformance fixtures to prevent ossification.  
  Sources: `REF-RFC-9170`
- `BASICS-SC-055` (MAY): Naming deviations are permitted when semantics are preserved and deviation metadata is registered.  
  Sources: `REF-RFC-6709`, `REF-SEMVER`

### 4.7 Quality Benchmarks

- `BASICS-SC-060` (MUST): Releases define measurable criteria for reliability, maintainability, portability/flexibility, legibility, and performance efficiency.  
  Sources: `REF-ISO-25010`
- `BASICS-SC-061` (MUST): Reliability and performance evidence is published for each conformant release line.  
  Sources: `REF-ISO-25010`

## 5) Governance and Conformance Policy Rules

- `BASICS-GOV-001` (MUST): BASICS uses proposal plus community review governance.
  Sources: `REF-ISO-42030`, `REF-ISO-15288`
- `BASICS-GOV-002` (MUST): Governance lifecycle target is 100 days from draft to ratification decision.
  Sources: `REF-ISO-15288`
- `BASICS-GOV-003` (MUST): Conformance may be run by Babb or delegated partners; delegated publication requires Babb and partner review.
  Sources: `REF-ISO-42030`
- `BASICS-GOV-004` (MUST): Public conformance claims include spec version, tier, profiles, and evidence URI.
  Sources: `REF-ISO-42030`
- `BASICS-GOV-005` (MUST): Requirement sunset includes superseding rule, migration path, overlap period, and removal date.
  Sources: `REF-SEMVER`, `REF-ISO-15288`

## 6) Tier Policy Rules

- `BASICS-TIER-001` (MUST): Higher tiers include all lower-tier mandatory requirements.
  Sources: `REF-ISO-15288`
- `BASICS-TIER-002` (MUST): Higher tiers cannot weaken lower-tier guarantees.
  Sources: `REF-ISO-15288`
- `BASICS-TIER-003` (MUST): Mandatory controls are binary pass/fail; optional controls are maturity-scored.
  Sources: `REF-ISO-42030`, `REF-ISO-25010`
- `BASICS-TIER-010` (MUST): Core tier requires published command contract, local record create/edit, and baseline interop docs.
  Sources: `REF-ANDROID-OFFLINE`, `REF-RFC-6709`
- `BASICS-TIER-011` (MUST): Field tier requires degraded-mode and sync/conflict evidence.
  Sources: `REF-ANDROID-OFFLINE`, `REF-RFC-4838`
- `BASICS-TIER-012` (MUST): Industrial tier requires security lifecycle evidence and published reviewed conformance results.
  Sources: `REF-ISO-15288`, `REF-ISO-42030`

## 7) Versioning and Compatibility Rules

- `BASICS-VERS-001` (MUST): BASICS spec uses semantic versioning.
  Sources: `REF-SEMVER`
- `BASICS-VERS-002` (MUST): Normative requirements use stable rule IDs.
  Sources: `REF-SEMVER`
- `BASICS-VERS-003` (MUST): Minor/major releases publish migration and deprecation notes.
  Sources: `REF-SEMVER`, `REF-ISO-15288`
- `BASICS-VERS-004` (MUST): Compatibility preserves operation at the simplest supported profile ("no device left behind").
  Sources: `REF-ISO-25010`, `REF-ANDROID-OFFLINE`

## 8) Minimum Evidence

- `BASICS-EVID-001` (MUST): Projects publish command surface spec.
  Sources: `REF-ISO-42030`
- `BASICS-EVID-002` (MUST): Projects publish event schema spec.
  Sources: `REF-RFC-6709`
- `BASICS-EVID-003` (MUST): Projects publish ADR index.
  Sources: `REF-ISO-42030`
- `BASICS-EVID-004` (MUST): Projects publish compatibility and deviation policy.
  Sources: `REF-SEMVER`, `REF-RFC-6709`
- `BASICS-EVID-005` (MUST): Projects publish degraded-mode behavior matrix and tier test results.
  Sources: `REF-ANDROID-OFFLINE`, `REF-ISO-25010`

## 9) Proof Product Priority

- `BASICS-PROOF-001` (POLICY): `workpads` is the primary proof product for early BASICS hardening cycles.
  Sources: `REF-ISO-15288`

