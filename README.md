# Startup Design Skill

An AI agent skill for comprehensive startup design and idea validation. Takes a raw idea from concept to validated business plan through structured research, strategic frameworks, and honest assessment.

Built for founders, solopreneurs, and product people who want to validate ideas rigorously before investing time and money. Works with [Claude Code](https://claude.ai/claude-code) and any agent that supports skills.

**Contributions welcome!** Found a way to improve the skill or have a new idea? [Open a PR](#contributing).

Run into a problem or have a question? [Open an issue](https://github.com/ferdinandobons/startup-skill/issues).

## What It Does

The skill guides an AI agent through 8 structured phases, producing a complete set of markdown documents:

```
INTAKE -> BRAINSTORM -> RESEARCH -> STRATEGY -> BRAND -> PRODUCT -> FINANCIAL -> VALIDATION
```

Each phase builds on the previous one. Sessions can be interrupted and resumed from checkpoints.

### Phases

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

### Modes

- **Full Mode** (default): All 8 phases, thorough analysis
- **Fast Track**: Compressed version for quick go/no-go decisions

### Features

- Multi-language support (auto-detects from user input, defaults to English)
- Progress tracking via `PROGRESS.md` for session resumption
- Multi-agent parallel web research with source quality tiers
- Strategic frameworks: Lean Canvas, April Dunford Positioning, Value Proposition Canvas, RICE/MoSCoW
- Honest assessment with risk analysis and validation experiments

## Installation

### Option 1: Claude.ai (Web App)

Use this skill directly in Claude.ai without any terminal or CLI:

1. Download the latest `startup-design.zip` from the [Releases page](https://github.com/ferdinandobons/startup-skill/releases)
2. Open [claude.ai](https://claude.ai) and go to **Settings → Skills**
3. Click **"Add Skill"** and upload the `.zip` file
4. Start a new conversation and describe your startup idea — the skill triggers automatically

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
claude plugin install startup
```

### Option 4: Clone and Copy

Clone the entire repo and copy the skill folder:

```bash
git clone https://github.com/ferdinandobons/startup-skill.git
cp -r startup-skill/startup-design .agents/skills/
```

### Option 5: Git Submodule

Add as a submodule for easy updates:

```bash
git submodule add https://github.com/ferdinandobons/startup-skill.git .agents/startup-skill
```

Then reference the skill from `.agents/startup-skill/startup-design/`.

### Option 6: Fork and Customize

1. Fork this repository
2. Customize the skill for your specific needs
3. Clone your fork into your projects

### Option 7: SkillKit (Multi-Agent)

Use [SkillKit](https://github.com/rohitg00/skillkit) to install skills across multiple AI agents (Claude Code, Cursor, Copilot, etc.):

```bash
# Install the skill (auto-detects Claude Code, Cursor, Copilot, etc.)
npx skillkit install ferdinandobons/startup-skill
```

## Usage

Start a conversation with your AI agent and describe your startup idea:

```
I have an idea for a SaaS that helps real estate agents automate their follow-up emails using AI.
I've been an agent for 12 years and I know the pain. Can you help me figure out if it's worth building?
```

The skill will automatically trigger and guide you through the intake interview, then proceed phase by phase.

To resume a previous session:

```
Resume from checkpoint
```

For a quick validation:

```
I need a quick validation of this idea: [your idea]. Fast track mode.
```

## Repository Structure

```
startup-skill/
├── .claude-plugin/
│   └── marketplace.json                   # Plugin marketplace definition
├── startup-design/
│   ├── SKILL.md                          # Main skill file (8 phases)
│   └── references/
│       ├── research-principles.md        # Cross-cutting research rules
│       ├── research-wave-1-market.md     # Market sizing agents
│       ├── research-wave-2-competitors.md # Competitive analysis agents
│       ├── research-wave-3-customers.md  # Customer research agents
│       ├── research-wave-4-distribution.md # Distribution agents
│       ├── research-synthesis.md         # How to synthesize findings
│       └── frameworks.md                 # Strategic frameworks
├── CLAUDE.md                             # Agent guidelines
├── CONTRIBUTING.md                       # How to contribute
├── LICENSE                               # MIT License
└── README.md                             # This file
```

## Eval Results

The skill has been tested across 5 eval scenarios comparing skill-guided output vs. baseline:

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
