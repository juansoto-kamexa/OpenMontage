# Independent Build Reviewer Brief

The authoring agent fills the input values below and sends this brief to a fresh-context reviewer. It is a review task, not a request to implement or approve by default. Keep findings append-only between attempts.

## Inputs supplied by the author

- Absolute repository/candidate location and permitted read/test scope.
- Step ID, gate (`G1`, `G2`, or `G3`), attempt number, and intended report path.
- Original requested behavior and constraints, without author conclusions.
- Paths to `AGENT_GUIDE.md`, `docs/piraxe/README.md`, `BUILD_WORKFLOW.md`, the full spec and phase plan.
- Exact branch, HEAD/base, changed-file inventory, snapshot manifest and declared exclusions. At G3: reviewed staged-tree ID and closeout recovery location.
- Relevant source/schema/config/tests, raw prior reports and raw validation evidence.
- Required gate checklist from `BUILD_WORKFLOW.md`, permitted commands, unavailable environments and live-service restrictions.

## Reviewer task

Read the project instructions before inspecting the work. Independently check the actual artifacts against the user requirements, full spec and gate checklist. Do not rely on the author's description or green test summary. Inspect missing/new/deleted files and relevant integration points. Reproduce safe relevant checks and report exactly what you did and did not execute. Validate snapshot identity before and after inspection.

Do not edit implementation, spec, index, branch, or remote state. Return your report to the parent; write it only if explicitly given a dedicated safe output path. Do not invoke the commit skill as part of reviewing it. If required artifacts are missing, snapshots disagree, the candidate changes during review, or execution permissions prevent essential verification, return BLOCKED or FAIL with evidence rather than guessing.

## Required report

1. Identity: step/gate/attempt; reviewer agent identifier; date/time; fresh-context/non-author confirmation and isolation limits.
2. Candidate: checkout, branch, base and HEAD; file hash manifest or staged-tree ID; exact exclusions and inventory verified.
3. Verdict: `PASS`, `FAIL`, or `BLOCKED`.
4. Coverage table: requirement/acceptance/gate item -> actual inspected artifact/test -> observed evidence -> result. Every mandatory item needs coverage.
5. Commands: command, working directory, environment, exit code, observed assertions/output; clearly distinguish independent execution from inspection of supplied logs.
6. Findings: severity, required or optional, file/location, reproducible evidence, impact, necessary correction; explicitly say when there are none.
7. Unverified items and blockers; an essential unverified item prohibits PASS.
8. Gate exit decision and what would invalidate it. A PASS is conditional on this exact candidate remaining unchanged.

The parent must preserve the report's content and verdict, fix findings in the work, and request a new attempt. The parent cannot promote FAIL/BLOCKED to PASS.
