# Startup Skill

AI agent skills for startup design, validation, and competitive intelligence. Built for founders, solopreneurs, and product people who want to make better decisions with real data.

Works with [Claude Code](https://claude.ai/claude-code) and any agent that supports skills.

**Contributions welcome!** Found a way to improve a skill or have a new idea? [Open a PR](#contributing).

Run into a problem or have a question? [Open an issue](https://github.com/ferdinandobons/startup-skill/issues).

## Skill Categories

Skills are organized in 3 categories:

```
startup (plugin)
│
├── DESIGN — Full process, idea to validated plan
│   └── startup-design             ✅ Complete startup design (8 phases)
│
├── ANALYZE — Deep standalone analysis of one area
│   ├── startup-competitors        ✅ Competitive intelligence
│   ├── startup-positioning        🔜 Coming soon
│
└── BUILD — Post-validation, ready to execute
    └── startup-pitch              🔜 Coming soon
```

| Category | Purpose | When to Use |
|----------|---------|-------------|
| **Design** | Complete process from idea to validated business plan | Starting from scratch, exploring a new idea |
| **Analyze** | Deep analysis of a single dimension, standalone | Already have a startup, need specific intelligence |
| **Build** | Tools for executing after validation | Idea is validated, ready to build and present |

## Skills

### startup-design (Design)

The core skill. Takes a raw idea through 8 structured phases, producing a complete set of markdown documents:

```
INTAKE -> BRAINSTORM -> RESEARCH -> STRATEGY -> BRAND -> PRODUCT -> FINANCIAL -> VALIDATION
```

| Phase | What It Produces | Key Output Files |
|-------|-----------------|-----------------|
| 1. Intake Interview | Deep understanding of the idea, founder, and constraints | `00-intake/brief.md` |
| 2. Brainstorm | 5-8 variations of the idea before committing | `00-intake/brainstorm.md` |
| 3. Market Research | Multi-agent web research in 4 waves (11 agents) | `01-discovery/*.md` |
| 4. Strategy | Lean Canvas, positioning, business model, GTM | `02-strategy/*.md` |
| 5. Brand | Mission, vision, tone of voice, personality | `03-brand/*.md` |
| 6. Product | MVP definition, feature prioritization, user journey | `04-product/*.md` |
| 7. Financial | Revenue model, cost structure, projections | `05-financial/*.md` |
| 8. Validation | Experiments, risk analysis, scorecard | `06-validation/*.md` |

**Modes:** Full Mode (all 8 phases) or Fast Track (compressed for quick go/no-go decisions).

### startup-competitors (Analyze)

Deep competitive intelligence for any market. Goes far beyond basic competitor lists — analyzes pricing strategy, customer sentiment, GTM channels, and growth signals.

```
INTAKE -> RESEARCH (3 parallel waves) -> SYNTHESIS -> BATTLE CARDS
```

| Wave | What It Researches | Key Output |
|------|-------------------|------------|
| 1. Profiles + Pricing | Competitor deep-dives, pricing reverse-engineering, switching costs | `competitor-profiles.md`, `pricing-intelligence.md` |
| 2. Sentiment Mining | Review mining (G2, Capterra), forum mining (Reddit, HN), language map | `review-mining.md`, `forum-mining.md` |
| 3. GTM & Signals | Acquisition channels, content/SEO gaps, hiring patterns, funding trajectory | `gtm-analysis.md`, `strategic-signals.md` |

**Output:** Competitive report, feature matrix, pricing landscape, and per-competitor battle cards.

### startup-positioning (Analyze) — Coming Soon

Dedicated positioning strategy using April Dunford's complete framework. Not just "how to describe your product" — a deep process that maps competitive alternatives, unique attributes, value chains, and market categories.

**Output:** Positioning document + messaging framework reusable for landing pages, pitch decks, and ads.

### startup-pitch (Build) — Coming Soon

Structured pitch deck generation with narrative design, data integration, and slide-by-slide content. Supports investor pitch, customer pitch, and accelerator applications in multiple formats (5-slide lightning to 15-slide detailed).

**Output:** Complete slide content in markdown, ready for Keynote/Google Slides/Figma.

## Features

- Multi-language support (auto-detects from user input, defaults to English)
- Progress tracking via `PROGRESS.md` for session resumption
- Multi-agent parallel web research with source quality tiers
- Strategic frameworks: Lean Canvas, April Dunford Positioning, Value Proposition Canvas, RICE/MoSCoW
- Honest assessment with risk analysis and validation experiments
- Works in Claude Code (parallel agents) and Claude.ai (sequential fallback)

## Installation

### Option 1: Claude.ai (Web App)

Use skills directly in Claude.ai without any terminal or CLI:

1. Download the latest `.zip` from the [Releases page](https://github.com/ferdinandobons/startup-skill/releases)
2. Open [claude.ai](https://claude.ai) and go to **Settings → Skills**
3. Click **"Add Skill"** and upload the `.zip` file
4. Start a new conversation — skills trigger automatically

### Option 2: CLI Install

Use [npx skills](https://github.com/vercel-labs/skills) to install skills directly:

```bash
# Install the skill
npx skills add ferdinandobons/startup-skill

# List installed skills
npx skills list
```

This automatically installs to your `.agents/skills/` directory (and symlinks into `.claude/skills/` for Claude Code compatibility).

### Option 3: Claude Code Plugin

Install via Claude Code's built-in plugin system:

```bash
# From the Claude Code CLI
claude plugin marketplace add ferdinandobons/startup-skill
claude plugin install startup@startup-skill
```

### Option 4: Clone and Copy

Clone the entire repo and copy the skill folders:

```bash
git clone https://github.com/ferdinandobons/startup-skill.git
cp -r startup-skill/startup-design .agents/skills/
cp -r startup-skill/startup-competitors .agents/skills/
```

### Option 5: Git Submodule

Add as a submodule for easy updates:

```bash
git submodule add https://github.com/ferdinandobons/startup-skill.git .agents/startup-skill
```

### Option 6: Fork and Customize

1. Fork this repository
2. Customize the skills for your specific needs
3. Clone your fork into your projects

### Option 7: SkillKit (Multi-Agent)

Use [SkillKit](https://github.com/rohitg00/skillkit) to install skills across multiple AI agents (Claude Code, Cursor, Copilot, etc.):

```bash
# Install the skill (auto-detects Claude Code, Cursor, Copilot, etc.)
npx skillkit install ferdinandobons/startup-skill
```

## Usage

### Startup Design

Start a conversation and describe your startup idea:

```
I have an idea for a SaaS that helps real estate agents automate their follow-up emails using AI.
I've been an agent for 12 years and I know the pain. Can you help me figure out if it's worth building?
```

### Competitive Analysis

Ask for competitor research on any market:

```
I'm building a project management tool for creative agencies. Who are my competitors
and where are the gaps in the market?
```

### Resume a Session

```
Resume from checkpoint
```

### Fast Track

```
I need a quick validation of this idea: [your idea]. Fast track mode.
```

## Repository Structure

```
startup-skill/
├── .claude-plugin/
│   └── marketplace.json                    # Plugin marketplace definition
├── startup-design/                         # DESIGN: Full startup design process
│   ├── SKILL.md                           # Main skill file (8 phases)
│   └── references/
│       ├── research-principles.md         # Cross-cutting research rules
│       ├── research-wave-1-market.md      # Market sizing agents
│       ├── research-wave-2-competitors.md # Competitive analysis agents
│       ├── research-wave-3-customers.md   # Customer research agents
│       ├── research-wave-4-distribution.md # Distribution agents
│       ├── research-synthesis.md          # How to synthesize findings
│       └── frameworks.md                  # Strategic frameworks
├── startup-competitors/                    # ANALYZE: Competitive intelligence
│   ├── SKILL.md                           # Main skill file (3 waves)
│   └── references/
│       ├── research-principles.md         # Research rules
│       ├── research-wave-1-profiles-pricing.md  # Competitor profiles + pricing
│       ├── research-wave-2-sentiment-mining.md  # Review + forum mining
│       ├── research-wave-3-gtm-signals.md       # GTM + strategic signals
│       └── research-synthesis.md          # Synthesis + battle card templates
├── CLAUDE.md                              # Agent guidelines
├── CONTRIBUTING.md                        # How to contribute
├── LICENSE                                # MIT License
└── README.md                              # This file
```

## Eval Results

The startup-design skill has been tested across 5 eval scenarios comparing skill-guided output vs. baseline:

| Metric | With Skill | Without Skill |
|--------|-----------|---------------|
| Assertion Pass Rate | 100% (21/21) | 57% (12/21) |
| Structured Output | Always | Rarely |
| Interview Process | Multi-round, targeted | Single dump |
| Brainstorming | 5-8 variations | Skipped |
| Progress Tracking | Always | Never |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for details on how to contribute.

### Quick Start

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement-name`)
3. Make your changes
4. Test with an AI agent
5. Submit a pull request

## License

[MIT](LICENSE)
