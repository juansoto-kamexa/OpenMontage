# PIRAXE OpenMontage Vision

Last updated: 2026-09-28

## Mission

Build a maintainable OpenMontage fork in which PIRAXE governs advertising strategy and production flow, while OpenMontage continues to provide the pipeline, provider, checkpoint, cost, UI, and rendering infrastructure.

## Product direction

The finished system should help a user move from incomplete commercial intent to a coherent, reviewable production without forcing the user to write a complete brief first.

The workflow should preserve a single creative through-line:

1. Extract the brief from available information.
2. Establish audience and situation, objective, single takeaway, product role and evidence, tone, and distribution constraints.
3. Develop one principal creative direction.
4. Translate that direction into a shot-level production blueprint.
5. Create and manage references.
6. Compile provider-aware prompts.
7. Generate assets and footage through registered providers.
8. Review results against the approved intent.
9. Correct weak or inconsistent material without losing continuity.
10. Compose and validate the final production.

## Required capabilities

- A dedicated PIRAXE workflow represented through OpenMontage's pipeline and skill contracts.
- Paipu BK integration for video generation.
- Nano Banana API handling for image generation and image editing.
- Canonical artifacts that carry decisions from brief through review and correction.
- Human approval at materially creative or costly gates.
- Provider availability, configuration, cost, and failure behavior exposed through existing OpenMontage conventions.
- Tests that protect provider contracts, pipeline manifests, artifacts, checkpoints, and critical workflow rules.

## Governing principles

- PIRAXE governs creative decisions; OpenMontage governs production infrastructure.
- Ask only for information that materially changes the result.
- Prefer one principal direction over mandatory sets of arbitrary alternatives.
- Offer alternatives when a genuine unresolved choice exists.
- Keep claims grounded in evidence.
- Preserve continuity across concept, shots, references, prompts, generations, and corrections.
- Do not bypass OpenMontage's registry, pipeline, checkpoint, or artifact contracts.
- Never hide provider substitutions, degraded paths, costs, or blockers.

## Non-goals

- Rewriting OpenMontage from scratch.
- Creating a separate Python orchestrator that competes with the instruction-driven agent model.
- Bypassing selectors or the tool registry with ad hoc API scripts.
- Copying the existing `cinematic` pipeline unchanged when it conflicts with PIRAXE.
- Baking credentials or user-specific configuration into the repository.
- Expanding into unrelated providers or UI redesigns before the core PIRAXE flow works end to end.

## Hard constraints

- Preserve upstream behavior unless a planned change explicitly requires otherwise.
- Keep provider integrations modular and discoverable through `BaseTool` and the registry.
- Keep workflow stages declarative through pipeline manifests and stage skills.
- Use canonical, schema-validated artifacts between stages.
- Keep pull requests and commits focused on one logical change.
- Validate each milestone before starting the next.
- Treat API names, endpoints, authentication, supported models, pricing, and async behavior as facts that must be verified from authoritative provider documentation before implementation.

## Done when

The fork is ready for its first stable release when:

- The PIRAXE pipeline can carry an incomplete request through an approved brief, principal concept, shot blueprint, assets, review, correction, and final composition.
- Nano Banana image generation and editing operate through the standard image capability path.
- Paipu BK video generation operates through the standard video capability path.
- Configuration and missing-credential behavior are explicit and safe.
- Provider and pipeline contract tests pass.
- A representative end-to-end production can be reproduced from documented inputs.
- The Backlot/checkpoint experience exposes the relevant approvals and progress.
- Project documentation accurately describes setup, architecture, limitations, and validation.
