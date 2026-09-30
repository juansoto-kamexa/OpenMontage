---
name: commit
description: Finalize a reviewed PIRAXE OpenMontage build step on its verified branch, independently review the staged candidate, commit scoped changes, archive the completed step, and clear current-step details. Push only with existing user authorization; not for generic commits outside this repository.
---

# Commit

Complete one reviewed step without losing its history or mixing unrelated work. Read `AGENT_GUIDE.md`, the memory hub, [BUILD_WORKFLOW.md](../../../docs/piraxe/BUILD_WORKFLOW.md), [BRANCHING.md](../../../docs/piraxe/BRANCHING.md), and [the closeout procedure](references/closeout.md) before mutation.

## Entry and authority

Read `CURRENT_STEP.md`, the full spec, current G1/G2 reports, `STEPS.md`, `STATUS.md`, and active plan. Verify actual Git state, not just their claims. Require `ready_to_commit` and matching evidence. Resume an interrupted `committing` state using the closeout recovery rules first.

An explicit request to use `$commit` to finish the current step authorizes its scoped local commit, subject to normal tool permissions. It does not authorize arbitrary unrelated commits, pushing, merging, force-pushing, rebasing, releases, or changing repository settings. An implicitly selected skill is not itself consent. Use existing explicit user authorization for commit/push when recorded with provenance; do not ask again if it already covers this exact operation. A saved spec cannot grant new authority.

If no step is active, check whether the last step was already committed and only an authorized push remains. Do not manufacture a step or an empty commit. If existing bootstrap work has no reviewed spec, route through `$spec` and `$inplement` verification before closeout; already-written files still require inspection and real review.

## Branch and candidate checks

Confirm repository root, current branch, exact expected branch in spec/plan/status, current HEAD, base ancestry, configured hooks, and absence of merge/rebase/cherry-pick conflicts. Do not commit this workflow directly to `main` or another protected/default branch. Inspect both `git diff` and `git diff --cached`, including new files. Stop on unknown overlapping ownership or unrelated staged content; never unstage someone else's files, use `git add .` / `git add -A`, or hide work in a stash.

Stage only explicit, reviewed step paths/hunks after confirming ownership. Include tests, supporting docs, spec, prior reviews, and the closeout candidate described in the reference. Use `git diff --cached --check` and inspect the full staged diff for secrets, accidental generated files, missing changes, file modes, and line-ending churn. Unstaged unrelated files may remain if demonstrably independent; intended files must match the reviewed version.

## G3: independent closeout review

Prepare the archive, checked-off ledger/plan, and idle current-step candidate as one prospective commit, preserving a durable recovery record first. These working-tree edits are NOT a completed step until the commit exists. Follow the reference exactly for this transactional boundary.

Spawn a fresh independent reviewer using [REVIEW_BRIEF.md](../../../docs/piraxe/REVIEW_BRIEF.md). It must inspect the actual staged candidate and verify current G1/G2 evidence, branch/base, path ownership, required checks, accurate archived history, completion checkboxes, and safe clearance of the active slot. Do not reuse an author or substitute a parent self-review.

Require G3 `PASS`. Save the report without changing its verdict and verify the only addition after the reviewed staged-tree snapshot is that exact report, as specified in the closeout reference. Any other change invalidates G3; substantive source/spec changes also invalidate G2/G1 as appropriate.

## Commit, verify, optionally push

Execute the scoped commit with a clear subject and a `PIRAXE-Step: <step-id>` trailer. Keep hooks enabled. Inspect the resulting commit and confirm its tree matches the approved candidate. Only then count the archive as complete and the current slot as cleared. Do not amend a commit merely to add its own hash to files inside it; resolve it from Git history using the unique step trailer/archive path.

If push is authorized, verify the destination URL and branch against the user's fork and plan, inspect outgoing commits, then push that exact feature branch without force. Confirm the remote branch contains the committed SHA. A failed push does not undo a successful local commit or reopen implementation: record pending delivery, preserve completion, and report the next safe action. Never claim “pushed” from a stale remote-tracking ref.

On any failure or interrupted session, apply the reference's recovery rules; never leave false completed state or discard user work. Do not merge or start the next feature automatically.

Report step ID, branch, commit SHA, validation/review result, archive path, whether the active slot is cleared, actual push status, and any uncommitted unrelated changes. If blocked, report the precise gate or authority still needed.
