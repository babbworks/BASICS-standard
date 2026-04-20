# BASICS Deviation Registry v0.1.1

Status: Draft v0.1.1

## 0) External Reference Index

- `REF-ISO-42030`: [ISO/IEC/IEEE 42030:2019](https://www.iso.org/standard/73436.html)
- `REF-ISO-15288`: [ISO/IEC/IEEE 15288:2023](https://www.iso.org/standard/81702.html)
- `REF-SEMVER`: [Semantic Versioning 2.0.0](https://semver.org/)

## 1) Purpose

The BASICS Deviation Registry records approved or pending deviations from normative BASICS requirements.
It provides long-lived references so teams can explain design choices without weakening interoperability trust.

## 2) Policy

- `BASICS-DEV-POL-001` (MUST): All normative deviations are registered.
  Sources: `REF-ISO-42030`, `REF-ISO-15288`
- `BASICS-DEV-POL-002` (MUST): Every registered deviation has a stable long-lived URI.
  Sources: `REF-SEMVER`, `REF-ISO-42030`
- `BASICS-DEV-POL-003` (MUST): Registry entries remain historically accessible after supersession.
  Sources: `REF-ISO-15288`, `REF-SEMVER`
- `BASICS-DEV-POL-004` (MUST): Deviation acceptance follows BASICS proposal/review lifecycle.
  Sources: `REF-ISO-42030`, `REF-ISO-15288`

## 3) Entry Schema

Each deviation entry MUST include:

- Deviation ID (immutable)
- Status (`proposed`, `accepted`, `rejected`, `superseded`, `withdrawn`)
- Affected BASICS rule IDs
- Short summary
- Detailed rationale
- Semantic compatibility impact
- Risk notes
- Mitigation notes
- Decision date
- Decision authority
- Stable URI
- Change history

## 4) Deviation ID Format

Recommended format:

`BASICS-DEV-YYYY-NNN`

Example:

`BASICS-DEV-2026-004`

## 5) Publishing and Referencing

- Tool documentation MUST reference deviation IDs for non-standard behavior.
- Public conformance claims MUST include active accepted deviations.
- Rejected deviations MUST remain visible to preserve review history.

## 6) Example Entry (Template)

```text
Deviation ID: BASICS-DEV-2026-004
Status: accepted
Affected Rules: BASICS-SC-5.1, BASICS-SW-3.2
Summary: Alternate event envelope for constrained link mode
Rationale: Preserves record integrity in 1KB transport envelope
Compatibility Impact: Requires adapter for canonical event consumers
Risk Notes: Medium risk of parser mismatch without adapter
Mitigation: Canonical adapter included and tested
Decision Date: 2026-04-20
Decision Authority: Babb + Partner Review Board
Stable URI: https://standards.babb.dev/deviations/BASICS-DEV-2026-004
History: v1 accepted
```

