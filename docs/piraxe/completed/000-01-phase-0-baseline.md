# Completed-step archive candidate — 000-01-phase-0-baseline

This is the prospective archive prepared for G3. Completion is effective only when this record is in a verified commit with trailer `PIRAXE-Step: 000-01-phase-0-baseline`.

## Identity, authority and outcome

- Step: commit the existing Phase 0 PIRAXE project-memory and local build-skill baseline.
- Contract: [spec revision 1](../specs/000-01-phase-0-baseline.md), SHA-256 `109B6AA7328CAFA4198B1D9C7842BCE93E8662F93A506D142236E514C2FDCE08`.
- Roadmap phase and plan: Phase 0, [Plan 000](../plans/000-project-memory.md).
- Branch: `docs/piraxe-project-context`; base `main` at `08e2151fa02de28a5d6a312b3d575692bf147ad7`; pre-commit HEAD is the same SHA.
- Original user request: “commit the current files, so we can start the first feature clean.” This authorizes the coherent current Phase 0 files and a local commit only. No push, merge, or feature implementation is authorized.
- Initial index: empty. Initial tracked changes: `AGENTS.md`, `AGENT_GUIDE.md`, `PROJECT_CONTEXT.md`. Initial untracked files: 25 under the three project-local skills and `docs/piraxe/`. No unrelated owned/staged content was found.
- Intended result: one documentation-only local commit, then an idle active-step slot and a clean working tree. The commit must be verified before this prospective record is treated as complete.

## Preserved task and acceptance log

| ID | State at G3 preparation | Evidence / outcome |
|---|---|---|
| T-01 | Checked | Inspected root diff, memory hub, three local skills, initial Git inventory, branch/base, empty index and absence of application-code edits. Ownership matched Plan 000 and the user's current-files request. |
| T-02 | Checked | Three skill validators, UI YAML parse, relative-link resolution, Git scope/whitespace check and credential-pattern scan passed; details below. |
| T-03 | Checked | Current independent G1 attempt 03 and G2 attempt 03 passed after four EOF-only repairs. Earlier review attempts and blocked G2-a01 remain preserved. |
| T-04 | Pending at archive preparation | Git-local recovery journal was created before prospective completion edits. The staged candidate and G3 review are due before commit. |
| T-05 | Pending until actual commit | Verify parent/tree/trailer/branch/clean working tree after the commit; the archive cannot contain its future SHA. |
| AC-01 | Passed at G2 | Root mandatory guide route retained; Phase 0 branch/plan/next action agree; providers remain planned. |
| AC-02 | Passed at G2 | Three local skills validate, UI YAML parses, lifecycle/recovery reviewed; historical fixture evidence is explicitly separate from the real step. |
| AC-03 | Passed at G2 | Owned documentation-only inventory, links, targeted credential hygiene, whitespace and application-code absence verified. |
| AC-04 | Pending at archive preparation | Exact staged archive/index and independent G3 review are the next gate. |
| AC-05 | Pending until actual commit | Commit parent/tree/trailer and clean-tree checks are post-commit. |

At G2, the ledger remained unchecked and the active slot remained live. Later checks are scheduled at their actual gates; this record makes no claim that an uncreated commit was already tested.

## Validation commands and observed results

All checks ran on 2026-09-29 at the repository root in the offline Windows PowerShell checkout. No live provider call was applicable or made.

| AC | Command or method | Exit / observed assertion |
|---|---|---|
| AC-01 | Inspect `git diff -- AGENTS.md AGENT_GUIDE.md PROJECT_CONTEXT.md` and the PIRAXE memory files | Mandatory `AGENT_GUIDE.md` routing remained; Phase 0 plan/status/branch aligned; Paipu BK and Nano Banana were described as planned. |
| AC-02 | `PYTHONUTF8=1 python .../skill-creator/scripts/quick_validate.py` on each of `spec`, `inplement`, `commit` | Exit 0 for each: `Skill is valid!`. |
| AC-02 | Parse three `agents/openai.yaml` files with Python/PyYAML | Exit 0; display names `Spec`, `Inplement`, `Commit`; short descriptions nonempty. |
| AC-03 | Resolve relative Markdown links in owned Markdown files | Parent pass: 27 files, 42 links, zero broken. G2-a02 pass: 29 files, 51 links, zero broken. Current G2-a03 pass: 31 files, 54 links, zero broken. Counts increased as review receipts were added. |
| AC-03 | `git diff --check`, `git diff --name-status`, `git ls-files --others --exclude-standard`, `git status --short -- tools pipeline_defs schemas tests lib backlot`, `git diff --cached --name-status` | Exit 0; only three root tracked edits and owned untracked docs/skills; application-code and index outputs empty before closeout. |
| AC-03 | Targeted `rg` patterns for private keys and long API tokens over candidate Markdown/YAML | No matches (exit 1 for `rg`); manual review and G2 repeated hygiene check found no secret value. Pattern scan cannot prove absence of arbitrary secrets. |
| G2 | Independent manifest and contract checks | Current G2-a03 PASS on a 34-file snapshot digest `C5D2A59484E3CDA369B5029B5D8389D68412FD08AA84517FCDB68FC860271779` (prospective archive excluded); G1-a03 spec/authority/plan/status hashes reproduced. |
| Closeout attempt 01 | First `git diff --cached --check` | Failed on one extra blank LF in four Phase 0 Markdown files. Scoped index and active metadata were restored from the journal. One LF was removed from each; G1/G2 attempt 03 passed. |
| Closeout attempt 02 | `git diff --cached --check` and staged-tree review | Whitespace check passed, but G3-a01 failed because two Plan 000 task-line parentheticals changed the G1/G2 contract hash. The 36-path index and five metadata preimages were restored. |

The [historical skill-validation record](../reviews/2026-09-29-skill-validation.md) separately describes instruction reviews and a disposable Git exercise. It did not certify this live step, push, or merge.

## Review history, deviations, and decisions

- [G1 attempt 01 — PASS](../reviews/000-01-phase-0-baseline-G1-a01.md), independent `/root/g1_baseline`, 2026-09-29 21:27 America/Bogota. The report's `CURRENT_STEP.md` authority-prefix hash later could not be reconciled after progress edits.
- [G2 attempt 01 — BLOCKED](../reviews/000-01-phase-0-baseline-G2-a01.md), independent `/root/g2_baseline`, 2026-09-29 21:41 America/Bogota. Candidate requirements/checks passed, but G1 currency was uncertain. The report was preserved without changing its verdict.
- [G1 attempt 02 — PASS](../reviews/000-01-phase-0-baseline-G1-a02.md), independent `/root/g1_baseline_a02`, 2026-09-29 21:48 America/Bogota. Freshly reviewed the current spec and authority/ownership contract with reproducible extraction/hash rules; it did not retroactively explain the earlier hash mismatch.
- [G2 attempt 02 — PASS](../reviews/000-01-phase-0-baseline-G2-a02.md), independent `/root/g2_baseline_a02`, 2026-09-29 21:57 America/Bogota. It independently verified current G1, all G2-due requirements and the 32-file candidate. A manifest-line transcription error was corrected by the reviewer before its report was saved; it rehashed all candidate files and kept the digest.
- Closeout attempt 01 failed staged whitespace preflight on four extra blank EOF lines; the original index and active metadata were restored from its Git-local journal. G1/G2 attempt 03 reviewed the exact one-LF repairs.
- [G1 attempt 03 — PASS](../reviews/000-01-phase-0-baseline-G1-a03.md), independent `/root/g1_baseline_a03_retry`, 2026-09-30 16:28 America/Bogota. It verified the exact four one-LF removals, current contract and recovered journal/index.
- [G2 attempt 03 — PASS](../reviews/000-01-phase-0-baseline-G2-a03.md), independent `/root/g2_baseline_a03`, 2026-09-30 16:38 America/Bogota. It verified current G1, all G2-due criteria, 54 links and a 34-file candidate manifest.
- [G3 attempt 01 — FAIL](../reviews/000-01-phase-0-baseline-G3-a01.md), independent `/root/g3_baseline_a01`, 2026-09-30 16:52 America/Bogota. The 36-path staged tree `61e83321e20b0f0748507b80e24e777f14b66c1f` matched the journal, but two added parentheticals in the Plan 000 task lines changed its reviewed contract hash. Its index and five metadata preimages were restored; no commit was made.
- G3 attempt 02: pending report at `docs/piraxe/reviews/000-01-phase-0-baseline-G3-a02.md`. Closeout attempt 03 retains the original Plan task text and changes only their checkboxes within the hashed contract span. The G3 receipt may be attached only after a PASS on the exact staged tree.

No runtime design decision was made in this step. The accepted PIRAXE decisions remain in [DECISIONS.md](../DECISIONS.md). There is no change to provider API facts or application behavior.

## Remaining limits and next prerequisites

- Phase 0 terminology and branch-policy discussion is still an unchecked Plan 000 item. The local baseline commit does not imply that discussion occurred or that `main` accepted the branch.
- No remote push or merge was requested. Delivery and branch integration remain separate from the local commit.
- The next planned work is the Phase 1 architecture/provider-contract audit on its own research branch after an accepted baseline. This archive does not authorize that work automatically.
- A closing commit is found by its unique `PIRAXE-Step: 000-01-phase-0-baseline` trailer and this archive path. Its actual SHA and post-commit checks must be read from Git history; do not amend this archive to insert a self-referential hash.
