# PIRAXE Executable Plans

Each file in this directory describes one bounded milestone or logical change. Plans are operational state, not aspirational notes.

## Plan lifecycle

Use one of these statuses:

- `Proposed`
- `Accepted`
- `In progress`
- `Blocked`
- `Complete`
- `Superseded`

Only one plan should normally be active on a branch. `docs/piraxe/STATUS.md` identifies it.

## Required contents

Every plan must state:

- Outcome and scope.
- Non-goals.
- Base branch and working branch.
- Dependencies and assumptions.
- Files or systems expected to change.
- Ordered implementation steps.
- Acceptance criteria.
- Validation commands or checks.
- Progress log.
- Decisions or discoveries that must be copied into durable context.
- Handoff instructions and exact next action.

Copy `TEMPLATE.md` when starting a plan. Use the next available numeric prefix.

## Detailed build steps

A phase plan may contain several independently specified steps. Use `$spec` and its detailed template to create each contract under `docs/piraxe/specs/`; use `CURRENT_STEP.md` for the single live execution record and `STEPS.md` for the permanent ledger. Follow [BUILD_WORKFLOW.md](../BUILD_WORKFLOW.md) for isolated-agent gates, implementation and transactional closeout. Completing a step checks only the criteria it actually satisfies; the whole phase remains open until all its acceptance criteria and required approvals are met.
