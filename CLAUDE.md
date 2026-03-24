# CLAUDE.md

Guidelines for AI agents working in this repository.

## Repository Overview

This repository contains the **startup** plugin for AI agents. The plugin namespace is `startup`, and it includes multiple skills organized in 3 categories: Design, Analyze, and Build (4 skills total).

- **Name**: Startup Skills
- **GitHub**: [ferdinandobons/startup-skill](https://github.com/ferdinandobons/startup-skill)
- **Creator**: Ferdinando Bons
- **License**: MIT

## Skill Taxonomy

| Category | Purpose | Skills |
|----------|---------|--------|
| **Design** | Full process, idea to validated plan | `startup-design` |
| **Analyze** | Deep standalone analysis of one area | `startup-competitors`, `startup-positioning` |
| **Build** | Post-validation execution tools | `startup-pitch` |

## Repository Structure

```
startup-skill/                         # Plugin namespace (startup:*)
├── .claude-plugin/
│   └── marketplace.json               # Plugin definition (name must be "startup")
├── startup-design/                    # Skill: startup:startup-design
│   ├── SKILL.md                       # Main skill file (~522 lines, 8 phases)
│   └── references/                    # Supporting documents loaded on demand
│       ├── research-principles.md
│       ├── research-scaling.md
│       ├── research-wave-1-market.md
│       ├── research-wave-2-competitors.md
│       ├── research-wave-3-customers.md
│       ├── research-wave-4-distribution.md
│       ├── research-synthesis.md
│       ├── verification-agent.md
│       └── frameworks.md
├── startup-competitors/               # Skill: startup:startup-competitors
│   ├── SKILL.md                       # Main skill file (~220 lines, 3 waves)
│   └── references/
│       ├── research-principles.md
│       ├── research-scaling.md
│       ├── research-wave-1-profiles-pricing.md
│       ├── research-wave-2-sentiment-mining.md
│       ├── research-wave-3-gtm-signals.md
│       ├── research-synthesis.md
│       ├── verification-agent.md
│       └── honesty-protocol.md
├── startup-positioning/               # Skill: startup:startup-positioning
│   ├── SKILL.md                       # Main skill file (~240 lines, 2 waves)
│   └── references/
│       ├── research-principles.md
│       ├── research-scaling.md
│       ├── research-wave-1-alternatives.md
│       ├── research-wave-2-market-frame.md
│       ├── research-synthesis.md
│       ├── verification-agent.md
│       ├── frameworks.md
│       └── honesty-protocol.md
├── startup-pitch/                     # Skill: startup:startup-pitch
│   ├── SKILL.md                       # Main skill file (~370 lines, 2 waves)
│   └── references/
│       ├── research-principles.md
│       ├── research-scaling.md
│       ├── research-wave-1-audience-narrative.md
│       ├── research-wave-2-competitive-framing.md
│       ├── research-synthesis.md
│       ├── verification-agent.md
│       ├── pitch-frameworks.md
│       └── honesty-protocol.md
├── CLAUDE.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Key Conventions

### Naming Convention

- **Plugin name** (`startup`): defined in `.claude-plugin/marketplace.json` → becomes the namespace prefix
- **Skill name** (`startup-design`, `startup-competitors`): defined in `SKILL.md` frontmatter → must match directory name
- **Command**: `/startup:startup-design`, `/startup:startup-competitors`, `/startup:startup-positioning`, `/startup:startup-pitch` — `plugin-name:skill-name`
- Future skills go in the same repo as separate directories

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

**startup-positioning** uses 2 sequential waves of parallel agents:
- Wave 1: Competitive Alternatives + Customer Intelligence (2 agents)
- Wave 2: Market Frame + Trends (2 agents)

**startup-pitch** uses 2 sequential waves of parallel agents:
- Wave 1: Audience & Narrative Intelligence (2 agents)
- Wave 2: Competitive Framing & Why Now (2 agents)

Each wave must complete before the next starts. Agents use WebSearch for real data. All skills support Claude.ai (sequential fallback) and Knowledge-Based Mode when WebSearch is unavailable.

**Research Scaling:** All skills dynamically adjust research depth. After intake, a complexity score (3-9) maps to Light/Standard/Deep tiers, changing agent count and search rounds per wave. Users can override. See each skill's `references/research-scaling.md`.

**Verification Agent:** All skills run a V1: Verification agent after synthesis. It audits deliverables for consistency, unlabeled claims, and skill-specific coherence. Critical issues pause for user review. See each skill's `references/verification-agent.md`.

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

**startup-positioning** generates files in `{project-name}/`:
- `intake.md` — Product and market context
- `positioning-doc.md` — Main deliverable (Dunford 5 components)
- `positioning-statement.md` — Moore + Neumeier statements + elevator pitch
- `competitive-alternatives.md` — JTBD-informed alternatives map
- `market-category-analysis.md` — Category candidates + recommendation
- `raw/` — Raw research data from each wave

**startup-pitch** generates files in `{project-name}/`:
- `intake.md` — Product, team, and pitch context
- `pitch-full.md` — Full 10-minute pitch narrative
- `pitch-5min.md` — Compressed 5-minute version
- `pitch-2min.md` — Verbal 2-minute pitch script
- `pitch-1min.md` — Elevator pitch (formal + casual)
- `pitch-email.md` — Investor cold email + follow-up
- `pitch-appendix.md` — Q&A preparation, objection handling
- `pitch-scorecard.md` — Pitch quality scoring rubric
- `raw/` — Raw research data from each wave

### Integration Between Skills

`startup-competitors` can detect and leverage prior `startup-design` output. If files like `01-discovery/competitor-landscape.md` exist, it uses them as a starting point instead of re-interviewing.

`startup-positioning` can detect and leverage output from BOTH `startup-design` (intake, discovery, strategy) and `startup-competitors` (battle cards, pricing landscape). It uses prior data as a head start and skips redundant intake questions.

`startup-pitch` can detect and leverage output from ALL three other skills. `startup-design` is the recommended prior work (provides market data, business model, validation scorecard). It also reads `startup-competitors` (battle cards for Q&A prep) and `startup-positioning` (positioning statements, messaging hierarchy).

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
