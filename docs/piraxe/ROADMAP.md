# PIRAXE Fork Roadmap

Last updated: 2026-09-28

This roadmap establishes build order. Each implementation phase gets its own branch and executable plan. Branch names are targets until the relevant phase begins.

## Phase overview

| Phase | Outcome | Target branch | Status |
|---|---|---|---|
| 0 | Durable project memory and agent handoff | `docs/piraxe-project-context` | Ready for review |
| 1 | Verified architecture and integration contract audit | `research/piraxe-architecture-audit` | Planned |
| 2 | PIRAXE artifacts, pipeline skeleton, and stage skills | `feat/piraxe-workflow-foundation` | Planned |
| 3 | Nano Banana image-generation and editing provider | `feat/nano-banana-provider` | Planned |
| 4 | Paipu BK video-generation provider | `feat/paipu-bk-provider` | Planned |
| 5 | End-to-end PIRAXE routing, review, correction, and Backlot fit | `feat/piraxe-end-to-end` | Planned |
| 6 | Hardening, documentation, and release readiness | `release/piraxe-initial` | Planned |

## Phase 0 — Durable project memory

Deliverables:

- Root routing files point future agents to the project memory.
- Vision, architecture overlay, roadmap, live status, decisions, and branching policy exist.
- An active-plan convention and reusable plan template exist.
- Current documentation changes live on a documentation branch rather than `main`.

Acceptance criteria:

- A new agent can identify the current phase, current branch, next action, and unresolved decisions from repository files alone.
- No application code is changed.
- Links between guidance files resolve.

## Phase 1 — Architecture and provider contract audit

Deliverables:

- Map the exact pipeline, skill, schema, registry, selector, cost, checkpoint, and UI extension points.
- Compare PIRAXE requirements with the existing `cinematic` and adjacent pipelines.
- Verify Paipu BK and Nano Banana API contracts from authoritative documentation.
- Decide the exact provider class names, capability declarations, configuration keys, artifacts, and test seams.
- Decide whether an `upstream` Git remote and synchronization cadence are required.

Acceptance criteria:

- No unresolved API assumptions remain in the implementation plan.
- Proposed file changes are enumerated and justified.
- Each later implementation phase has validation commands and rollback boundaries.

## Phase 2 — PIRAXE workflow foundation

Deliverables:

- Dedicated PIRAXE pipeline manifest.
- Stage director skills for the approved PIRAXE stages.
- Required new or extended artifact schemas.
- Contract tests for manifests and artifacts.
- Human approval gates aligned with creative and cost decisions.

Acceptance criteria:

- Pipeline and artifact validation passes.
- The workflow can run with mocked or existing providers through every stage boundary.
- The pipeline does not inherit mandatory multi-direction or research-volume requirements that conflict with PIRAXE.

## Phase 3 — Nano Banana provider

Deliverables:

- Concrete image generation/editing adapter in the established graphics capability package.
- Registry and selector integration.
- Configuration, availability, provider menu, provenance, cost, and error behavior.
- Provider-specific skill/documentation.
- Focused unit and contract tests with external calls mocked.

Acceptance criteria:

- Text-to-image and the approved editing modes follow the standard `ToolResult` contract.
- Missing credentials and unsupported operations fail clearly without exposing secrets.
- Selector routing and provider discovery work as expected.

## Phase 4 — Paipu BK provider

Deliverables:

- Concrete video provider in the established video capability package.
- Async job submission and lifecycle handling where required.
- Registry and selector integration.
- Configuration, availability, provider menu, provenance, cost, and error behavior.
- Provider-specific skill/documentation.
- Focused unit and contract tests with external calls mocked.

Acceptance criteria:

- Supported generation modes follow the standard `ToolResult` contract.
- Polling, timeout, retry, failure, and output retrieval paths are tested.
- Selector routing and provider discovery work as expected.

## Phase 5 — End-to-end PIRAXE production

Deliverables:

- Provider-aware prompt compilation.
- Consistent reference and continuity handling.
- Generation-job records linked to output review.
- Review and correction loop with checkpoint visibility.
- Any necessary Backlot changes based on verified artifact needs.
- Representative end-to-end fixture or test production.

Acceptance criteria:

- A single production can move from partial brief to reviewed final output without losing approved decisions.
- Human gates stop and resume correctly.
- Costs, provider substitutions, failures, and corrections remain inspectable.

## Phase 6 — Hardening and release readiness

Deliverables:

- Full relevant test, lint, and type-check pass.
- Setup and operator documentation.
- Example project and smoke-test flow.
- Security and secret-handling review.
- Upstream-drift review and migration notes.
- Initial release notes and known limitations.

Acceptance criteria:

- The documented setup is reproducible on a clean checkout.
- No unresolved critical test or security failures remain.
- Known limitations and unsupported provider behavior are explicit.
