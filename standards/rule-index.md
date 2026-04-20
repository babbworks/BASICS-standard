# BASICS Rule Index v0.1.1

Status: Draft v0.1.1

This index is the canonical quick-reference for BASICS rule IDs.
Use it to map requirements across documents, conformance checks, and deviation entries.

## 1) Shared Core Rules (`standards/shared-core.md`)

- `BASICS-SC-001` documented command surface with stable semantics
- `BASICS-SC-002` UI actions map to explicit command semantics
- `BASICS-SC-003` machine-readable output mode for automation
- `BASICS-SC-004` Unix durability patterns for command surfaces
- `BASICS-SC-010` required universal typologies
- `BASICS-SC-011` required domain typologies when relevant
- `BASICS-SC-012` canonical command classes
- `BASICS-SC-020` profile/context separation
- `BASICS-SC-021` operator-visible storage behavior
- `BASICS-SC-022` explicit destructive operations
- `BASICS-SC-030` ADRs for material architecture decisions
- `BASICS-SC-031` ADR content requirements
- `BASICS-SC-040` degraded-mode definitions
- `BASICS-SC-041` local core record create/edit
- `BASICS-SC-042` durable deferred sync
- `BASICS-SC-043` conflict comparison header contract
- `BASICS-SC-044` controlled read-only degraded mode
- `BASICS-SC-050` published event/command interoperability baselines
- `BASICS-SC-051` additive evolution default + break signaling
- `BASICS-SC-052` unknown non-critical extension handling
- `BASICS-SC-053` unknown critical extension handling
- `BASICS-SC-054` extension-point anti-ossification exercise
- `BASICS-SC-055` naming deviation allowance with registry metadata
- `BASICS-SC-060` required quality criteria set
- `BASICS-SC-061` required reliability/performance evidence

## 2) Governance, Tier, Version, and Evidence Rules (`standards/shared-core.md`)

- `BASICS-GOV-001` proposal plus community review governance
- `BASICS-GOV-002` 100-day governance target
- `BASICS-GOV-003` Babb or delegated conformance execution with joint publication review
- `BASICS-GOV-004` public claim metadata requirements
- `BASICS-GOV-005` requirement sunset mechanics
- `BASICS-TIER-001` tier inheritance
- `BASICS-TIER-002` no weakening at higher tiers
- `BASICS-TIER-003` binary mandatory plus scored optional model
- `BASICS-TIER-010` Core tier entry controls
- `BASICS-TIER-011` Field tier entry controls
- `BASICS-TIER-012` Industrial tier entry controls
- `BASICS-VERS-001` semver for BASICS specification
- `BASICS-VERS-002` stable rule identifiers
- `BASICS-VERS-003` migration/deprecation publication requirements
- `BASICS-VERS-004` simplest-profile compatibility preservation
- `BASICS-EVID-001` command surface evidence
- `BASICS-EVID-002` event schema evidence
- `BASICS-EVID-003` ADR index evidence
- `BASICS-EVID-004` compatibility and deviation evidence
- `BASICS-EVID-005` degraded-mode and tier test evidence
- `BASICS-PROOF-001` workpads proof-product policy

## 3) Software Rules (`standards/software-profile.md`)

- `BASICS-SW-001` software boundary and contract ownership
- `BASICS-SW-002` versioned event/command contracts
- `BASICS-SW-003` migration requirement for breaking changes
- `BASICS-SW-004` simplest-profile behavior support
- `BASICS-SW-010` offline core create/edit
- `BASICS-SW-011` durable deferred mutation handling
- `BASICS-SW-012` no silent accepted-mutation loss
- `BASICS-SW-013` operator-visible sync/failure status
- `BASICS-SW-020` deterministic conflict detection
- `BASICS-SW-021` operator compare view
- `BASICS-SW-022` auditable auto-merge constraints
- `BASICS-SW-030` SSDF-mapped secure development lifecycle
- `BASICS-SW-031` critical/high exploitability release blocking policy
- `BASICS-SW-032` safe default security behavior
- `BASICS-SW-033` security notes for exceptions
- `BASICS-SW-040` SBOM release requirement
- `BASICS-SW-041` provenance attestation requirement
- `BASICS-SW-042` build integrity maturity progression
- `BASICS-SW-050` software quality evidence
- `BASICS-SW-051` multi-language adaptation consistency fixtures

## 4) Hardware Rules (`standards/hardware-profile.md`)

- `BASICS-HW-001` controlled hardware build/release and revision impact tracking
- `BASICS-HW-002` traceable nonconformance/corrective actions
- `BASICS-HW-003` published support horizon and spare policy
- `BASICS-HW-004` revision-test-defect traceability
- `BASICS-HW-010` test access and diagnostics pathways
- `BASICS-HW-011` explicit repeatable pass/fail manufacturing tests
- `BASICS-HW-012` coverage and post-repair retest requirements
- `BASICS-HW-013` non-destructive field diagnostics preference
- `BASICS-HW-020` replace/repair/refurbish/retire service model
- `BASICS-HW-021` high-failure component accessibility preference
- `BASICS-HW-022` service documentation minimums
- `BASICS-HW-023` maintainable standardized interfaces/parts preference
- `BASICS-HW-030` device capability profile minimums
- `BASICS-HW-031` lifecycle security control documentation
- `BASICS-HW-032` threat model update trigger
- `BASICS-HW-040` declared hardware module compatibility level
- `BASICS-HW-041` discrete optional-module identity in manifests
- `BASICS-HW-042` registered module deviation requirement

## 5) Firmware Rules (`standards/firmware-profile.md`)

- `BASICS-FW-001` protect/detect/recover controls
- `BASICS-FW-002` boot and activation authenticity/integrity verification
- `BASICS-FW-003` trusted recovery path testability
- `BASICS-FW-010` signed metadata/manifest updates
- `BASICS-FW-011` freshness/expiration metadata controls
- `BASICS-FW-012` key rotation and revocation support
- `BASICS-FW-013` safe update failure and recoverability
- `BASICS-FW-014` explicit verifiable rollback policy
- `BASICS-FW-020` role-separated trust model requirements
- `BASICS-FW-021` single-role compromise blast-radius limitation
- `BASICS-FW-030` intermittent/delayed delivery support preference
- `BASICS-FW-031` staged payload allowance
- `BASICS-FW-032` simplest-profile update/recovery path
- `BASICS-FW-040` published patch policy/support/disclosure
- `BASICS-FW-041` advisory-to-artifact patch traceability
- `BASICS-FW-042` firmware SBOM and provenance requirement

## 6) Deviation Policy Rules (`standards/deviation-registry.md`)

- `BASICS-DEV-POL-001` all normative deviations registered
- `BASICS-DEV-POL-002` long-lived stable URI per deviation
- `BASICS-DEV-POL-003` historical visibility after supersession
- `BASICS-DEV-POL-004` lifecycle-governed deviation acceptance

## 7) Maintenance Notes

- Add new rules here when they are ratified in profile documents.
- Do not reuse retired IDs.
- If a rule is superseded, keep the old ID in this index and mark status in source document.

