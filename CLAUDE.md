# CLAUDE.md

Guidelines for AI agents working in this repository.

## Repository Overview

This repository contains the **startup** plugin for AI agents. The plugin namespace is `startup`, and it currently includes the `startup-design` skill (`/startup:startup-design`). The skill guides comprehensive startup design and idea validation through 8 structured phases.

- **Name**: Startup Design Skill
- **GitHub**: [ferdinandobons/startup-skill](https://github.com/ferdinandobons/startup-skill)
- **Creator**: Ferdinando Bons
- **License**: MIT

## Repository Structure

```
startup-skill/                         # Plugin namespace (startup:*)
├── .claude-plugin/
│   └── marketplace.json               # Plugin definition (name must be "startup")
├── startup-design/                    # Skill: startup:startup-design
│   ├── SKILL.md                # Main skill file (~495 lines, 8 phases)
│   └── references/             # Supporting documents loaded on demand
│       ├── research-principles.md
│       ├── research-wave-1-market.md
│       ├── research-wave-2-competitors.md
│       ├── research-wave-3-customers.md
│       ├── research-wave-4-distribution.md
│       ├── research-synthesis.md
│       └── frameworks.md
├── CLAUDE.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Key Conventions

### Naming Convention

- **Plugin name** (`startup`): defined in `.claude-plugin/marketplace.json` → becomes the namespace prefix
- **Skill name** (`startup-design`): defined in `SKILL.md` frontmatter → must match directory name
- **Command**: `/startup:startup-design` — `plugin-name:skill-name`
- Future skills go in the same repo as separate directories (e.g. `startup-pitch/`, `startup-growth/`)

### Skill Format

- `SKILL.md` uses YAML frontmatter with `name` and `description` fields
- `name` must match directory name exactly (lowercase, hyphens)
- `description` must be 1-1024 characters with trigger phrases
- Keep `SKILL.md` under 500 lines; move details to `references/`
- References are loaded progressively (only when needed for current phase)

### Research Architecture

Phase 3 (Market Research) uses 4 sequential waves of parallel agents:
- Wave 1: Market Landscape (3 agents)
- Wave 2: Competitive Analysis (3 agents)
- Wave 3: Customer & Demand (3 agents)
- Wave 4: Distribution (2 agents)

Each wave must complete before the next starts. Agents use WebSearch for real data.

### Output Structure

The skill generates files in subdirectories:
- `00-intake/` — Brief, brainstorm
- `01-discovery/` — Market research (raw + synthesized)
- `02-strategy/` — Lean canvas, positioning, business model, GTM
- `03-brand/` — Mission, vision, tone of voice
- `04-product/` — MVP, features, user journey
- `05-financial/` — Revenue, costs, projections
- `06-validation/` — Experiments, risks, scorecard

### Testing

Eval cases are in `startup-design-workspace/evals/evals.json`. To test:
1. Run each eval prompt through the skill
2. Grade against assertions in `eval_metadata.json`
3. Compare with/without skill performance

## Git Workflow

### Commit Messages

Follow conventional commits:
- `feat: add new phase or capability`
- `fix: improve skill instructions`
- `docs: update README or CLAUDE.md`
- `test: add or update eval cases`

### Branch Naming

- `feature/description`
- `fix/description`
- `docs/description`
