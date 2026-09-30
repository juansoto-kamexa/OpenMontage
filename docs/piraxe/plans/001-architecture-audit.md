# Plan 001 — Architecture and Provider Contract Audit

- Status: Proposed
- Roadmap phase: 1
- Base branch: `main` after Phase 0 acceptance
- Working branch: `research/piraxe-architecture-audit`
- Owner: Unassigned
- Last updated: 2026-09-28

## Outcome

Produce a verified, implementation-ready design for the PIRAXE workflow, Nano Banana provider, and Paipu BK provider without changing runtime behavior.

## Scope

- Map relevant OpenMontage contracts and tests.
- Verify provider APIs from authoritative documentation.
- Decide exact pipeline stages, artifacts, adapters, configuration, registration, and validation seams.
- Produce bounded implementation plans for Phases 2–4.

## Non-goals

- Writing provider adapters.
- Creating production pipeline files.
- Adding credentials or making paid generation calls.
- Changing Backlot before artifact requirements are known.

## Dependencies and assumptions

- Phase 0 is accepted and available on the base branch.
- Authoritative Paipu BK documentation can be obtained.
- The intended Nano Banana API/model surface can be identified.

## Expected change surface

- `docs/piraxe/ARCHITECTURE.md`
- `docs/piraxe/DECISIONS.md`
- `docs/piraxe/ROADMAP.md`
- Additional phase plans under `docs/piraxe/plans/`
- No runtime code

## Steps

- [ ] Audit representative image and video provider implementations.
- [ ] Audit image/video selector behavior and registry discovery.
- [ ] Audit configuration, availability, cost, and error conventions.
- [ ] Audit pipeline, artifact, checkpoint, and Backlot contracts.
- [ ] Map PIRAXE stages against existing artifacts and identify required schema work.
- [ ] Verify Paipu BK API and operational constraints.
- [ ] Verify Nano Banana API and operational constraints.
- [ ] Decide upstream remote and synchronization policy.
- [ ] Produce implementation-ready plans for Phases 2–4.

## Acceptance criteria

- [ ] Every proposed runtime file and contract change is enumerated.
- [ ] Provider requests, responses, async behavior, authentication, cost, limits, and errors are verified.
- [ ] Pipeline stages, artifacts, and approval gates are explicitly mapped.
- [ ] Test strategy covers success, unavailable, invalid-input, provider-failure, timeout, and cost paths.
- [ ] No unresolved architectural assumption is presented as fact.

## Validation

| Check | Command or method | Result |
|---|---|---|
| Repository audit | Cross-reference paths and symbols | Not started |
| Provider facts | Cite authoritative documentation | Not started |
| Plan completeness | Review against Phase 1 acceptance criteria | Not started |

## Progress log

- 2026-09-28 — Placeholder plan created during Phase 0.

## Decisions and discoveries

- None yet.

## Handoff

- Current state: Proposed only.
- Blocker: Phase 0 acceptance and provider documentation.
- Exact next action: Start only after Phase 0 is accepted and the branch is created from the accepted baseline.
