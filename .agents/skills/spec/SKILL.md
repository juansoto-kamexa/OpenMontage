---
name: spec
description: Write or revise an implementation-ready specification for a PIRAXE OpenMontage build step, with measurable acceptance criteria and a required independent-agent review. Use when planning the next feature or refining the active step; does not implement application code.
---

# Spec

Turn the requested build step into a contract another agent can execute without the original chat. This skill belongs only to this OpenMontage repository.

## Read and reconcile

1. Read the repository's `AGENT_GUIDE.md` first, then follow `docs/piraxe/README.md`.
2. Read [BUILD_WORKFLOW.md](../../../docs/piraxe/BUILD_WORKFLOW.md), [CURRENT_STEP.md](../../../docs/piraxe/CURRENT_STEP.md), the active phase plan, and relevant architecture/decision records completely.
3. Verify repository root, branch, HEAD, remotes, tracked and untracked changes, and existing staged content. Record pre-existing changes and ownership, without capturing secret values.
4. Resume the active step if it matches the request. Do not overwrite a different unfinished step. Ask for a decision if the request would replace it; preserve its spec, progress, and reviews if it is explicitly superseded.
5. With no active step, choose the next dependency-ready step within the user's authorized scope and existing plan. Allocate a stable `PPP-NN-slug` identifier, such as `001-01-provider-contract-audit`; never reuse an identifier. Do not silently jump roadmap phases.

## Produce the executable specification

Read and adapt [the specification template](assets/step-spec-template.md). Save it at `docs/piraxe/specs/<step-id>.md`. Create that directory when first needed. Keep this file as the stable contract; put task completion, commands/results, blockers, and reviews in `CURRENT_STEP.md` until archival.

Inspect the actual source files, tests, schemas, configuration, and tool contracts before defining changes. Cite real repository paths and authoritative provider documentation. Preserve OpenMontage's registry/selectors, checkpoints, costs, and declarative orchestration where they fit. PIRAXE remains the governing creative workflow; Paipu BK and Nano Banana are planned integrations, not assumed existing capabilities.

Fill every applicable template section with concrete details:

- Exact outcome, observable before/after behavior, scope, and exclusions.
- Branch/base commit, dependency evidence, expected files and symbols, and pre-existing work excluded from this step.
- Numbered requirements, data/API contracts, validation rules, state transitions, failure/retry/cancellation behavior, compatibility, security, costs, and configuration as relevant.
- Ordered tasks with inputs, outputs, dependencies, and testable exit conditions; include documentation and integration work, not just code.
- Acceptance-to-test mapping, actual commands, working directory, fixtures, assertions, negative cases, regression coverage, and environment assumptions.
- Review gates, explicit human decisions where needed, rollout/rollback, completion record, and next-step prerequisites.

Be detailed about what materially constrains implementation; use `Not applicable — <reason>` for irrelevant sections instead of inventing requirements. No vague “handle errors,” “add tests,” or “ensure it works” as acceptance criteria. Do not fabricate API names, endpoints, pricing, model identifiers, or capabilities. A missing essential contract blocks that implementation step; specify a separate bounded research step if appropriate.

Populate `CURRENT_STEP.md` with state `drafting`, links, branch/base, exact task checklist, acceptance checklist, initial change ownership, requested commit/push authority, and next action. Add the step as unchecked in `STEPS.md` and reference it from the active phase plan. Synchronize `STATUS.md` without declaring the phase complete.

## G1: independent specification review

Set state `spec_review`. Spawn a new isolated reviewer using the shared workflow's review protocol and [review brief](../../../docs/piraxe/REVIEW_BRIEF.md). Give raw requirements, project instructions, proposed spec, source paths, and the G1 checklist, not your conclusion that the spec is complete.

The reviewer must verify feasibility against actual files, requirement/test coverage, unambiguous contracts, dependencies, correct branch/scope, and absence of unresolved blocking decisions. Save its real report under `docs/piraxe/reviews/`. Fix findings and obtain a new review for the new snapshot; retain prior reports.

Only a valid G1 `PASS` permits `ready_to_implement`. No reviewer, insufficient evidence, or unresolved required finding means `blocked`, with a specific next action. Never simulate a second agent or approve your own spec. A separate human approval is required only when requested by the user or the accepted plan; it cannot be inferred from reviewer approval.

## Handoff

Report the step ID, spec path, branch, G1 verdict, unresolved decisions, and exact next action. Do not implement merely because the spec passed. Continue into `$inplement` only if the user's current request already authorizes implementation.
