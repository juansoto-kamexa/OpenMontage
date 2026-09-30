# Step 000-01-phase-0-baseline — Commit the Phase 0 project baseline

## Identity and authority

- Revision 1, 2026-09-29. Phase 0; [Plan 000](../plans/000-project-memory.md).
- User request: “commit the current files, so we can start the first feature clean.” This authorizes the current coherent Phase 0 files and a local commit, but no push, merge, or new feature work.
- Working branch: `docs/piraxe-project-context`; base: `main` at `08e2151fa02de28a5d6a312b3d575692bf147ad7`; pre-step HEAD equals base.
- No prior build-step dependency. Existing Phase 0 work and its fixture validation record are inputs, not real-project G1/G2 evidence.
- The plan's separate terminology and branch-policy discussion remains open; it need not be marked complete for a scoped local commit.

## Outcome, scope, and ownership

Produce one reviewed documentation-only local commit containing the current PIRAXE memory hub, root guidance links, three project-local build skills, this step's spec/reviews/archive, an accurate ledger/status, and an idle active-step slot. The working tree must be clean afterward. No runtime behavior, provider, pipeline, generated media, credential, push, merge, or branch switch is in scope.

At entry the index is empty. Tracked edits are `AGENTS.md`, `AGENT_GUIDE.md`, and `PROJECT_CONTEXT.md`. The untracked files are the 25 files under `.agents/skills/{spec,inplement,commit}/` and `docs/piraxe/` shown by `git ls-files --others --exclude-standard` on 2026-09-29. Plan 000 describes those exact surfaces; the user's “current files” request includes them. No other owner or overlapping edit is evident. Recheck the inventory before staging.

## Verified baseline and design

- `AGENTS.md` routes to `AGENT_GUIDE.md`; the working edit adds fork context while preserving that first action.
- `AGENT_GUIDE.md` is the upstream contract; the working edit adds a PIRAXE overlay and memory link without modifying production pipeline rules.
- `PROJECT_CONTEXT.md` remains the upstream architecture source and links to fork-specific memory.
- `docs/piraxe/` and the three local skills exist only in the working tree at entry. They define memory and reviewed build steps. The earlier disposable-repository skill validation is historical evidence; this real candidate still needs fresh G1/G2/G3 reviews.
- Application code, manifests, schemas, and tests are unchanged. Public API, configuration, cost, retry, credential, and provider contracts are not applicable to this documentation step.

## Requirements and interfaces

| ID | Observable invariant |
|---|---|
| R-01 | Root routing and upstream architecture context remain intact, with a clear PIRAXE memory entry point. |
| R-02 | Memory identifies phase, branch, plan, next action, decisions, and boundaries without claiming planned providers exist. |
| R-03 | Local Spec, Inplement, and Commit skills give implementable G1/G2/G3 review and recovery instructions without certifying prior work. |
| R-04 | Only owned documentation/instruction files are committed; no secrets, generated files, or application code; local links resolve. |
| R-05 | Closeout preserves complete step history, checks only this ledger entry, clears the active slot only in the committed candidate, and states delivery truthfully. |
| R-06 | The local commit has the approved staged tree, expected parent/branch, `PIRAXE-Step: 000-01-phase-0-baseline` trailer, and a clean working tree. |

Markdown paths and the `CURRENT_STEP.md` state labels are the only changed persistent interfaces. They follow `BUILD_WORKFLOW.md`; no schema migration or runtime caller is involved. Recovery follows the commit skill's `closeout.md` journal, scoped restoration, and no duplicate commit rule. The main operational risk is inaccurate guidance or broken links.

## Files and ordered tasks

Allowed paths: entry inventory plus `docs/piraxe/specs/000-01-phase-0-baseline.md`, `docs/piraxe/reviews/000-01-phase-0-baseline-G{1,2,3}-a01.md`, and `docs/piraxe/completed/000-01-phase-0-baseline.md`. Review retries may add higher attempt suffixes. The status, plan, ledger, and current-step files are owned bookkeeping. No other path or hunk may be staged.

| Task | Output | Due | Exit |
|---|---|---|---|
| T-01 | Reconcile and inspect complete Phase 0 candidate. | G2 | R-01–R-04 are evidenced. |
| T-02 | Validate skill metadata, links, scope, and secret hygiene; record commands/results. | G2 | AC-01–AC-03 pass. |
| T-03 | Obtain fresh G1 and G2 independent reports. | G1/G2 | Current PASS reports. |
| T-04 | Journal, archive, stage explicit paths, obtain G3. | G3 | Approved staged tree plus exact G3 receipt only. |
| T-05 | Commit and verify. | Post-commit | R-05–R-06 pass. |

No shared-file edits may occur while a reviewer checks a snapshot.

## Acceptance and validation

| ID | Requirements | Due | Assertion and method |
|---|---|---|---|
| AC-01 | R-01,R-02 | G2 | Inspect root diff and memory documents: mandatory guide routing, agreeing branch/phase/plan, providers still planned. |
| AC-02 | R-03 | G2 | Run bundled `quick_validate.py` for each skill, parse each `agents/openai.yaml`, inspect lifecycle/recovery instructions and prior fixture evidence/limits. |
| AC-03 | R-04 | G2 | `git status --short`, `git diff --name-status`, and `git ls-files --others --exclude-standard` contain only owned paths; owned Markdown links resolve; candidate has no credentials or generated assets. |
| AC-04 | R-05 | G3 | Reviewer inspects actual `git write-tree` candidate, full archive, checked ledger, plan/status, idle slot, authority and recovery journal. `git diff --cached --check` exits zero. |
| AC-05 | R-06 | Post-commit | `git show` verifies parent/tree/trailer, and `git status --porcelain` is empty. No push assertion. |

Commands run at repository root on this offline checkout. Resolve relative Markdown links against each file, ignoring external URLs, anchors and code examples. Skill validator is the installed bundled `quick_validate.py`. No paid/live services or generated runtime outputs are needed. G3 and post-commit checks remain explicitly pending at G2; feature behavior is not deferred.

## Reviews, release, recovery, handoff

G1, G2, and G3 require fresh non-author agents using `REVIEW_BRIEF.md` and `BUILD_WORKFLOW.md`. G1 snapshots spec/instructions/initial inventory/base; planned progress fields may change. G2 snapshots all implementation documentation, with only future archive/G3 and live progress bookkeeping excluded. Content/path/mode/branch/HEAD/contract changes invalidate affected gates. G3 reviews the staged tree; only its exact receipt may then be added.

Before closeout edits, create the Git-local recovery journal in `closeout.md`. Failed closeout retains reports and restores only prospective owned completion metadata. Commit subject: `docs: establish PIRAXE project baseline`; trailer: `PIRAXE-Step: 000-01-phase-0-baseline`. Archive: `docs/piraxe/completed/000-01-phase-0-baseline.md`. This satisfies the Phase 0 documentation baseline and local commit; terminology review, branch integration, and Phase 1 research remain separate. Do not start them automatically.

Sources inspected 2026-09-29: root guidance, `docs/piraxe/` memory/workflow/plan files, three local skills and their spec/closeout references, and Git branch/status/history/remotes. No essential unknown blocks this documentation commit.
