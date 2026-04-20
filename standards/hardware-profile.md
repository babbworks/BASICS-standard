# BASICS Hardware Profile v0.1.1

Status: Draft v0.1.1

Firmware-specific obligations are defined in the Firmware Profile.

## 1) External Reference Index

- `REF-ISO-9001`: [ISO 9001 summary](https://www.9001council.org/iso-9001-summary.php)
- `REF-IEC-61508`: [IEC 61508 overview](https://www.intertek.com/etl/standards/iec-61508/)
- `REF-NIST-CSF2`: [NIST CSF 2.0](https://csrc.nist.gov/pubs/cswp/29/the-nist-cybersecurity-framework-csf-20/final)
- `REF-NISTIR-8259A`: [NISTIR 8259A](https://csrc.nist.gov/publications/detail/nistir/8259a/final)
- `REF-DFT-GUIDE`: [Design for Testability guidance](https://resources.altium.com/p/designing-for-testability-dft)
- `REF-DFS-GUIDE`: [Design for Serviceability guidance](https://www.fictiv.com/articles/design-for-serviceability)
- `REF-REPAIR-GUIDE`: [Repair ecosystem guidance](https://www.ifixit.com/News/111354/designing-a-repair-ecosystem-a-guide-for-oems)

## 2) Hardware Rules

### 2.1 Manufacturing and Lifecycle Control

- `BASICS-HW-001` (MUST): Hardware programs define controlled build/release processes and revision impact notes.
  Sources: `REF-ISO-9001`, `REF-IEC-61508`
- `BASICS-HW-002` (MUST): Quality nonconformances and corrective actions are traceable.
  Sources: `REF-ISO-9001`
- `BASICS-HW-003` (MUST): End-of-life policy, support horizon, and spare availability policy are published.
  Sources: `REF-ISO-9001`, `REF-REPAIR-GUIDE`
- `BASICS-HW-004` (MUST): Revision traceability links hardware revision, test evidence, and defect history.
  Sources: `REF-ISO-9001`, `REF-IEC-61508`

### 2.2 Design for Testability (DFT)

- `BASICS-HW-010` (MUST): Test access and diagnostics paths are designed for each hardware class.
  Sources: `REF-DFT-GUIDE`
- `BASICS-HW-011` (MUST): Manufacturing tests have explicit repeatable pass/fail criteria.
  Sources: `REF-DFT-GUIDE`, `REF-ISO-9001`
- `BASICS-HW-012` (MUST): Test plans define coverage scope and retest rules after repair.
  Sources: `REF-DFT-GUIDE`
- `BASICS-HW-013` (SHOULD): Field diagnostics avoid destructive teardown where feasible.
  Sources: `REF-DFT-GUIDE`, `REF-DFS-GUIDE`

### 2.3 Design for Serviceability (DFS)

- `BASICS-HW-020` (MUST): Service model documents replace/repair/refurbish/retire pathways.
  Sources: `REF-DFS-GUIDE`, `REF-REPAIR-GUIDE`
- `BASICS-HW-021` (SHOULD): High-failure components are accessible with minimal disassembly.
  Sources: `REF-DFS-GUIDE`, `REF-REPAIR-GUIDE`
- `BASICS-HW-022` (MUST): Service documentation includes diagnostic sequence, parts replacement rules, and return-to-service verification.
  Sources: `REF-DFS-GUIDE`
- `BASICS-HW-023` (SHOULD): Interfaces and parts favor maintainable standardized options when feasible.
  Sources: `REF-REPAIR-GUIDE`

### 2.4 Capability and Security Baseline

- `BASICS-HW-030` (MUST): Device capability profile includes compute/storage constraints, network assumptions, environmental tolerances, and security-relevant interfaces.
  Sources: `REF-NISTIR-8259A`
- `BASICS-HW-031` (MUST): Hardware security controls are documented across govern/identify/protect/detect/respond/recover lifecycle functions.
  Sources: `REF-NIST-CSF2`
- `BASICS-HW-032` (MUST): Threat model is updated for major hardware revisions.
  Sources: `REF-IEC-61508`, `REF-NIST-CSF2`

### 2.5 Interoperability

- `BASICS-HW-040` (MUST): Hardware modules participating in BASICS workflows declare command/event compatibility level.
  Sources: `REF-NISTIR-8259A`
- `BASICS-HW-041` (MUST): Optional modules identify themselves discretely in interface manifests.
  Sources: `REF-NISTIR-8259A`
- `BASICS-HW-042` (MUST): Module-specific deviations are registered and linked.
  Sources: `REF-ISO-9001`

