# PIRAXE Fork Project Memory

This directory is the durable, repository-owned memory for the PIRAXE fork of OpenMontage. It exists so a new agent can understand the whole project, the current build phase, the active branch, prior decisions, and the next safe action without relying on chat history.

It supplements OpenMontage's existing documentation. It does not replace `AGENT_GUIDE.md`, `PROJECT_CONTEXT.md`, or `docs/ARCHITECTURE.md`.

## Mandatory reading order

Before planning or changing this fork, read:

1. `AGENT_GUIDE.md` — mandatory OpenMontage routing and operating contract.
2. `PROJECT_CONTEXT.md` — verified upstream architecture and conventions.
3. `docs/piraxe/VISION.md` — PIRAXE goals, boundaries, and definition of success.
4. `docs/piraxe/ARCHITECTURE.md` — current-system map and intended fork overlay.
5. `docs/piraxe/STATUS.md` — current phase, branch, working state, and immediate next action.
6. `docs/piraxe/ROADMAP.md` — ordered build phases and acceptance gates.
7. The active file under `docs/piraxe/plans/` named by `STATUS.md`.
8. `docs/piraxe/DECISIONS.md` when the task touches an existing architectural or workflow decision.
9. `docs/piraxe/BRANCHING.md` before creating a branch, committing, rebasing, merging, or opening a pull request.
10. [BUILD_WORKFLOW.md](BUILD_WORKFLOW.md) and [CURRENT_STEP.md](CURRENT_STEP.md) for build-step specification, implementation, review or closeout. Before trusting an idle slot, check for interrupted closeout journals as described by that workflow and the commit procedure.

## What each file owns

| File | Source of truth for |
|---|---|
| `VISION.md` | Mission, goals, non-goals, hard constraints, final success criteria |
| `ARCHITECTURE.md` | Verified current architecture, intended extension points, open technical questions |
| `ROADMAP.md` | Build order, milestones, dependencies, phase acceptance criteria |
| `STATUS.md` | Live handoff: current branch, active plan, completed work, next action, blockers |
| `DECISIONS.md` | Accepted and superseded decisions with rationale and consequences |
| `BRANCHING.md` | Branch roles, naming, commit discipline, merge safety |
| `plans/*.md` | Executable plan for one bounded milestone or change |
| `BUILD_WORKFLOW.md` | Step lifecycle, mandatory independent review and evidence rules |
| `CURRENT_STEP.md` | Single live step with task/acceptance evidence and next action |
| `STEPS.md` | Permanent step ledger with completion checkboxes and archive links |
| `specs/`, `reviews/`, `completed/` | Detailed contracts, real agent reviews and completed execution history; created as needed |

## Project-local build skills

- `$spec`: define one detailed step and obtain independent G1 specification review.
- `$inplement`: implement that current spec, validate it and obtain independent G2 review. The spelling is intentional.
- `$commit`: verify branch and authority, obtain independent G3 staged review, commit the complete step with its archive, and clear the active slot. Push only if already authorized.

Their definitions live only in this repository's `.agents/skills/`. The [spec template](../../.agents/skills/spec/assets/step-spec-template.md) covers requirements, interfaces, file-level work, task dependencies, acceptance tests, failures, reviews and recovery. [REVIEW_BRIEF.md](REVIEW_BRIEF.md) specifies the fresh-reviewer contract. The active slot is cleared by archival, not by deleting history or marking unfinished work done.

## Start-of-work protocol

Every agent beginning implementation or planning work must:

1. Follow `AGENT_GUIDE.md` routing first.
2. Read the files listed above.
3. Run read-only Git checks for the current branch, working-tree status, remotes, and recent history.
4. Confirm that the current branch matches the active plan.
5. Inspect existing changes before editing; never overwrite or absorb unrelated work silently.
6. State which roadmap phase and plan the task belongs to.
7. Separate verified repository facts from proposed design.

If the branch, plan, and working tree disagree, reconcile them before implementation. Do not guess which work belongs where.

## End-of-work protocol

Before handing work to another agent or ending a milestone:

1. Update the active plan's progress and validation results.
2. Update `STATUS.md` with what changed, what remains, and the exact next action.
3. Add decisions to `DECISIONS.md` when the implementation settled a meaningful choice.
4. Update `ARCHITECTURE.md` when inspection or implementation changes the verified system map.
5. Record validation commands and their outcomes.
6. Confirm that the diff contains only the intended logical change.
7. Commit, push, merge, or open a pull request only when the user's request authorizes that action.

## Documentation rules

- Write verified facts as facts and label proposals or assumptions explicitly.
- Keep `STATUS.md` concise and current; history belongs in Git and `DECISIONS.md`.
- Do not put secrets, tokens, or credentials in these files.
- Do not mark a milestone complete until its acceptance criteria and validation checks pass.
- If validation fails, fix it or record the blocker before advancing the roadmap.
- When a decision is replaced, keep the old entry and mark it `Superseded` with a link to the replacement.
