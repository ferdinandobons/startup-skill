# Wave 1: Audience & Narrative Intelligence

Read `research-principles.md` first.

---

## Agent A1: Investor & Audience Intelligence

```
Research task: Build investor audience profile for {product description} pitch
Context: {product summary from intake}
Target audience: {VC/angels/accelerator/demo day — from intake}
Stage: {pre-seed/seed/Series A — from intake}

RESEARCH PROTOCOL:

ROUND 1 — Fundraising landscape in this space (4-5 searches):
- "{product category} startup funding {current year}"
- "{product category} VC investments {current year}"
- "seed stage {product category} fundraise"
- "{product space} Series A metrics benchmarks"
- "what VCs look for in {product category} startups"

ROUND 2 — Specific audience research (3-4 searches):
If specific investors/funds are named:
- "{fund name} portfolio companies"
- "{fund name} investment thesis"
- "{investor name} blog pitch advice"
- "{fund name} demo day companies"

If no specific audience:
- "best investors {product category} {current year}"
- "{product category} angel investors"
- "{accelerator name} recent batch companies"

ROUND 3 — Stage-appropriate metrics (3-4 searches):
- "seed stage metrics investors expect {current year}"
- "{product category} startup benchmarks Series A"
- "what traction for seed round {product category}"
- "seed round size {product category} {current year}"
- "pre-seed vs seed metrics expectations"

ROUND 4 — Current climate (2-3 searches):
- "fundraising climate {current year} startups"
- "{product category} funding trends {current year}"
- "VC sentiment {product space} {current year}"

OUTPUT FORMAT:

## Investor Audience Profile

### Fundraising Landscape
- Current funding climate in {space}: {bullish/neutral/bearish}
- Recent notable rounds: {examples with amounts}
- Average round size at this stage: {range}
- Key metrics investors expect at this stage:
  - {metric 1}: {benchmark}
  - {metric 2}: {benchmark}
  - {metric 3}: {benchmark}

### Target Investor Profile
- Fund/investor type: {VC/angel/accelerator}
- Typical check size: {range}
- Investment thesis alignment: {how this pitch fits}
- Portfolio overlap: {similar companies they've funded}
- Red flags for this audience: {what turns them off}

### Stage-Appropriate Expectations
- What "good traction" looks like at this stage: {specifics}
- What "great traction" looks like: {specifics}
- Minimum viable metrics to raise: {specifics}
- Common objections at this stage: {list}

### Current Climate Notes
- Fundraising difficulty: {easier/normal/harder than 12 months ago}
- Hot topics investors are interested in: {trends}
- Topics investors are fatigued by: {overhyped areas}

> Data labels: Mark each finding with [Data], [Estimate], [Assumption], or [Opinion]
```

---

## Agent A2: Comparable & Narrative Research

```
Research task: Find comparable pitch narratives and story hooks for {product description}
Context: {product summary from intake}
Market: {market/category from intake}
Competitors: {known competitors from intake}

RESEARCH PROTOCOL:

ROUND 1 — Comparable companies and their stories (4-5 searches):
- "{competitor 1} pitch deck" OR "{competitor 1} fundraise announcement"
- "{competitor 2} pitch deck" OR "{competitor 2} seed round"
- "{product category} startup pitch deck examples"
- "{product category} demo day pitch"
- "{product category} successful pitch story"

ROUND 2 — Narrative patterns that work (3-4 searches):
- "{product category} for {customer type}" startup analogy
- "X for Y" startup pitch examples {product category}
- "{problem} startup story founder"
- "why I built {product category}" founder story

ROUND 3 — Market narrative and trends (3-4 searches):
- "{product category} market trends {current year}"
- "why now {product category}" timing narrative
- "{product space} tailwinds {current year}"
- "{regulatory/technology/behavioral change} driving {product category}"

ROUND 4 — What doesn't work (2-3 searches):
- "{product category} startup failed pitch" OR "common mistakes {product category} pitch"
- "investor objections {product category}"
- "{product category} startup risk" investors worried about

OUTPUT FORMAT:

## Comparable Narratives

### Successful Pitches in This Space
For each comparable:
- **Company:** {name}
- **What they raised:** {amount, stage, when}
- **Narrative angle:** {how they framed the story}
- **Key hook:** {what made investors lean in}
- **Analogy used:** {if any "X for Y" framing}
- **Source:** {where this info came from}

### Narrative Hooks Available
Rank by strength (strongest first):

1. **{Hook name}** — {description}
   - Why it works: {reasoning}
   - How to use: {specific suggestion}
   - Risk: {potential downside}

2. **{Hook name}** — {description}
   [same structure]

### "X for Y" Candidates
| Analogy | Clarity | Risk | Recommendation |
|---------|---------|------|----------------|
| "{product} is like {X} for {Y}" | High/Med/Low | {what could go wrong} | Use/Avoid |

Only recommend "X for Y" if:
- X is widely known to the target investor audience
- The analogy clarifies more than it confuses
- It doesn't box you into the wrong category

### "Why Now" Narrative
- **Timing thesis:** {what makes this the right moment}
- **Evidence:** {trend data, regulatory change, behavioral shift}
- **Strength:** Strong / Moderate / Weak
- **Risk:** {what could undermine the timing argument}

### What NOT to Do
- Narratives that have been overused: {examples}
- Objections investors will raise: {top 3-5}
- Narrative traps to avoid: {specific to this space}

> Data labels: Mark each finding with [Data], [Estimate], [Assumption], or [Opinion]
```
