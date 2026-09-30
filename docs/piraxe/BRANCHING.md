# PIRAXE Fork Branching and Commit Policy

Last updated: 2026-09-28
Build-step workflow added: 2026-09-29

## Branch roles

- `main` is the stable integration branch and tracks `origin/main`.
- Do not perform planned implementation directly on `main`.
- Use one focused branch for one roadmap phase or independently reviewable logical change.
- Record the active branch in both `STATUS.md` and the active plan.

## Naming

Use lowercase, hyphenated names:

- `docs/<topic>` for documentation-only changes.
- `research/<topic>` for audits and design work that should not alter runtime behavior.
- `feat/<topic>` for new behavior.
- `fix/<topic>` for corrections.
- `test/<topic>` for test-only changes.
- `refactor/<topic>` for behavior-preserving structural changes.
- `release/<topic>` for release preparation.

Planned branch names are listed in `ROADMAP.md`. Change one only by updating the roadmap, status, and active plan together.

## Before editing

1. Read the mandatory project-memory files.
2. Inspect `git status --short --branch`.
3. Inspect the current branch and its upstream.
4. Inspect existing diffs before touching overlapping files.
5. Confirm the active plan names the same branch.
6. If starting a new logical change, branch from the intended accepted baseline.
7. If unrelated uncommitted changes exist, do not move, stash, discard, or absorb them without reconciling ownership.

## Commit discipline

- A commit must represent one coherent change.
- Use clear imperative subjects with a conventional prefix when practical: `docs:`, `feat:`, `fix:`, `test:`, `refactor:`, or `chore:`.
- Include tests with behavior changes when feasible.
- Do not commit secrets, generated credentials, local environment files, or unrelated formatting churn.
- Do not mark documentation or status as complete before validation.
- Do not commit, push, merge, rebase, or open a pull request unless the user's request authorizes it.

For step closeout, follow [BUILD_WORKFLOW.md](BUILD_WORKFLOW.md) and the repository-local commit skill. An explicit `$commit` request to finish the active step authorizes that scoped local commit; merely discovering the skill does not. Push requires explicit current or durably recorded user authorization for the exact fork/branch. Record its provenance, not a self-issued permission. Existing authorization need not be requested again.

Require current independent specification, implementation and staged-closeout reviews. Stage only reviewed owned paths/hunks. Unrelated staged changes or unknown overlapping ownership block closeout; do not unstage, stash or absorb them. Archive the complete step and clear the active slot in the same verified commit. A failed push leaves the step committed locally with delivery pending, not incomplete or ready for a duplicate commit. Completing a step does not authorize a merge or establish a new accepted base branch.

## Suggested phase branches

| Work | Branch |
|---|---|
| Durable memory setup | `docs/piraxe-project-context` |
| Architecture and API audit | `research/piraxe-architecture-audit` |
| PIRAXE workflow foundation | `feat/piraxe-workflow-foundation` |
| Nano Banana provider | `feat/nano-banana-provider` |
| Paipu BK provider | `feat/paipu-bk-provider` |
| End-to-end integration | `feat/piraxe-end-to-end` |
| Initial release hardening | `release/piraxe-initial` |

## Pull request and merge rule

- Keep each pull request focused on one logical outcome.
- Summarize the plan, important decisions, validation results, and known limitations.
- Merge only after the plan's acceptance criteria pass or the remaining exception is explicitly accepted.
- After merge, update `STATUS.md` on the next active branch so it does not point to finished work.

## Upstream synchronization

The fork currently has only `origin` configured. Do not invent an upstream-sync operation during unrelated work. Phase 1 must decide whether to add the original OpenMontage repository as `upstream`, which branches to track, and how to resolve fork-specific conflicts.
