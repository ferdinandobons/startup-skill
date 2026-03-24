# Research Scaling Protocol

Dynamic scaling adjusts research depth based on market complexity and user preference. Evaluated after intake, before research begins.

## Complexity Score

Assess three factors from the intake data:

| Factor | Low (1) | Medium (2) | High (3) |
|--------|---------|------------|----------|
| **Market breadth** | Ultra-niche, few players, well-defined segment | Defined market, moderate competition | Broad market, many segments, diverse players |
| **Known competitors** | 0-2 identified | 3-5 identified | 6+ identified |
| **Geographic scope** | Single country | Regional (e.g., Europe, North America) | Global or multi-region |

**Complexity score** = sum of the three factors (range: 3-9)

## Research Depth Tiers

| Tier | Score Range | Manual Trigger | Description |
|------|-----------|----------------|-------------|
| **Light** | 3-4 | User says "light", "quick", or "fast research" | Quick scan, fewer agents, 2-3 search rounds |
| **Standard** | 5-7 | Default (no override needed) | Current behavior, balanced depth |
| **Deep** | 8-9 | User says "deep", "thorough", or "deep research" | More agents, 5-6 search rounds, extra coverage |

**Manual override always wins.** If the user requests "light" on a score-9 market, use Light. If they request "deep" on a score-3 market, use Deep.

## User Communication

After calculating the score, show this to the user:

```
## Research Depth

Based on your intake, I've assessed the research complexity:

| Factor           | Assessment          | Score |
|------------------|---------------------|-------|
| Market breadth   | {description}       | {1-3} |
| Known competitors| {N} identified      | {1-3} |
| Geographic scope | {description}       | {1-3} |

**Complexity score: {X}/9 — recommended depth: {Light/Standard/Deep}**

You can override this. Here's what each depth means:

| Depth        | Agents | Searches per agent | Best for                                      |
|--------------|--------|--------------------|-----------------------------------------------|
| **Light**    | {N}    | 2-3 rounds         | Quick scan, niche markets, time-sensitive decisions |
| **Standard** | {N}    | 3-4 rounds         | Most cases, balanced depth vs. speed           |
| **Deep**     | {N}    | 5-6 rounds         | Crowded markets, high-stakes decisions, thorough due diligence |

→ Type **light**, **deep**, or **ok** to accept the recommendation.
```

The agent counts shown should reflect the actual numbers for this skill (see Wave Configuration below).

## Wave Configuration: startup-pitch

### Light (3-4 score or user override)

**Wave 1** (1 wave, 2 agents)
- A1: Audience, Narrative & Competitive Framing (merge A1+A2+B1 into one agent)
- A2: Why Now & Timing (B2, unchanged scope)

Merge both waves into a single wave since there's no dependency between them at this scale.

**Total: 2 agents** (vs. 4 Standard), 2-3 search rounds per agent

### Standard (5-7 score, default)

No changes to current wave structure:
- Wave 1: 2 agents (A1, A2)
- Wave 2: 2 agents (B1, B2)

**Total: 4 agents**, 3-4 search rounds per agent

### Deep (8-9 score or user override)

**Wave 1: Audience & Narrative** (3 agents)
- A1: Investor & Audience Intelligence (unchanged)
- A2: Comparable & Narrative Research (unchanged)
- A3: Pitch Benchmark Analysis (NEW: research how similar startups in this space pitched, what decks worked, what narratives raised money, typical round sizes and valuations)

**Wave 2: Competitive Framing & Why Now** (2 agents)
- B1: Competitive Framing for Pitch (unchanged)
- B2: Why Now & Market Timing (unchanged)

**Total: 5 agents**, 5-6 search rounds per agent

## PROGRESS.md

Record the selected tier in PROGRESS.md:

```markdown
- **Research Depth:** {Light/Standard/Deep} (score: {X}/9, {override: user request / auto})
```
