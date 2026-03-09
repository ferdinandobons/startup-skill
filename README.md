# Startup Skills for AI Agents

AI agent skills for startup design, validation, and competitive intelligence. Built for founders, solopreneurs, and product people who want to make better decisions with real data. Works with [Claude Code](https://claude.ai/claude-code) and any agent that supports skills.

**Contributions welcome!** Found a way to improve a skill or have a new idea? [Open a PR](#contributing).

Run into a problem or have a question? [Open an issue](https://github.com/ferdinandobons/startup-skill/issues).

## Available Skills

```
startup (plugin)
│
├── DESIGN — Full process, idea to validated plan
│   └── startup-design             Complete startup design (8 phases)
│
├── ANALYZE — Deep standalone analysis
│   └── startup-competitors        Competitive intelligence (3 research waves)
│
└── 🔜 Coming soon
    ├── startup-positioning        Positioning strategy (April Dunford framework)
    └── startup-pitch              Pitch deck generation
```

| Skill | Description |
|-------|-------------|
| [startup-design](startup-design/) | Takes a raw idea through 8 phases: intake, brainstorm, market research (11 parallel agents), strategy, brand, product, financial, validation. Produces a complete set of markdown docs. |
| [startup-competitors](startup-competitors/) | Deep competitive intelligence using 3 research waves: competitor profiles + pricing, customer sentiment mining (G2, Reddit, HN), GTM & strategic signals. Produces battle cards, pricing landscape, and feature matrix. |

## Installation

### Option 1: Claude Code Plugin (Recommended)

```bash
claude plugin marketplace add ferdinandobons/startup-skill
claude plugin install startup@startup-skill
```

### Option 2: Claude.ai (Web App)

1. Download `.skill` files from the [Releases page](https://github.com/ferdinandobons/startup-skill/releases)
2. Open [claude.ai](https://claude.ai) → **Settings → Skills**
3. Upload the `.skill` files

### Option 3: CLI Install

```bash
npx skills add ferdinandobons/startup-skill
```

### Option 4: Clone and Copy

```bash
git clone https://github.com/ferdinandobons/startup-skill.git
cp -r startup-skill/startup-design .agents/skills/
cp -r startup-skill/startup-competitors .agents/skills/
```

### Option 5: Git Submodule

```bash
git submodule add https://github.com/ferdinandobons/startup-skill.git .agents/startup-skill
```

### Option 6: SkillKit (Multi-Agent)

```bash
npx skillkit install ferdinandobons/startup-skill
```

## Usage

Just describe what you need — skills trigger automatically:

```
"I have an idea for a SaaS that helps real estate agents automate follow-up emails.
Can you help me figure out if it's worth building?"
→ Uses startup-design

"Who are my competitors in the project management space for creative agencies?"
→ Uses startup-competitors

"Resume from checkpoint"
→ Resumes a previous session

"Quick validation of this idea: [your idea]. Fast track mode."
→ Uses startup-design in compressed mode
```

Or invoke directly: `/startup:startup-design`, `/startup:startup-competitors`

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

1. Fork the repository
2. Create a feature branch
3. Make your changes and test with an AI agent
4. Submit a pull request

## License

[MIT](LICENSE)
