# CLAUDE.md

Guidelines for AI agents working in this repository.

## Repository Overview

This repository contains the **startup** plugin for AI agents. The plugin namespace is `startup`, and it includes multiple skills organized in 3 categories: Design, Analyze, and Build.

- **Name**: Startup Skills
- **GitHub**: [ferdinandobons/startup-skill](https://github.com/ferdinandobons/startup-skill)
- **Creator**: Ferdinando Bons
- **License**: MIT

## Skill Taxonomy

| Category | Purpose | Skills |
|----------|---------|--------|
| **Design** | Full process, idea to validated plan | `startup-design` |
| **Analyze** | Deep standalone analysis of one area | `startup-competitors`, `startup-positioning` (planned) |
| **Build** | Post-validation execution tools | `startup-pitch` (planned) |

## Repository Structure

```
startup-skill/                         # Plugin namespace (startup:*)
├── .claude-plugin/
│   └── marketplace.json               # Plugin definition (name must be "startup")
├── startup-design/                    # Skill: startup:startup-design
│   ├── SKILL.md                       # Main skill file (~495 lines, 8 phases)
│   └── references/                    # Supporting documents loaded on demand
│       ├── research-principles.md
│       ├── research-wave-1-market.md
│       ├── research-wave-2-competitors.md
│       ├── research-wave-3-customers.md
│       ├── research-wave-4-distribution.md
│       ├── research-synthesis.md
│       └── frameworks.md
├── startup-competitors/               # Skill: startup:startup-competitors
│   ├── SKILL.md                       # Main skill file (~190 lines, 3 waves)
│   └── references/
│       ├── research-principles.md
│       ├── research-wave-1-profiles-pricing.md
│       ├── research-wave-2-sentiment-mining.md
│       ├── research-wave-3-gtm-signals.md
│       └── research-synthesis.md
├── CLAUDE.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Key Conventions

### Naming Convention

- **Plugin name** (`startup`): defined in `.claude-plugin/marketplace.json` → becomes the namespace prefix
- **Skill name** (`startup-design`, `startup-competitors`): defined in `SKILL.md` frontmatter → must match directory name
- **Command**: `/startup:startup-design`, `/startup:startup-competitors` — `plugin-name:skill-name`
- Future skills go in the same repo as separate directories (e.g. `startup-pitch/`, `startup-positioning/`)

### Skill Format

- `SKILL.md` uses YAML frontmatter with `name` and `description` fields
- `name` must match directory name exactly (lowercase, hyphens)
- `description` must be 1-1024 characters with trigger phrases
- Keep `SKILL.md` under 500 lines; move details to `references/`
- References are loaded progressively (only when needed for current phase)
- Reference files use `research-wave-N-` prefix for consistency across skills

### Research Architecture

**startup-design** Phase 3 uses 4 sequential waves of parallel agents:
- Wave 1: Market Landscape (3 agents)
- Wave 2: Competitive Analysis (3 agents)
- Wave 3: Customer & Demand (3 agents)
- Wave 4: Distribution (2 agents)

**startup-competitors** uses 3 sequential waves of parallel agents:
- Wave 1: Competitor Profiles + Pricing Intelligence (2 agents)
- Wave 2: Customer Sentiment Mining (2 agents)
- Wave 3: GTM & Strategic Signals (2 agents)

Each wave must complete before the next starts. Agents use WebSearch for real data. Both skills support Claude.ai (sequential fallback) and Knowledge-Based Mode when WebSearch is unavailable.

### Output Structure

**startup-design** generates files in subdirectories:
- `00-intake/` — Brief, brainstorm
- `01-discovery/` — Market research (raw + synthesized)
- `02-strategy/` — Lean canvas, positioning, business model, GTM
- `03-brand/` — Mission, vision, tone of voice
- `04-product/` — MVP, features, user journey
- `05-financial/` — Revenue, costs, projections
- `06-validation/` — Experiments, risks, scorecard

**startup-competitors** generates files in `{project-name}/`:
- `intake.md` — Product and market context
- `competitors-report.md` — Main deliverable with strategic analysis
- `competitive-matrix.md` — Feature comparison table
- `pricing-landscape.md` — Pricing analysis and positioning
- `battle-cards/{competitor}.md` — Per-competitor one-pagers
- `raw/` — Raw research data from each wave

### Integration Between Skills

`startup-competitors` can detect and leverage prior `startup-design` output. If files like `01-discovery/competitor-landscape.md` exist, it uses them as a starting point instead of re-interviewing.

### Testing

Eval cases are in `{skill}-workspace/evals/evals.json`. To test:
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
