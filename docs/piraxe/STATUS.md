# PIRAXE Fork Status

Last updated: 2026-09-30

## Current position

- Current phase: Phase 0 — Durable project memory baseline in prospective local closeout; terminology/branch-policy review remains open.
- Current branch: `docs/piraxe-project-context`.
- Base branch: `main` tracking `origin/main`.
- Active plan: `docs/piraxe/plans/000-project-memory.md`.
- Active build-step slot: [CURRENT_STEP.md](CURRENT_STEP.md), prospectively `idle` with the [step archive](completed/000-01-phase-0-baseline.md); this is effective only after G3 PASS and a verified local commit.
- Application-code status: untouched by Phase 0.

## Repository state at handoff

- Fork remote: `origin` -> `https://github.com/juansoto-kamexa/OpenMontage.git`.
- Default branch: `main`.
- Separate `upstream` remote: not configured.
- The root `AGENTS.md` routes agents to `AGENT_GUIDE.md`.
- `AGENT_GUIDE.md` contains the PIRAXE fork mandate in addition to the upstream OpenMontage contract.
- OpenMontage's existing `PROJECT_CONTEXT.md` remains the source of truth for current upstream architecture.
- `docs/piraxe/` now owns fork-specific durable memory and planning.
- Repository-local `spec`, `inplement`, and `commit` skills now define detailed steps, fresh-agent G1/G2/G3 reviews and recoverable completion archives. No global skill installation was made.

## Completed

- Created the local fork workspace and cloned the user's fork.
- Preserved OpenMontage's mandatory `AGENT_GUIDE.md` routing.
- Recorded PIRAXE as the governing creative workflow.
- Recorded Paipu BK and Nano Banana as planned provider integrations.
- Moved the documentation work off `main` to `docs/piraxe-project-context`.
- Established vision, architecture overlay, roadmap, decision log, branching policy, and executable-plan structure.
- Created the three build skills, detailed spec template, shared lifecycle/reviewer contract, active-step placeholder and permanent step ledger.

## Validation and closeout

- Review the Phase 0 documentation for desired terminology and branch policy before phase acceptance.
- Local documentation links have been validated successfully.
- The new change set is instructions, planning documents and skill metadata only; no application code changed.
- All three skill manifests, local Markdown links and UI metadata checks pass. Independent instruction reviews and a disposable-repository G1/G2/G3/commit/interruption-resume exercise passed. The observed gate-timing ambiguity was clarified and independently reviewed. See the [validation record](reviews/2026-09-29-skill-validation.md) for tested versions, evidence and limits.
- The user requested a scoped local commit. G1/G2 attempt 03 passed; G3 attempt 01 failed and was recovered. G3 attempt 02 and actual commit verification remain pending at this prospective candidate.

## Exact next action

Review the exact staged [Phase 0 baseline archive](completed/000-01-phase-0-baseline.md) at G3, then make and verify the user's requested local commit. After verified completion, review terminology/branch policy and decide branch integration before Phase 1. No push or merge is authorized by the current request.

After Phase 0 is accepted, begin Phase 1 on `research/piraxe-architecture-audit` from the accepted `main` baseline.

## Open questions and blockers

- Obtain or identify the authoritative Paipu BK API documentation before implementation planning is finalized.
- Confirm which official Nano Banana API/model surface and authentication path the fork will support.
- Decide whether to configure the original `calesthio/OpenMontage` repository as `upstream` and how often to sync it.
- Decide whether phase branches will be merged through pull requests only or may also be merged locally for solo work.
- Determine the exact PIRAXE stage and artifact mapping during Phase 1.

## Handoff rule

Any agent ending a work session must update this file. Keep it limited to current state and immediate next steps; put durable rationale in `DECISIONS.md` and detailed execution history in the active plan.
