# Contributing

Thanks for your interest in contributing to Startup Skills! This guide will help you improve existing skills or add new capabilities.

## Ways to Contribute

- **Improve skill instructions** — Make phases clearer, fix edge cases
- **Add reference files** — New frameworks, research templates
- **Improve research agents** — Better search queries, output formats
- **Add eval cases** — New test scenarios for different startup types
- **Fix bugs** — Report or fix issues with the skill

## Getting Started

1. Fork the repository
2. Clone your fork
3. Create a feature branch (`git checkout -b feature/your-improvement`)

## Skill Structure

Each skill follows the same directory pattern:

```
{skill-name}/
├── SKILL.md           # Main skill file (keep under 500 lines)
└── references/        # Supporting documents loaded on demand
    ├── research-principles.md
    ├── research-wave-*.md
    ├── research-synthesis.md
    └── frameworks.md (if applicable)
```

Current skills: `startup-design/`, `startup-competitors/`, `startup-positioning/`, `startup-pitch/`.

### Guidelines

- **SKILL.md** should stay under 500 lines. Move detailed content to `references/`
- **Reference files** should be self-contained and loaded only when needed
- **YAML frontmatter** must have valid `name` and `description` fields
- `name` must match directory name exactly (lowercase, hyphens only)
- `description` should include trigger phrases for skill discovery

## Testing Your Changes

1. Start a conversation with Claude Code in the repo directory
2. Test with different startup ideas (vague, detailed, non-English)
3. Verify the skill triggers correctly
4. Check that outputs follow the expected directory structure
5. Confirm PROGRESS.md is updated properly

### Eval Cases

Eval cases for each skill are in `{skill-name}-workspace/evals/evals.json`. Example from startup-design:

| Test | Scenario | Phases Tested |
|------|----------|---------------|
| 1 | Vague idea (mechanic app) | Phase 1 |
| 2 | Detailed B2B (invoice AI) | Phase 1 + 2 |
| 3 | Italian language (food marketplace) | Phase 1 |
| 4 | Validation focus (Slack extension) | Phase 1 + 2 |
| 5 | Checkpoint resume (parking app) | Phase 4 |

## Submitting Your Contribution

1. Make your changes
2. Test locally with an AI agent
3. Submit a pull request using the appropriate template

## Release Checklist

When creating a new release:

- [ ] Rebuild zip files for each changed skill:
  - `zip -r startup-design.zip startup-design/`
  - `zip -r startup-competitors.zip startup-competitors/`
  - `zip -r startup-positioning.zip startup-positioning/`
  - `zip -r startup-pitch.zip startup-pitch/`
- [ ] Create a git tag: `git tag -a vX.Y.Z -m "description"`
- [ ] Push code and tag: `git push origin main && git push origin vX.Y.Z`
- [ ] Create a GitHub release and attach zip files as assets (Claude.ai users download these)

The zip files are used by Claude.ai web app users who install skills via Settings → Skills → Add Skill. They must be updated with every release that changes skill files.

## Quality Checklist

- [ ] `SKILL.md` is under 500 lines
- [ ] YAML frontmatter is valid
- [ ] `name` matches directory name
- [ ] No sensitive data or credentials
- [ ] Tested locally with AI agent
- [ ] Changes are focused and minimal
- [ ] Zip files rebuilt for any changed skills

## Questions?

Open an issue if you have questions or need help with your contribution.
