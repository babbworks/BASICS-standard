# BASICS Conformance Checklist v0.1.1

Status: Draft v0.1.1

## 1) Usage

Use this checklist for self-assessment, delegated assessment, or Babb-led conformance review.

Scoring model:

- Mandatory controls: binary pass/fail
- Optional controls: maturity score (0-3)

Conformance can be administered by Babb or delegated partners.
Published results require Babb and partner review when delegated.

## 2) Claim Metadata (Required)

- Tool/Product name
- BASICS spec version
- Claimed tier (`Core`, `Field`, `Industrial`)
- Applicable profiles (`shared-core`, `software`, `hardware`, `firmware`)
- Evidence URI
- Active deviation IDs

Reference policy: `BASICS-GOV-004`.

## 3) Core Tier Mandatory Controls (Pass/Fail)

- [ ] `BASICS-TIER-010` Command contract published
- [ ] `BASICS-EVID-002` Event schema published
- [ ] `BASICS-SC-041` Local record create/edit works without network
- [ ] `BASICS-EVID-004` Compatibility/deviation policy published
- [ ] `BASICS-EVID-005` Degraded-mode matrix published

## 4) Field Tier Additional Mandatory Controls (Pass/Fail)

- [ ] `BASICS-TIER-011` All Core controls pass
- [ ] `BASICS-EVID-005` Degraded-mode test evidence published
- [ ] `BASICS-SC-043` Conflict comparison header contract implemented
- [ ] `BASICS-SC-042` Sync/conflict operator status surface verified
- [ ] `BASICS-TIER-011` Constrained deployment behavior validated

## 5) Industrial Tier Additional Mandatory Controls (Pass/Fail)

- [ ] `BASICS-TIER-012` All Field controls pass
- [ ] `BASICS-TIER-012` Security lifecycle evidence published
- [ ] `BASICS-SW-040` or `BASICS-FW-042` Supply-chain evidence published
- [ ] `BASICS-GOV-003` Published conformance results reviewed by Babb and partner (if delegated)

## 6) Optional Maturity Controls (0-3)

Scale:

- 0 = not present
- 1 = partial/manual
- 2 = implemented/repeatable
- 3 = automated/continuously evidenced

Controls:

- [ ] Extension-point anti-ossification testing
- [ ] Multi-language reference fixtures for behavior parity
- [ ] Cross-version compatibility test automation
- [ ] Recovery-time and failure-budget tracking
- [ ] Audit-friendly ADR enforcement in CI

## 7) Profile-Specific Mandatory Add-ons

Software:

- [ ] `BASICS-SW-011` Durable mutation handling
- [ ] `BASICS-SW-020` Deterministic conflict detection
- [ ] `BASICS-SW-033` Security notes workflow for exceptions

Hardware:

- [ ] `BASICS-HW-011` Manufacturing + field test plans with pass criteria
- [ ] `BASICS-HW-003` Serviceability policy and spare strategy
- [ ] `BASICS-HW-004` Revision-to-test traceability matrix

Firmware:

- [ ] `BASICS-FW-001` Protect/detect/recover controls evidenced
- [ ] `BASICS-FW-010` Signed metadata/manifest update flow
- [ ] `BASICS-FW-020` Role-separated trust model
- [ ] `BASICS-FW-014` Recovery and rollback tests

## 8) Assessment Summary

- Mandatory pass count:
- Mandatory fail count:
- Optional maturity average:
- Blocking issues:
- Recommended target date:
- Assessor:
- Review authority:

