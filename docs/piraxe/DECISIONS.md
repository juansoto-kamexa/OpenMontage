# PIRAXE Fork Decision Log

Last updated: 2026-09-28
Build-workflow decision added: 2026-09-29

Use sequential identifiers. Never delete an accepted decision. Mark it `Superseded` and link to the replacement.

## D-001 — Store durable context in the repository

- Date: 2026-09-28
- Status: Accepted
- Decision: Store project intent, architecture, roadmap, status, branch policy, decisions, and executable plans as checked-in Markdown under `docs/piraxe/`.
- Rationale: Chat transcripts are thread-scoped and may not be available to a new agent. Repository files travel with branches and are inspectable in reviews.
- Consequences: Every work session must update the relevant memory files. Stale documentation is treated as a handoff defect.

## D-002 — Keep `AGENTS.md` small and preserve OpenMontage routing

- Date: 2026-09-28
- Status: Accepted
- Decision: Keep root `AGENTS.md` as the mandatory entry point to `AGENT_GUIDE.md`. Put detailed project memory in existing context files and `docs/piraxe/`.
- Rationale: OpenMontage's guide contains request-routing rules that must run before task execution. A small bootstrap avoids duplicated or conflicting instruction sets.
- Consequences: `AGENT_GUIDE.md` must link to the PIRAXE memory hub, and new agents must follow its reading order.

## D-003 — PIRAXE governs creative workflow; OpenMontage remains the production substrate

- Date: 2026-09-28
- Status: Accepted
- Decision: Preserve OpenMontage's declarative pipelines, skills, tools, registry, artifacts, checkpoints, costs, UI, and composition systems while adding a dedicated PIRAXE workflow.
- Rationale: The existing architecture is aligned with provider and production orchestration, but the existing cinematic workflow imposes creative assumptions that conflict with PIRAXE.
- Consequences: Avoid a wholesale rewrite and avoid modifying `cinematic` into a hybrid of incompatible methods.

## D-004 — Integrate providers through existing capability contracts

- Date: 2026-09-28
- Status: Accepted
- Decision: Paipu BK will be designed as a concrete video provider and Nano Banana as a concrete image-generation/editing provider, both routed through existing registry and selector patterns.
- Rationale: The repository's verified convention is capability-first discovery with concrete provider tools derived from `BaseTool`.
- Consequences: No ad hoc provider scripts or parallel registries. Exact classes, filenames, and configuration keys remain subject to the Phase 1 audit.

## D-005 — Use branch-per-phase or branch-per-logical-change

- Date: 2026-09-28
- Status: Accepted
- Decision: Keep `main` stable and perform planned work on focused branches recorded in the active plan and `STATUS.md`.
- Rationale: Persistent branch identity makes handoffs safer and keeps provider, workflow, and documentation changes independently reviewable.
- Consequences: Agents must verify branch and working-tree state before editing. Unrelated changes must not be bundled into the same commit or pull request.

## D-006 — Repository-local spec, implementation and commit workflow

- Date: 2026-09-29
- Status: Accepted; bootstrap skill validation recorded in `reviews/2026-09-29-skill-validation.md`.
- Decision: Provide `spec` (displayed as Spec), `inplement` (requested spelling) and `commit` only under this repository's `.agents/skills/`. Maintain one active-step record, detailed retained specs, real fresh-agent review reports, and permanent completion archives linked from a checked-off ledger.
- Rationale: The user requires detailed executable steps, isolated-agent verification and continuity between agents, including correct branch selection and clearing completed work from the active slot without losing context.
- Consequences: G1 specification, G2 implementation and G3 staged-closeout reviews block advancement unless current and passed. These are separate from advisory video-production review. Commit completion, remote delivery and phase integration are distinct. Closeout needs recoverable metadata and a verified scoped commit before the step is considered complete. Skill invocation does not grant authority for unrelated actions.
