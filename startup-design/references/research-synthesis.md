# Research Synthesis Protocol

After ALL waves complete (10-11 agents, depending on whether A3/Regulatory was skipped), synthesize the raw findings into polished deliverables. This step creates the real analytical value — it's not copying, it's connecting.

## How to Synthesize

1. **Read all raw files** in `01-discovery/raw/` before writing anything.
2. **Look for patterns** across sources: what themes repeat? What surprised you?
3. **Identify contradictions** between sources and explain which you trust more and why.
4. **Connect the dots** between research areas: how do competitive gaps connect to customer pains? How do market trends affect the go-to-market?
5. **Highlight strategic implications** — don't just report facts; say what they mean for this startup.
6. **Rate your confidence** for each major finding: High (multiple Tier 1 sources agree), Medium (some evidence but gaps), Low (limited data, mostly inferred).
7. **Aggregate data gaps** from all raw files and present them clearly — these become inputs for Phase 8 (Validation).

## Output Files

### `01-discovery/market-analysis.md`
Synthesize from: `raw/market-size.md`, `raw/trends.md`, `raw/regulatory.md`, `raw/geographic.md`

Structure:
- **Executive summary** (5-sentence overview of the market opportunity)
- **Market size** with TAM/SAM/SOM breakdown and confidence ratings
- **Growth trajectory** with key drivers and headwinds
- **Market maturity assessment** (emerging / growing / mature / declining)
- **Unit economics benchmarks** (carried from market sizing, used by Phase 7)
- **Regulatory summary** (key requirements, compliance costs, timeline)
- **Geographic analysis** (beachhead market, expansion path)
- **Timing assessment:** why now? What tailwinds and headwinds exist?
- **Data gaps** aggregated from all market-related research

### `01-discovery/competitor-landscape.md`
Synthesize from: `raw/direct-competitors.md`, `raw/indirect-competitors.md`, `raw/competitor-gtm.md`

Structure:
- **Competitive overview** (how crowded, market concentration, overall threat level)
- **Competitor comparison matrix** (features × competitors table)
- **Positioning map** (describe how competitors position themselves, where the whitespace is)
- **Competitor GTM summary** (what acquisition channels work, what's saturated)
- **Platform risk assessment** (which platforms could absorb our functionality)
- **Switching cost analysis** (what keeps people on current solutions)
- **Strategic recommendations:** where to compete, where to avoid, how to differentiate
- **Vulnerability analysis:** which competitors are weakest and why — where can we win?
- **Data gaps**

### `01-discovery/target-audience.md`
Synthesize from: `raw/customer-voice.md`, `raw/target-audience.md`, `raw/demand-signals.md`

Structure:
- **Primary persona** (vivid, data-backed, with representative quote)
- **Secondary persona** (if applicable)
- **Anti-persona** (who NOT to target)
- **Customer pain hierarchy** (ranked by frequency × intensity, from customer voice)
- **Jobs-to-be-done framework** (functional, social, emotional)
- **Language map** (exact words customers use — feed directly into copywriting)
- **Buying behavior** (decision process, criteria, cycle length, objections)
- **Where to reach them** (ranked channels with density and cost)
- **Demand validation** (search trends, WTP evidence, market validation score)
- **Data gaps**

### `01-discovery/industry-trends.md`
Synthesize from: `raw/trends.md`, `raw/regulatory.md`, `raw/demand-signals.md`

Structure:
- **Macro trends** affecting the industry (with timeline and impact assessment)
- **Technology shifts** and their adoption curve
- **Investment and M&A signals** (what smart money is doing)
- **Behavioral shifts** in target customers
- **Regulatory trajectory** (direction of travel, not just current state)
- **What this means for our startup** — explicit strategic implications
- **Timing scorecard:** is now the right time? Rate: tailwinds vs. headwinds
- **Data gaps**

### `01-discovery/confidence-dashboard.md`
Synthesize from: ALL raw files across all waves.

Structure:
- **Overview** — How much of the analysis rests on solid ground vs. thin ice
- **Claim-level confidence** table:

| Claim | Source Tier | # Corroborating Sources | Confidence | Data Age |
|-------|-----------|------------------------|------------|----------|
| {major claim from research} | 1/2/3 | {count} | High/Medium/Low | {date or range} |

- **Highest confidence findings** — Claims backed by multiple Tier 1 sources
- **Lowest confidence findings** — Claims based on single sources, inferred data, or old information
- **Critical unknowns** — Things we don't know that could change the strategy
- **Recommendations** — What the founder should verify first, and how

This file helps the founder understand where they're standing on solid ground vs. making decisions based on weak data. It's the meta-layer above the other 4 deliverables.

---

## Cross-Document Connections

After writing all 4 files, add a "Strategic Connections" section at the end of each that links to insights from the other documents. For example:

- In market-analysis.md: "The growth in [trend X] (see industry-trends.md) creates an opening in [segment Y] that [competitor Z] (see competitor-landscape.md) hasn't addressed."
- In target-audience.md: "The pricing sensitivity found here aligns with the $X-Y range from competitor pricing analysis (see competitor-landscape.md)."

These connections help Phase 4 (Strategy) build on concrete research rather than abstract claims.

## Post-Synthesis Verification

After writing all deliverables, run the Verification Agent protocol. See `references/verification-agent.md` for the full process. The verification step checks all deliverables for unlabeled claims, internal contradictions, confidence rating consistency, and startup-design-specific cross-phase coherence (strategy reflects market data, product reflects customer pains, financial reflects business model, validation covers identified risks).

## Cleanup

Keep the `raw/` directory for reference. Note in PROGRESS.md that raw research files are available at `01-discovery/raw/`.
