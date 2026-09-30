# PIRAXE Fork Architecture

Last verified: 2026-09-28

Status: Baseline architecture recorded; detailed integration audit still required.

## Context boundaries

- `PROJECT_CONTEXT.md` is the concise source of truth for the current OpenMontage architecture.
- `docs/ARCHITECTURE.md` is the upstream architecture deep-dive.
- This file owns the PIRAXE fork overlay: what will be preserved, what is expected to change, and what remains unverified.

## Verified current architecture

OpenMontage is instruction-driven. The agent performs orchestration by reading declarative pipeline manifests and Markdown skills. Python supplies tools, validation, persistence, checkpoints, cost governance, and media operations.

Current execution shape:

```text
User request
  -> AGENT_GUIDE routing
  -> pipeline manifest in pipeline_defs/
  -> stage director skill in skills/pipelines/
  -> registered BaseTool implementations
  -> canonical schema-validated artifacts
  -> checkpoint and human approval rules
  -> edit / compose / publish
```

Verified extension surfaces relevant to this fork:

| Concern | Existing location or contract |
|---|---|
| Pipeline definitions | `pipeline_defs/*.yaml` |
| Stage behavior | `skills/pipelines/<pipeline>/` |
| Tool base contract | `tools/base_tool.py` |
| Tool discovery and provider reporting | `tools/tool_registry.py` |
| Video providers and selector | `tools/video/` and `tools/video/video_selector.py` |
| Image providers and selector | `tools/graphics/` and `tools/graphics/image_selector.py` |
| Artifact contracts | `schemas/artifacts/` |
| Pipeline contract | `schemas/pipelines/pipeline_manifest.schema.json` |
| Checkpoint persistence | `lib/checkpoint.py` and `schemas/checkpoints/` |
| Budget tracking | `tools/cost_tracker.py` |
| Backlot UI | `backlot/` |
| Composition | `tools/video/video_compose.py`, Remotion, HyperFrames, and FFmpeg paths |
| Contract and quality tests | `tests/contracts/` and `tests/qa/` |

## Confirmed incompatibility to address

The existing `cinematic` pipeline requires extensive research and at least three directions or concept options. PIRAXE instead prefers one principal direction and introduces alternatives only for a real unresolved choice. The PIRAXE workflow therefore needs its own pipeline behavior rather than an unmodified copy of `cinematic`.

## Intended PIRAXE overlay

The exact filenames remain provisional until the architecture audit is accepted. The likely shape is:

```text
PIRAXE workflow layer
  -> dedicated pipeline manifest
  -> PIRAXE stage director skills
  -> PIRAXE-specific canonical artifacts or compatible extensions
  -> existing checkpoint, review, cost, and composition infrastructure

Provider layer
  -> Paipu BK concrete video provider
  -> existing video selector and registry
  -> Nano Banana concrete image provider/editor
  -> existing image selector and registry
```

### PIRAXE workflow responsibilities

- Brief extraction from partial user input.
- Principal creative direction.
- Shot breakdown and continuity plan.
- Reference manifest.
- Provider-aware prompt compilation.
- Generation job tracking.
- Footage and asset review.
- Targeted correction or regeneration.

### Paipu BK integration contract to verify

- Official service name, base URL, authentication scheme, and API version.
- Supported generation modes and models.
- Request schema and media/reference inputs.
- Async submission, polling, cancellation, timeout, and retry behavior.
- Output retrieval, expiry, and provenance metadata.
- Pricing or credit reporting.
- Rate limits and error taxonomy.
- Fit with `BaseTool`, `video_selector`, checkpoints, cost tracking, and provider menus.

### Nano Banana integration contract to verify

- Official API surface and current model identifiers.
- Authentication and Google credential reuse, if applicable.
- Text-to-image, image-to-image, multi-image, mask, and edit capabilities.
- Input/output constraints, safety responses, and metadata.
- Cost, quota, retry, and error behavior.
- Fit with `BaseTool`, `image_selector`, asset manifests, and provider menus.

## Architectural rules

- Add concrete providers through the existing capability packages; do not create parallel registries.
- Prefer selector-plus-provider routing.
- Record provider, model, seed when available, request identifiers, source inputs, cost, and output provenance.
- Keep provider-specific API behavior inside its adapter and related provider skill.
- Keep creative policy in PIRAXE skills and artifacts, not in provider code.
- Reuse checkpoint, review, cost, and composition infrastructure where contracts fit.
- Change shared contracts only through an explicit decision entry and focused migration plan.

## Open questions

- The authoritative Paipu BK API specification has not yet been recorded in this repository.
- The exact Nano Banana product/API/model surface to support has not yet been selected and verified.
- PIRAXE stage names and artifact boundaries require a formal mapping against existing schemas.
- Backlot changes may or may not be necessary; determine this after artifact and checkpoint mapping.
- The fork currently has only the `origin` remote configured; an upstream synchronization policy is not yet recorded.

## Update rule

When an audit or implementation confirms an extension point, replace provisional language with the verified path and cite the relevant repository files. When a design changes, add or supersede an entry in `DECISIONS.md`.
