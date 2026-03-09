# Startup Skills for AI Agents

Everything you need to validate and launch a startup — researched by AI agents, not guesswork.

These skills turn Claude into a startup analyst. They search the web, profile competitors, mine customer reviews, reverse-engineer pricing, and produce structured deliverables you can actually use: battle cards, financial projections, positioning docs, risk scorecards.

Works with [Claude Code](https://claude.ai/claude-code) and any agent that supports skills.

**Contributions welcome!** [Open a PR](#contributing) or [an issue](https://github.com/ferdinandobons/startup-skill/issues).

## Available Skills

| Skill | What you get |
|-------|-------------|
| [startup-design](startup-design/) | A complete startup plan: market research, strategy, brand, product definition, financial projections, and validation experiments. 8 phases, 11 research agents, one command. |
| [startup-competitors](startup-competitors/) | Battle cards for every competitor, a pricing landscape with reverse-engineered tiers, a feature matrix, and a strategic report — built from real reviews, forums, and web data. |

Coming soon: `startup-positioning` (April Dunford framework) and `startup-pitch` (investor deck generation).

## Usage

Describe what you need — skills trigger automatically:

```
"I want to build a SaaS for real estate agents that automates follow-up emails.
Is it worth building?"
→ startup-design runs the full 8-phase process

"Who are my competitors in the project management space for creative agencies?
I need battle cards and a pricing comparison."
→ startup-competitors profiles 5-8+ competitors across 3 research waves

"Quick validation — fast track mode."
→ startup-design runs a compressed go/no-go analysis
```

Or invoke directly: `/startup:startup-design`, `/startup:startup-competitors`

> **Token usage:** These skills run multiple research agents and can consume a large number of tokens. For the best experience, use [Claude Max 5x](https://claude.ai/upgrade). If a session hits the limit, just ask Claude to "resume from where you left off" — it will pick up the process.

## Installation

### Claude Code Plugin (Recommended)

```bash
claude plugin marketplace add ferdinandobons/startup-skill
claude plugin install startup@startup-skill
```

### Claude.ai (Web App)

Download `.skill` files from the [Releases page](https://github.com/ferdinandobons/startup-skill/releases), then upload in **Settings → Skills**.

### Other Methods

```bash
# CLI Install
npx skills add ferdinandobons/startup-skill

# Clone and copy
git clone https://github.com/ferdinandobons/startup-skill.git
cp -r startup-skill/startup-design .agents/skills/
cp -r startup-skill/startup-competitors .agents/skills/

# Git submodule
git submodule add https://github.com/ferdinandobons/startup-skill.git .agents/startup-skill

# SkillKit (works with Claude Code, Cursor, Copilot, etc.)
npx skillkit install ferdinandobons/startup-skill
```

## Updating

### Claude Code Plugin

```bash
claude plugin update startup@startup-skill
```

> If the update doesn't pick up new changes, refresh the marketplace source and reinstall:
> ```bash
> claude plugin uninstall startup@startup-skill
> claude plugin marketplace remove startup-skill
> claude plugin marketplace add ferdinandobons/startup-skill
> claude plugin install startup@startup-skill
> ```

### Claude.ai

Download the latest `.skill` files from the [Releases page](https://github.com/ferdinandobons/startup-skill/releases) and re-upload in **Settings → Skills**.

### CLI / SkillKit

Re-run the install command — it overwrites the previous version:

```bash
npx skills add ferdinandobons/startup-skill
# or
npx skillkit install ferdinandobons/startup-skill
```

### Git Submodule

```bash
git submodule update --remote .agents/startup-skill
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## License

[MIT](LICENSE)
