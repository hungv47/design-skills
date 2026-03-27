# Design Skills

Brand identity, design systems, and user experience design.

## Pipeline
brand-system → user-flow (optional sequence)

## Artifacts
Skills write to `.agents/design/`:
- `.agents/design/brand-system.md`
- `.agents/design/user-flow.md`

## Cross-Stack (Optional)
user-flow can read `.agents/product-context.md` for audience context.
Created by `icp-research`: `npx skills add hungv47/comms-skills`

## Recommended Starting Point
Run `icp-research` (from comms-skills) first to create `.agents/product-context.md` and audience research — both `brand-system` and `user-flow` produce significantly better output with audience context.

## Multi-Agent Skills

Both skills use a two-layer multi-agent orchestration pattern:

- `SKILL.md` = **orchestrator** — dispatch graph, routing logic, merge step, critic gate
- `agents/` = **sub-agent instruction files** — each with role, input/output contracts, domain knowledge, self-check
- `references/` = **shared data catalogs** — formula lists, template libraries read by multiple agents

### How it works
1. Orchestrator gathers context (pre-writing, artifacts, brief)
2. **Layer 1** agents run in parallel — each writes one section independently
3. Orchestrator merges outputs into the artifact template
4. **Layer 2** agents run sequentially — each refines the full document through one lens
5. **Critic agent** scores the output and returns PASS or FAIL (max 2 rewrite cycles)

### Skills using this pattern
- `brand-system` — 8 agents (strategy, personality, voice, visual, token-architect, component-token, accessibility, critic). Layer 1 parallel (strategy + personality + voice + visual) → Layer 2 sequential (token-architect → component-token → accessibility → critic). 2 routes: Quick Brand (strategy + visual + critic) for MVPs, Full Brand System (all agents) for comprehensive guidelines.
- `user-flow` — 5 agents (structure, edge-case, diagram, validation, critic). Layer 1 parallel (structure + edge-case) → Layer 2 sequential (diagram → validation → critic). Single route — complexity handled by automatic sub-flow decomposition for flows >15 screens.

### Reusable template
Each skill's `agents/_template.md` defines the standard structure for agent instruction files.
