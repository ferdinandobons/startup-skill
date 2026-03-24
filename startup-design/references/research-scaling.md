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

## Wave Configuration: startup-design

### Light (3-4 score or user override)

**Wave 1: Market Landscape** (2 agents)
- A1: Market Sizing & Economics (unchanged)
- A2: Industry Trends, Timing & Regulatory (merge A2+A3 into one agent)

**Wave 2: Competitive Analysis** (2 agents)
- B1: Direct Competitor Deep-Dives (unchanged)
- B2: Indirect Competitors & GTM (merge B2+B3 into one agent)

**Wave 3: Customer & Demand** (2 agents)
- C1: Customer Voice & Pain Points (unchanged)
- C2: Demand Signals & Audience Profiling (merge C2+C3 into one agent)

**Wave 4: Distribution** (1 agent)
- D1: Distribution & Geographic Entry (merge D1+D2 into one agent)
- Skip Wave 4 entirely if market is local/single-country

**Total: 6-7 agents** (vs. 11 Standard), 2-3 search rounds per agent

### Standard (5-7 score, default)

No changes to current wave structure:
- Wave 1: 3 agents (A1, A2, A3)
- Wave 2: 3 agents (B1, B2, B3)
- Wave 3: 3 agents (C1, C2, C3)
- Wave 4: 2 agents (D1, D2)

**Total: 11 agents**, 3-4 search rounds per agent

### Deep (8-9 score or user override)

**Wave 1: Market Landscape** (4 agents)
- A1: Market Sizing & Economics (unchanged)
- A2: Industry Trends & Timing (unchanged)
- A3: Regulatory & Compliance (unchanged)
- A4: Adjacent Markets & Expansion (NEW: research adjacent verticals, whitespace, expansion paths)

**Wave 2: Competitive Analysis** (4 agents)
- B1: Direct Competitor Deep-Dives (unchanged)
- B2: Indirect Competitors & Substitutes (unchanged)
- B3: Competitor Go-to-Market (unchanged)
- B4: Emerging & Stealth Competitors (NEW: search for stealth startups, recent launches, pre-launch products in the space)

**Wave 3: Customer & Demand** (4 agents)
- C1: Customer Voice & Pain Points (unchanged)
- C2: Demand Signals & Market Validation (unchanged)
- C3: Target Audience Profiling (unchanged)
- C4: Pricing Deep-Dive (NEW: detailed pricing intelligence, WTP analysis, price sensitivity research)

**Wave 4: Distribution & Partnerships** (3 agents)
- D1: Distribution Channel Deep-Dive (unchanged)
- D2: Geographic & Market Entry (unchanged)
- D3: Strategic Partnership Mapping (NEW: potential partners, integration opportunities, channel partnerships)

**Total: 15 agents**, 5-6 search rounds per agent

## PROGRESS.md

Record the selected tier in PROGRESS.md:

```markdown
- **Research Depth:** {Light/Standard/Deep} (score: {X}/9, {override: user request / auto})
```
