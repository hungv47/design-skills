# Design Skills

Skills for brand identity, design systems, and user experience design.

## Installation

```bash
npx skills add hungv47/design-skills
```

## Skills

| Skill | Description |
|-------|-------------|
| `brand-system` | Brand identity and design systems — strategy, personality, voice, visual identity, tokens, components |
| `user-flow` | User flow diagrams and wireflows for digital products |

## Pipeline

```
brand-system → user-flow (optional sequence)
```

## Cross-Stack DAG

```
strategy: problem-analysis → solution-design → funnel-planner → experiment
                                    ↓                  ↓
comms:    icp-research → imc-plan → content-create → attribution
               ↓              ↕ (reads solution-design, targets)
design:   brand-system → user-flow
                              ↓
prod:     plan-interviewer → system-architecture → task-breakdown
          code-cleanup (standalone)    technical-writer (standalone)
```

`brand-system` benefits from `.agents/product-context.md` and `.agents/mkt/icp-research.md` (audience data from comms-skills).
`user-flow` output (`.agents/design/user-flow.md`) feeds into `system-architecture` and `task-breakdown` (from prod-skills).

## Cross-Stack Workflow

`user-flow` can read `.agents/product-context.md` for audience context, created by `icp-research` from [comms-skills](https://github.com/hungv47/comms-skills).

## Usage

- "Create a design system" → `brand-system`
- "Create a user flow" → `user-flow`
## License

MIT
