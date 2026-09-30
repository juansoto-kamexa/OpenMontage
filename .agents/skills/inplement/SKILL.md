---
name: inplement
description: Implement the current independently reviewed PIRAXE OpenMontage build step, run its acceptance checks, and obtain an isolated-agent implementation review. Use for authorized feature work against the active spec, not for planning-only or commit-only requests.
---

# Inplement

The spelling `inplement` is intentional: it preserves the project's requested skill name. Implement one current step, not the entire roadmap.

## Verify entry conditions

1. Read `AGENT_GUIDE.md`, follow `docs/piraxe/README.md`, and read [BUILD_WORKFLOW.md](../../../docs/piraxe/BUILD_WORKFLOW.md).
2. Read [CURRENT_STEP.md](../../../docs/piraxe/CURRENT_STEP.md), its complete spec, active phase plan, review reports, and relevant source/tests. Do not infer context from a previous chat.
3. Verify the Git root, named non-default working branch, base/HEAD, staged and unstaged diffs, and untracked files. Preserve pre-existing work. If the expected branch differs, reconcile ownership before switching; do not carry dirty changes to another branch silently.
4. Require implementation authorization, satisfied dependencies, a current G1 `PASS`, and any required human decision. `idle` or a missing/inadequate spec routes to `$spec` within the authorized scope; do not invent a passed gate.
5. Resume `implementing` or `implementation_review` from saved evidence. Recheck old evidence after changes. A `ready_to_commit` step with no new implementation request should be handed to `$commit`, not rewritten.

## Implement and verify

Set `CURRENT_STEP.md` to `implementing`. Follow the spec's task order and acceptance IDs. Load applicable OpenMontage domain instructions before changing their systems.

- Deliver the smallest coherent change that satisfies the reviewed contract. Preserve existing pipelines, public behavior, and unrelated user edits.
- Keep creative decisions in PIRAXE workflow/artifacts; keep provider-specific API mechanics in existing adapter/selector conventions. Do not add a second orchestration engine or registry by accident.
- Add meaningful tests for success and failure paths, using existing frameworks. Use mocks/fixtures for provider calls by default; live paid requests need explicit authorization and a budget.
- Verify current official API contracts before provider implementation. Never guess Paipu BK endpoints or Nano Banana model/authentication details.
- Keep secrets in established local credential mechanisms, not source, specs, logs, reports, or snapshots. Redact error evidence appropriately.
- Record each task's actual changed paths, checks, command outputs/exit codes, limitations, and next action in `CURRENT_STEP.md`. A checkbox means its stated exit condition was verified, not merely that code was written.
- If a change affects architecture or decisions, update those durable records. Keep the phase plan and `STATUS.md` aligned.

If scope, acceptance, dependency, API contract, or branch/base must change, revise the spec and return to G1 before implementing that new scope. Do not weaken criteria to make a failing implementation pass. Record an unrelated baseline failure separately with reproduction evidence; it cannot excuse a failing required acceptance criterion.

## G2: independent implementation review

Run all required implementation checks before review; record `not run` with its reason instead of `PASS` when unavailable. Resolve required test failures before claiming readiness. Keep explicitly scheduled G3 and post-commit checks pending: the staged closeout and resulting commit cannot be verified before they exist. This deferral is for closeout/delivery verification, not for unfinished feature behavior or its tests.

Set state `implementation_review`. Freeze the exact implementation snapshot described by the shared workflow. Spawn a fresh, non-author reviewer using [REVIEW_BRIEF.md](../../../docs/piraxe/REVIEW_BRIEF.md). Supply the spec, G1 report, all changed/new/deleted files, relevant baseline source, and raw test evidence.

The reviewer independently inspects the implementation against every requirement and acceptance criterion, runs safe relevant checks, examines negative/regression cases, and checks for missed integration or documentation. A green test run alone is not proof of requirement coverage. The reviewer must not edit the implementation it is judging.

Save the real report. Fix required findings, rerun affected checks, capture a fresh snapshot, and spawn a fresh review attempt. No advisory production-review auto-pass applies. If the reviewer is unavailable or a required check cannot run, leave the step `blocked`, not “complete with warnings.”

Only a current G2 `PASS`, all mandatory implementation tasks and acceptance checks due by G2 satisfied, and no unresolved required finding permit `ready_to_commit`. Explicitly list later G3/post-commit checks as pending, never passed. Update `STATUS.md` and the plan with readiness; leave the step's completion checkbox in `STEPS.md` unchecked.

## Handoff or authorized continuation

Summarize changed behavior, actual validations, reviewer verdict, limitations, and next command. Do not clear `CURRENT_STEP.md`, archive as completed, or declare completion before `$commit` succeeds. If the user's task explicitly includes committing or pushing as the next step, continue through `$commit` under that authority; otherwise hand off without committing.
