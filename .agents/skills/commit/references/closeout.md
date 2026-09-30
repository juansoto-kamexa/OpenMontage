# Transactional Step Closeout

Read with the commit skill. No command below authorizes unrelated Git changes. Use explicit paths, preserve the initial index and user edits, and respect the host's filesystem/network approvals.

## 1. Preflight and recovery journal

Before trusting an idle current-step slot, check for an interrupted attempt under the checkout-local path returned by `git rev-parse --git-path piraxe-closeout`. Inspect any unresolved journal and follow section 5 before new work. Do not start simultaneous closeouts in one checkout.

Check branch/HEAD/base, user authority, all G1/G2 evidence and snapshots, relevant tests, path ownership, existing staged content, Git operation/conflict state, and configured hooks. Unrelated staged content or overlapping unknown edits are blockers. Don't clear it to make preflight pass. Record any pre-existing owned staged hunks so failure recovery preserves them.

Create a recovery record at the resolved Git-local `piraxe-closeout/<step-id>/` path BEFORE modifying completion metadata. It is local transaction state, not a tracked source file or secret store. Record:

- Step ID, attempt number, branch, exact pre-commit HEAD/base, intended trailer/subject and archive/report paths.
- Verified commit/push authority and exact intended remote/destination.
- Original contents/existence of just the closeout metadata files this attempt will change: current-step, ledger, phase plan, status and new archive.
- Their original index entries (path, mode, blob ID or absent), initial Git status, and the owned path/hunk allowlist. Store only necessary non-secret project metadata.
- G1/G2 report paths and snapshot evidence; transaction state `prepared`.

Use file-edit tools to save this record. If local recovery storage cannot be written, stop before clearing anything and request the normal filesystem permission. A Git object or chat message alone is not sufficient crash-recovery state.

## 2. Prepare one closeout candidate

Set the active state to `committing` during preparation. Construct `docs/piraxe/completed/<step-id>.md` containing:

- Step identity, spec path/revision, phase, branch/base and original authorized outcome.
- The complete previous active-step execution log, checked tasks, every acceptance result, validation commands/outcomes, all review attempts, decisions/deviations and remaining non-blocking limitations. Preserve history, not just a summary saying “done.”
- Links to current G1/G2 and the predetermined new G3 attempt report. The G3 link may be pending until receipt attachment.
- “Completion is effective only when this record is in a verified commit with trailer `PIRAXE-Step: <step-id>`.” Do not claim a future SHA or a future push.
- Next-step prerequisites and which phase-level criteria remain unfinished.

Mark only this step's `STEPS.md` checkbox complete and update its archive link. Tick corresponding phase-plan items only when their actual criteria are met; do not complete a whole phase merely because a step ended. Update `STATUS.md` with the new local state and next action; use “delivery not yet verified,” not “pushed.”

Replace `CURRENT_STEP.md` with a small `idle` candidate linking the archive and next action, removing old detailed tasks only because their full record is now in the candidate archive. Keep the spec and every prior review. Record in the local journal that these are prospective completion changes, not committed facts.

Stage only explicitly owned paths/hunks including the complete step implementation/tests/docs and closeout files. Do not stage the local recovery journal. Inspect the staged diff and run `git diff --cached --check`. Verify no intended change remains unstaged and no extra path or hunk is staged. Use `git diff --exit-code -- <owned paths>` to detect index/working-tree mismatches where appropriate. Inspect new files explicitly.

## 3. G3 and the non-circular receipt

Use `git write-tree` to capture the candidate's exact staged-tree ID; save it in the journal. This includes the archive, cleared active slot and completion checkboxes, but does not yet include the new G3 report. Give the reviewer that ID and the full spec/G1/G2 evidence. Freeze all edits while it reviews the staged candidate, not only the working copy.

If the result is FAIL or BLOCKED, save the report and restore the pre-closeout active metadata as described in section 5. Repair the actual issue and obtain new relevant reviews. Do not leave the slot idle awaiting a failed review.

If PASS, preserve the reviewer's report verbatim at the predetermined G3 path. Stage that single receipt. Create a second staged-tree ID. Compare the two trees: the ONLY permitted difference is addition of that exact G3 report, with no implementation, spec, checklist, status, archive or earlier-review changes. Compare its staged bytes with the received report and verify no executable mode or other unintended metadata. This narrow exception solves the report's self-hash cycle; it is not permission to exclude arbitrary documentation.

If anything else differs, repeat G3 on a new candidate. Store the final approved tree ID and `reviewed` state in the local journal, without editing tracked files after snapshot verification. Recheck branch and HEAD against the journal immediately before committing.

## 4. Commit and optional delivery

Create the commit from the verified index with a clear subject and `PIRAXE-Step: <step-id>` trailer. Do not use `--no-verify`, `--amend`, force, reset, or automatic rebase to bypass a failure. Wait for the command and inspect its result; then read Git state even if the command errored or timed out.

Verify the new commit's parent is the expected pre-commit HEAD, its branch is unchanged, its tree equals the final approved staged tree, and the archive/ledger/current-step contents are present. Inspect post-hook working/index changes too. Only a verified commit closes the step. Record its SHA and local success in the local journal; the journal can now be marked resolved. A new agent can resolve the closing commit by its unique trailer and archive path; no self-referential SHA edit or amend is needed.

Push only when the user's current or durably recorded explicit authority covers it. Verify `origin` (or the explicitly named remote) still points to the intended fork and verify the exact destination feature branch. Inspect ALL outgoing commits, including ancestors; stop if unrelated or unauthorized commits would be published. Push that one branch explicitly, without force or implicit tags. Do not push to the upstream project or default branch by inference.

Verify the result against a fresh remote query (for example, `git ls-remote --heads <remote> <exact-branch>`); require the expected SHA or verified descendant relationship. Distinguish verified success, no publication requested, pending authorization, and failed/unknown delivery. A stale local tracking ref is not proof. Record a post-commit delivery note in `STATUS.md` if needed and disclose that it is uncommitted; do not create endless metadata commits. Merge/PR/release actions need their own authorization.

## 5. Failure and interruption recovery

Always inspect the current HEAD/history/index before retrying. Use the unique step ID, expected parent and tree, trailer and archive to determine whether a commit actually succeeded. A nonzero exit or missing terminal output alone does not prove that it failed.

| Observation | Required action |
|---|---|
| No closing commit exists; candidate preparation or G3 failed | Restore only this attempt's closeout edits to their saved preimages and original staged entries, preserving all implementation and unrelated edits. Keep failed reports and journal. Reinstate the active step as `ready_to_commit` or `blocked` with exact reason/resume state; uncheck prospective completion. |
| Commit/hook failed with HEAD unchanged | Inspect hook edits and original index before restoring closeout metadata. Source/test changes invalidate G2, staged changes invalidate G3. Keep hooks enabled; repair the cause and re-review. |
| A closing commit exists and matches approved parent/tree/trailer | Mark transaction locally resolved; leave the completed archive and idle slot. Do not create a duplicate commit. Resume only requested delivery. |
| Commit exists but content/tree/parent differs from approval | Do not call it verified completion or rewrite history automatically. Preserve the commit and journal; record a blocked discrepancy, restore active follow-up state and uncheck the working-copy completion claim. Inspect and review a scoped corrective change before any further commit/push. |
| Concurrent user edits overlap saved closeout files | Do not overwrite with preimages. Preserve both evidence and current files, explain the overlap, and reconcile the affected hunks with the user. |
| Local commit verified, push failed or not confirmed | Keep local completion and archive; record delivery pending/unknown. Check the remote before retrying because an interrupted push may already have succeeded. No duplicate commit, force push or automatic pull/rebase. |

Restore through scoped file edits and, only for this attempt's owned index entries, exact saved blob/mode restoration. Never use broad `git reset`, `git checkout --`, `git restore .`, stash, or recursive deletion. If a newly created prospective archive is retained after failure, clearly mark it non-completed and remove its checked ledger status; preserve its evidence. Do not roll back actual user work or prior successful commits.
