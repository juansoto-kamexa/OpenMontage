# Plan 000 — Durable Project Memory

- Status: In progress
- Roadmap phase: 0
- Base branch: `main`
- Working branch: `docs/piraxe-project-context`
- Owner: Project maintainer with Codex assistance
- Last updated: 2026-09-29

## Outcome

Create a durable, version-controlled context and planning system so any future agent can understand the fork, choose the correct branch, continue the right milestone, and preserve decisions without depending on a previous chat.

## Scope

- Preserve the root OpenMontage routing contract.
- Connect `AGENT_GUIDE.md` and `PROJECT_CONTEXT.md` to the PIRAXE memory hub.
- Record vision, architecture overlay, roadmap, status, decisions, and branch policy.
- Establish a reusable executable-plan convention.
- Add project-local `spec`, `inplement`, and `commit` skills with detailed step contracts, isolated-agent review gates and recoverable archived completion.
- Keep all runtime and application code unchanged.

## Non-goals

- Implementing the PIRAXE pipeline.
- Adding Paipu BK or Nano Banana code.
- Selecting unverified provider endpoints or configuration keys.
- Modifying production behavior.
- Committing, pushing, or merging without user authorization.

## Dependencies and assumptions

- The fork is cloned and `origin` points to `juansoto-kamexa/OpenMontage`.
- OpenMontage's current `AGENT_GUIDE.md` and `PROJECT_CONTEXT.md` remain authoritative for existing behavior.
- Git history is the long-term archive; `STATUS.md` is the concise live handoff.

## Expected change surface

- `AGENTS.md`
- `AGENT_GUIDE.md`
- `PROJECT_CONTEXT.md`
- `docs/piraxe/`
- `.agents/skills/spec/`, `.agents/skills/inplement/`, `.agents/skills/commit/`

## Steps

- [x] Inspect existing repository guidance and architecture documentation.
- [x] Verify Git branch and remote state.
- [x] Create `docs/piraxe-project-context` before adding the memory system.
- [x] Create the `docs/piraxe/` memory hub.
- [x] Record roadmap phases and suggested branch names.
- [x] Wire `AGENT_GUIDE.md` and `PROJECT_CONTEXT.md` to the memory hub.
- [x] Validate links, changed files, and documentation-only scope.
- [x] Create the three repository-local build skills and their detailed template/lifecycle/reviewer/closeout references.
- [x] Add an idle current-step file and permanent step ledger without claiming prior work is completed.
- [x] Validate skill frontmatter, UI metadata and local links.
- [x] Finish independent instruction review and disposable-repository workflow testing; clarify gate timing based on observed behavior and independently review that change.
- [x] Complete [step 000-01-phase-0-baseline](../specs/000-01-phase-0-baseline.md) through real-project G1/G2/G3 review and local commit.
- [ ] Review terminology and branch policy with the user.
- [x] Commit only if requested or approved.

## Acceptance criteria

- [x] A new agent can identify project purpose, current state, active plan, current branch, and next action from repository files.
- [x] Every planned build phase has an outcome, branch, and acceptance gate.
- [x] Existing OpenMontage routing remains intact.
- [x] No application code is changed.
- [x] No secrets or credentials are added.
- [x] Documentation links resolve.

## Validation

| Check | Command or method | Result |
|---|---|---|
| Branch | Inspect `git status --short --branch` | Passed: `docs/piraxe-project-context` |
| Scope | Inspect tracked diffs and untracked paths | Passed: guidance, `docs/piraxe/`, and the three project-local skills only; no application code |
| Links | Verify every referenced local Markdown path exists | Passed |
| Runtime code | Confirm no application-code path changed | Passed |
| Skills | Run bundled `quick_validate.py` for all three skill folders | Passed on 2026-09-29 |
| Skill metadata and links | Parse all three UI YAML files and resolve local Markdown links | Passed on 2026-09-29; final links rechecked at handoff |
| Independent evaluation | Fresh-context instruction reviews and isolated temporary Git workflow | Passed, including G1/G2/G3, scoped fixture commit and fresh-agent interrupted-closeout recovery; [evidence and limits](../reviews/2026-09-29-skill-validation.md) |
| Real baseline G1 | Fresh independent specification review of `000-01-phase-0-baseline` | Passed 2026-09-29; [G1 report](../reviews/000-01-phase-0-baseline-G1-a01.md) |
| Real baseline G2 preparation | Three skill validators, UI YAML parse, 42 local links, Git scope/whitespace and targeted credential scan | Passed 2026-09-29; details in [CURRENT_STEP.md](../CURRENT_STEP.md); independent G2 pending |
| Real baseline G2 attempt 01 | Fresh independent candidate review | [Blocked](../reviews/000-01-phase-0-baseline-G2-a01.md): candidate checks passed, but G1 authority-prefix hash could not be reconciled; renew G1 then G2 |
| Real baseline G1 attempt 02 | Fresh independent review of current specification and contract | [Passed](../reviews/000-01-phase-0-baseline-G1-a02.md); G2 attempt 02 pending |
| Real baseline G2 attempt 02 | Fresh independent review of 32-file Phase 0 candidate and G1 currency | [Passed](../reviews/000-01-phase-0-baseline-G2-a02.md); G3 and actual commit pending |
| Real baseline G1 attempt 03 | Fresh independent review after four EOF-only repairs and restored closeout state | [Passed](../reviews/000-01-phase-0-baseline-G1-a03.md) |
| Real baseline G2 attempt 03 | Fresh independent review of repaired documentation and current G1 | [Passed](../reviews/000-01-phase-0-baseline-G2-a03.md); G3 and actual commit pending |
| Real baseline G3 attempt 01 | Fresh independent review of staged tree `61e83321e20b0f0748507b80e24e777f14b66c1f` | [Failed](../reviews/000-01-phase-0-baseline-G3-a01.md): two added task-line parentheticals changed the G1/G2 Plan contract hash; index and metadata restored |
| Real baseline G3 attempt 02 and commit | Exact staged closeout and resulting local commit | Pending at prospective candidate preparation; checkmarks become effective only after verified commit |

## Progress log

- 2026-09-28 — Fork and existing agent guidance inspected.
- 2026-09-28 — Documentation branch created.
- 2026-09-28 — Durable memory files drafted under `docs/piraxe/`.
- 2026-09-28 — Root cross-links added; link, branch, and documentation-only scope checks passed.
- 2026-09-29 — Added only repository-local build skills and durable step/review/archive protocol at the user's request; preserved existing uncommitted work. No application changes, staging, commits or pushes performed in the live repository.
- 2026-09-29 — Independent skill review and actual temporary-repository workflow passed. A fresh agent resumed the completed-but-unresolved transaction without a duplicate commit. Gate-timing wording was clarified after an observed ambiguity and separately reviewed; no synthetic test step was added to the live ledger.
- 2026-09-29 — User requested a local commit of the current files. Step `000-01-phase-0-baseline` specified; independent real-project G1 passed. Local documentation checks passed; G2/G3 and actual commit remain pending.
- 2026-09-29 — Real-project G2 attempt 01 found a G1 snapshot-currency discrepancy in the active-step authority prefix; its verdict is BLOCKED. Preserve the report and renew G1/G2 before closeout.
- 2026-09-29 — Fresh G1 attempt 02 passed on the current authority/ownership contract. The prior hash discrepancy remains preserved; G2 attempt 02 is pending.
- 2026-09-29 — Fresh G2 attempt 02 passed the real documentation candidate and G1 currency checks. G3 and local commit remain pending.
- 2026-09-29 — First staged closeout failed `git diff --cached --check` on four extra blank EOF lines. Restored the exact pre-closeout index and active metadata from the Git-local journal, retained an explicitly prospective archive, trimmed one final LF in each affected file, and queued fresh reviews.
- 2026-09-30 — Independent G1 attempt 03 passed on the EOF-only changes and restored recovery state; [report](../reviews/000-01-phase-0-baseline-G1-a03.md). G2 attempt 03 remains pending.
- 2026-09-30 — Independent G2 attempt 03 passed the current candidate, [report](../reviews/000-01-phase-0-baseline-G2-a03.md). A pre-closeout whitespace scan of all untracked files passed; fresh G3 closeout remains.
- 2026-09-30 — G3 attempt 01 failed because two explanatory additions to task lines changed the reviewed Plan contract hash. Restored the exact staged index and five metadata preimages; preserved the FAIL report and recovery journal. Attempt 03 will change only task checkboxes within the contract span.
- 2026-09-30 — Prepared attempt-03 journal and prospective archive/ledger/idle-slot candidate. The two task lines above changed only from unchecked to checked; the user requested this local commit. Completion becomes effective only after G3 PASS and verified commit.

## Decisions and discoveries

- The repository already has a detailed `PROJECT_CONTEXT.md`; fork-specific memory should extend it rather than duplicate it.
- `tools/graphics/` owns current image providers and `tools/video/` owns video providers.
- Existing selectors and the `BaseTool` registry contract are the likely provider integration surfaces.
- The existing `cinematic` pipeline has creative requirements that conflict with PIRAXE's principal-direction method.

## Handoff

- Current state: Fresh G1/G2 attempt 03 passed. The G3 attempt-02 closeout candidate is prospective; prior failed G3 and restored index/metadata remain in the archive and journals.
- Blocker: No current blocker; verify the normalized Plan contract hash on the exact staged candidate before G3. The checkmarks are only prospective until a verified local commit.
- Exact next action: Independently review the exact staged candidate at G3, then make and verify the user's requested local commit. Terminology/branch-policy review and branch integration remain separate.
