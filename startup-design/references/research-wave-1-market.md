# Wave 1: Market Landscape (3 agents)

Read `research-principles.md` first for cross-cutting rules on source quality, cross-referencing, and quantification.

---

## Agent A1: Market Sizing & Economics

```
Research task: Deep market sizing for {industry/product category}
Context: We're designing a startup that {one-sentence description}.
Target market: {geography}, {customer segment}

RESEARCH PROTOCOL — perform these searches in sequence, each building on the last:

ROUND 1 — Broad market overview (2-3 searches):
- "{broad category} market size {current year}"
- "{broad category} market report {current year}"
- "{industry} industry overview statistics"
Capture: TAM figures, growth rates, key players. Note which reports are cited most.

ROUND 2 — Segment drill-down (2-3 searches):
- "{specific segment} market size {geography}"
- "{specific segment} spending trends"
- "{customer type} budget for {product category}"
Capture: SAM figures, segment-specific growth, spending patterns per customer.

ROUND 3 — Unit economics research (2-3 searches):
- "{product category} average contract value"
- "{product category} customer acquisition cost benchmarks"
- "{product category} churn rate benchmarks"
- "{product category} pricing survey"
Capture: Industry benchmarks for ACV, CAC, LTV, churn. These ground the financial model later.

ROUND 4 — Reality check (1-2 searches):
- "{product category} market challenges {current year}"
- "why {product category} startups fail"
Capture: Headwinds, saturation signals, common failure modes.

OUTPUT FORMAT:
# Market Sizing: {industry}

## TAM (Total Addressable Market)
- Figure: $X (Source, Date)
- Figure: $Y (Source, Date) — [note if different and why]
- Growth rate: X% CAGR (Source)

## SAM (Serviceable Addressable Market)
- Segment: {specific segment}
- Figure: $X (Source, Date)
- Reasoning: [how SAM was derived from TAM]

## SOM (Serviceable Obtainable Market)
- Realistic Year 1 capture: $X
- Reasoning: [based on comparable company trajectories]

## Unit Economics Benchmarks
- Average contract value: $X/mo or $X/yr
- Customer acquisition cost: $X
- Lifetime value: $X
- Churn rate: X%/mo or X%/yr
- [Note if benchmarks are for this specific segment or broader industry]

## Market Headwinds & Risks
- [List specific challenges with sources]

## Source Quality Assessment
- [Rate each major source as Tier 1/2/3 and note any data gaps]

## Data Gaps
- [List anything you couldn't find with suggested ways to fill the gap]

Save to: {project-name}/01-discovery/raw/market-size.md
```

---

## Agent A2: Industry Trends & Timing

```
Research task: Industry trends, timing signals, and future trajectory for {industry}
Context: We're designing a startup that {one-sentence description}.

RESEARCH PROTOCOL — perform these searches in sequence:

ROUND 1 — Technology trends (2-3 searches):
- "{industry} technology trends {current year}"
- "AI impact on {industry}"
- "{industry} innovation report {current year}"
Capture: Which technologies are reshaping the space. Adoption curves. Maturity levels.

ROUND 2 — Investment & M&A activity (2-3 searches):
- "{industry} startup funding {current year}"
- "{industry} acquisitions {current year}"
- "{product category} venture capital deals"
Search Crunchbase, PitchBook summaries, TechCrunch funding roundups.
Capture: Deal sizes, acquiring companies (signals of where big players see value), accelerating or decelerating investment.

ROUND 3 — Behavioral shifts (2 searches):
- "{customer type} changing expectations {industry}"
- "remote work impact on {industry}" OR "{customer type} digital adoption"
Capture: How customer behavior is evolving. New expectations. Generational shifts.

ROUND 4 — Expert predictions (1-2 searches):
- "{industry} predictions {current year + 1}"
- "{industry} future outlook analyst"
Capture: Where credible analysts think this is heading. Consensus vs. contrarian views.

OUTPUT FORMAT:
# Industry Trends: {industry}

## Technology Trends
For each trend:
- Trend name and description
- Current adoption stage (early/growing/mature/declining)
- Impact on our startup (opportunity/threat/neutral)
- Timeline: when does this become mainstream?
- Source and date

## Investment Activity
- Total funding in space (last 12 months): $X across N deals
- Notable rounds: [company, amount, stage, date]
- Notable acquisitions: [acquirer → target, amount, date, strategic rationale]
- Investment trend: accelerating / stable / decelerating
- What this signals for our startup

## Behavioral Shifts
- [Specific shift with data]
- [How this affects demand for our product]

## Expert Predictions
- [Prediction, source, credibility assessment]

## Timing Assessment
- Is now a good time to enter this market? Why or why not?
- What would make the timing better or worse?

## Data Gaps
- [List anything you couldn't find]

Save to: {project-name}/01-discovery/raw/trends.md
```

---

## Agent A3: Regulatory & Compliance Landscape

Skip this agent if the startup has no obvious regulatory exposure. When in doubt, run it — better to discover regulatory requirements early than late.

```
Research task: Regulatory landscape for {industry} in {geography}
Context: We're designing a startup that {one-sentence description}.

RESEARCH PROTOCOL:

ROUND 1 — Current regulations (2-3 searches):
- "{industry} regulations {geography} {current year}"
- "{product type} compliance requirements"
- "{industry} licensing requirements {geography}"

ROUND 2 — Data & privacy (2 searches):
- "{industry} data privacy requirements"
- "GDPR CCPA impact on {industry}" OR "{industry} data handling regulations"

ROUND 3 — Upcoming changes (1-2 searches):
- "{industry} new regulations {current year}"
- "{industry} regulatory changes pending legislation"

ROUND 4 — Enforcement & precedent (1 search):
- "{industry} regulatory enforcement actions" OR "{industry} compliance fines"

OUTPUT FORMAT:
# Regulatory Landscape: {industry} in {geography}

## Current Regulations
For each regulation:
- Name and jurisdiction
- What it requires
- Who it applies to (does it apply to us at launch? At scale?)
- Compliance cost estimate
- Timeline to compliance

## Data & Privacy
- Applicable frameworks (GDPR, CCPA, HIPAA, etc.)
- Data handling requirements specific to this industry
- Impact on product architecture

## Upcoming Changes
- Pending legislation or proposed rules
- Expected timeline
- Potential impact

## Compliance Cost Estimate
- Minimum viable compliance: $X (what you need at launch)
- Full compliance: $X (what you need at scale)
- Certifications needed: [SOC 2, ISO 27001, HIPAA, etc.]

## Risk Assessment
- Regulatory risk level: Low / Medium / High
- Key regulatory risks for this specific startup

## Data Gaps
- [List anything you couldn't find]

Save to: {project-name}/01-discovery/raw/regulatory.md
```
