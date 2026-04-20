# BASICS Adoption Playbook

Status: Draft v0.1.1

This playbook helps teams adopt BASICS without freezing delivery.
It is designed for real codebases, mixed maturity, and constrained environments.

## 1) Adoption Outcomes

By the end of an initial adoption cycle, a team should have:

- a published BASICS conformance claim target (tier + profiles + version)
- a mapped command and event surface
- local-first behavior defined for core records
- degraded-mode behavior documented and tested
- a first conformance evidence bundle
- a deviation register for anything not yet aligned

## 2) Adoption Principles

1. Start with behavior, not rewrites.
2. Keep existing product delivery moving.
3. Conform by evidence, not by declaration.
4. Use deviations to keep velocity while preserving trust.
5. Harden iteratively through tier progression.

## 3) Which Profile Applies?

Use this fast decision table:

- CLI / API / app only -> Shared Core + Software Profile
- Physical device with software services -> Shared Core + Software + Hardware
- Device with updateable firmware -> Shared Core + Hardware + Firmware (and Software if applicable)

## 4) 30-Day Adoption Track

### Week 1: Scope and Baseline

- Pick target tier (`Core` recommended for first pass).
- Pick applicable profiles.
- Identify product owner and conformance owner.
- Run baseline against `standards/conformance-checklist.md`.
- Capture known gaps and classify as:
  - quick fix
  - medium refactor
  - deviation candidate

Deliverables:

- tier/profile target statement
- baseline checklist snapshot
- gap register

### Week 2: Interface and Record Spine

- Publish command contract draft.
- Publish event schema draft.
- Confirm local create/edit behavior for core records.
- Define compatibility policy and versioning behavior.

Deliverables:

- command surface spec
- event schema spec
- compatibility policy

### Week 3: Resilience and Evidence

- Define degraded-mode matrix (network/storage/dependency/integrity).
- Implement or document conflict comparison header behavior.
- Add minimal test coverage for degraded and offline record operations.

Deliverables:

- degraded-mode behavior matrix
- first tier test output
- conflict header declaration

### Week 4: Governance and Publication

- Add ADR index.
- Register active deviations in `standards/deviation-registry.md` format.
- Produce first conformance evidence bundle and internal review.

Deliverables:

- ADR index
- deviation entries
- conformance evidence bundle v1

## 5) 100-Day Hardening Track

### Phase A (Days 31-50): Field Readiness

- Improve deferred sync durability.
- Improve operator-visible failure and recovery messaging.
- Expand constrained-device behavioral testing.

### Phase B (Days 51-75): Security and Supply Chain

- Map secure development controls.
- Introduce SBOM generation.
- Add provenance attestations to release path.

### Phase C (Days 76-100): Industrial Readiness

- Close or justify major deviations.
- Raise automation for conformance evidence.
- Prepare publishable conformance report for Babb/partner review.

## 6) Evidence Bundle Structure

Recommended layout:

```text
conformance/
  BASICS-claim.yaml
  command-surface.md
  event-schema.md
  compatibility-policy.md
  adr-index.md
  degraded-mode-matrix.md
  test-results/
  security-notes/
  supply-chain/
```

`BASICS-claim.yaml` should include:

- product name
- BASICS version
- claimed tier
- profiles
- evidence URI
- active deviation IDs

## 7) Dirty Test Procedure (Fast Assessment)

Use this when you need a quick reality check in under one day.

1. Validate existence of:
   - command contract
   - event schema
   - local core record create/edit path
2. Run five mandatory checks:
   - offline create/edit works
   - basic degraded mode documented
   - conflict header contract defined
   - compatibility policy exists
   - claim metadata can be produced
3. Mark each control:
   - PASS
   - FAIL
   - DEVIATION NEEDED

Output:

- one-page dirty test report
- list of blocking failures
- list of deviations needed to claim initial conformance

## 8) Common Failure Modes

- Treating BASICS as doc-only governance
- Delaying command/event publication until "later"
- Calling cloud-dependent writes "offline-first"
- Hiding compatibility breaks in release notes
- Using deviations without long-lived references

## 9) Recommended First Proof Target

`workpads` remains the primary proof product for BASICS hardening.

For adjacent repositories, run a dirty test first, then choose:

- align directly to `Core`
- or file explicit deviations before claiming conformance

