# Step <PPP-NN-slug> — <Outcome>

Replace angle-bracket fields with verified details. This is the stable specification, not the live execution log. Use `Not applicable — reason` for irrelevant sections. Essential unresolved choices block G1. Keep task/check progress in `docs/piraxe/CURRENT_STEP.md`.

## 1. Identity and authority

- Step ID and spec revision:
- Date and author:
- Roadmap phase and phase-plan path:
- User request / authorized outcome and provenance:
- Working branch / base branch / exact base SHA / observed HEAD:
- Dependency step IDs and verified completion evidence:
- Commit authority and source (or not authorized):
- Push authority, exact remote/branch and source (or not authorized):
- Required human decisions/approvals (or none and why):

## 2. Product and project context

Explain who needs the outcome, why this step is next, and how it supports PIRAXE, Paipu BK or Nano Banana without expanding scope. Describe current behavior and desired observable behavior. Separate facts, user decisions, and assumptions. Reference VISION, ARCHITECTURE and relevant decision IDs; do not replicate the whole roadmap.

## 3. Scope, non-goals and change ownership

| Included outcome | Explicit exclusion | Reason/boundary |
|---|---|---|
| <concrete behavior> | <adjacent work deferred> | <scope justification> |

Record initial Git status, existing staged/unstaged/untracked work, ownership and any user-approved inclusion. Unknown overlapping ownership must be resolved before editing/committing. Specify the candidate's allowed paths/hunks and exclusions; revise and re-review material scope changes.

## 4. Verified baseline and proposed design

| Concern | Existing path and symbol/schema | Observed behavior/evidence | Proposed change |
|---|---|---|---|
| <routing/provider/artifact/etc.> | <real inspected path> | <facts> | <minimal compatible change> |

Explain the end-to-end data/control flow, callers and downstream consumers, reuse vs new work, compatibility with existing pipelines, and rejected alternatives only where the tradeoff matters. Label provisional paths. No second provider registry or new orchestration architecture without a scoped decision.

## 5. Functional requirements

| ID | Trigger / input / precondition | Required behavior | Observable output / invariant |
|---|---|---|---|
| R-01 | <specific> | <specific> | <testable> |

Cover ordinary flow and applicable edge cases: missing/invalid inputs, empty results, duplicate calls, partial completion, retries, cancellation, timeouts, rate limits, provider safety rejection and restart/resume. Define what must never occur (duplicate billed jobs, lost artifacts, unsupported fallback, etc.) when relevant.

## 6. Interface and data contracts

For every changed public function/tool/API/artifact/config key, give:

- Exact name, location, callers and supported versions.
- Input fields/types/requiredness/defaults, allowed ranges, validation order and examples.
- Output fields/types, identifiers, errors/statuses and examples.
- Persistent fields, schema/version/migration rules, ownership and backward compatibility.
- State transitions, idempotency, restart/recovery, concurrency/cancellation semantics.
- Config/credential lookup, environment variable names, local setup and secret redaction; no credential values.

For provider work, cite official source URL and verification date for base URL, auth, model identifiers, limits, pricing assumptions, submission/polling/output/error behavior. Identify unsupported capabilities explicitly. Do not invent absent facts; turn essential uncertainty into a blocker or research task.

## 7. Operational and non-functional requirements

Define applicable constraints with measurable limits or concrete behavior: timeout/retry/backoff bounds; rate/budget enforcement; output size/storage/expiry; provenance; logs/error redaction; privacy; accessibility/UI states; performance and resource usage. List compatibility and regression risks. Explain each not-applicable section rather than padding the spec with generic demands.

## 8. File-by-file work

| Path / symbol | Add/change/remove | Intended responsibility/change | Related requirements | Validation |
|---|---|---|---|---|
| <path> | <operation> | <precise change> | R-01 | AC-01 |

Include source, tests, fixtures, schemas, docs, registry/selector/config wiring and migrations. Do not prescribe unverified filenames as existing facts.

## 9. Ordered implementation tasks

### T-01 — <Bounded action>

- Depends on:
- Inputs/read first:
- Exact change and expected output:
- Files/symbols allowed:
- Requirements addressed:
- Due gate (G1, G2, G3, or post-commit; feature implementation must be due by G2):
- Validation command and expected assertions:
- Exit condition:

Repeat for all work, including documentation and integration validation. Identify safe parallel tasks and shared-file conflicts. Testing and evidence collection are tasks, not an implied afterthought.

## 10. Acceptance and validation matrix

| AC ID | Requirements | Due gate | Given / when / then assertion | Check type and exact command | Fixtures/environment | Pass/fail rule |
|---|---|---|---|---|---|---|
| AC-01 | R-01 | G2 | <observable behavior> | <unit/contract/integration/manual command> | <offline/live, dependencies> | <exact assertions/exit status> |

Every requirement needs at least one criterion. Include positive, negative, boundary, regression and restart cases as applicable. Specify command working directories, setup, cleanup of only owned artifacts, dependency versions and safe fixtures. Separate required checks from optional ones. Essential unavailable tests block completion. Existing unrelated baseline failures need reproduction and impact evidence, not a blanket exemption.

Assign feature behavior and its tests to G2 or earlier. Checks of the staged archive/index belong to G3; checks of the resulting commit's actual parent/tree/trailer belong to post-commit. Those later checks stay pending at G2 rather than blocking it or being falsely marked passed. Do not use this distinction to defer unfinished implementation. Record delivery separately from local completion unless the user explicitly requires a delivered outcome.

For manual/visual checks define the concrete expected state and recorded evidence. For mocks state what live behavior remains unverified. Live paid API calls require explicit user authorization and cost limits.

## 11. Review gates and snapshot scope

- G1: independent feasibility/spec review before implementation; mandatory items from BUILD_WORKFLOW plus step-specific checks.
- G2: fresh independent review of actual implementation and test evidence; required acceptance coverage and integration probes.
- G3: fresh review of staged implementation, archive and cleared active slot before commit.
- Step-specific additional human gates, if any:
- Explicit manifest paths and relevant baseline/instruction dependencies:
- Narrow predeclared evidence/bookkeeping exclusions:
- Conditions invalidating each review:

Use REVIEW_BRIEF for all reports. No self-approval, fabricated reviewer or advisory auto-pass. Record report paths in the execution log, not by mutating this contract after each review.

## 12. Release, rollback and recovery

Define activation/default behavior, migration/deployment needs (if any), how to verify success, and scoped rollback. Preserve user data and working changes. Define partially completed/failed-job recovery where applicable. A local feature commit is not deployment or permission to merge/release.

## 13. Completion and handoff

- Required artifacts and task/acceptance checklist to archive:
- Documentation/decision/architecture updates required:
- Proposed coherent commit subject and `PIRAXE-Step` trailer:
- Archive path and ledger entry:
- Phase criteria satisfied by this step versus still outstanding:
- Next dependency-ready step suggestion, not automatic authorization:

## 14. Open questions, assumptions and risks

| ID | Question/assumption/risk | Evidence / decision owner | Blocks what? | Resolution required |
|---|---|---|---|---|
| Q-01 | <specific> | <source or owner> | <gate/task or non-blocking rationale> | <action> |

## 15. Revision history and sources

Record spec revision/date, changed requirement IDs, why it changed and which reviews became stale. List authoritative source links with dates and repository paths inspected. Never rewrite the user request or old review reports to fit the result.
