# AGENTS.md

Guidelines for AI agents working in this repository.

## Repository Overview

This repository contains the **startup-design** skill — a comprehensive startup design and idea validation workflow for AI agents.

- **Name**: Startup Design Skill
- **GitHub**: [ferdinandobons/startup-skill](https://github.com/ferdinandobons/startup-skill)
- **Creator**: Ferdinando Bons
- **License**: MIT

## Repository Structure

```
startup-skill/
├── startup-design/
│   ├── SKILL.md              # Main skill file (~495 lines)
│   └── references/           # Supporting documents (loaded on demand)
│       ├── research-principles.md    # ~60 lines
│       ├── research-wave-1-market.md # ~130 lines
│       ├── research-wave-2-competitors.md # ~170 lines
│       ├── research-wave-3-customers.md   # ~170 lines
│       ├── research-wave-4-distribution.md # ~110 lines
│       ├── research-synthesis.md     # ~90 lines
│       └── frameworks.md            # ~110 lines
├── CLAUDE.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Skill Specification

The skill follows standard SKILL.md format with YAML frontmatter:

```yaml
---
name: startup-design
description: Design, validate, and plan a startup from scratch...
---
```

### Frontmatter Constraints

| Field | Required | Constraints |
|-------|----------|-------------|
| `name` | Yes | 1-64 chars, lowercase `a-z`, numbers, hyphens. Must match directory name. |
| `description` | Yes | 1-1024 chars. Include trigger phrases. |

### Progressive Loading

Reference files are loaded on demand — only read the file needed for the current phase:
- Phase 3 Wave 1: read `research-principles.md` + `research-wave-1-market.md`
- Phase 3 Wave 2: read `research-wave-2-competitors.md`
- Phase 4: read `frameworks.md`
- Never load all reference files at once

## Writing Style

- Direct and instructional
- Specific over vague — quantify everything
- Honest over encouraging — surface real risks
- Actionable — every section should tell the founder what to do next
- No filler or generic platitudes

## Testing

Eval cases are in `startup-design-workspace/evals/evals.json` (5 test cases). Run evals by:
1. Spawning an agent with the eval prompt
2. Grading outputs against assertions
3. Comparing with/without skill results

## Git Workflow

- Branch naming: `feature/`, `fix/`, `docs/`
- Commit messages: conventional commits (`feat:`, `fix:`, `docs:`, `test:`)
- Always create new commits, never amend
