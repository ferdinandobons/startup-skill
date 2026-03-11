# Wave 1: Competitor Profiles + Pricing Intelligence

Read `research-principles.md` first.

---

## Agent A1: Competitor Deep-Dives

```
Research task: Deep analysis of direct competitors for {product description}
Context: {product summary from intake}
Known competitors: {list from intake, if any}

RESEARCH PROTOCOL — identify and profile 5-8 direct competitors:

ROUND 1 — Identify competitors (4-5 searches):
- "{problem} software/app/tool {current year}"
- "best {product category} tools {current year}"
- "{known competitor 1} vs alternatives"
- "G2 {product category} grid"
- "{product category} Product Hunt"
- "top {product category} startups"
- "{problem} solutions" OR "how do {customer type} currently handle {problem}"
  (this catches adjacent solutions — inventory tools, platforms with overlapping features, manual/offline alternatives that compete for the same budget)

ROUND 2 — Deep-dive each competitor (2-3 searches per competitor):
- Visit their website: capture positioning, features, messaging, social proof
- "{competitor name} review G2 Capterra"
- "{competitor name} crunchbase funding"
- "{competitor name} linkedin employees" (team size signals)
- "{competitor name} changelog" or "{competitor name} updates {current year}"

ROUND 3 — Competitive dynamics (2-3 searches):
- "{product category} market share"
- "{competitor 1} vs {competitor 2}" comparison articles
- "{product category} landscape {current year}"

For EACH competitor, build a complete profile:

## {Competitor Name}
- **Website:** {url}
- **Founded:** {year}
- **Headquarters:** {location}
- **Team size:** {estimate from LinkedIn/Crunchbase}
- **Funding:** {total raised, last round, lead investors}
- **Stage:** bootstrapped / seed / Series A / Series B+ / public
- **Estimated revenue:** {if available, or proxy estimate}

### Product
- **Tagline:** {their actual tagline/positioning statement}
- **Core offering:** {what they sell in one sentence}
- **Key features:** {top 5-8 features}
- **Tech stack signals:** {any public info}
- **Integrations:** {key integrations}
- **Platform:** {web / mobile / desktop / API}

### Market Position
- **Target customer:** {who they serve — be specific}
- **Positioning:** {how they describe themselves}
- **Key differentiator:** {what they claim makes them unique}
- **Social proof:** {notable customers, case studies, logos}

### Traction Signals
- **G2/Capterra:** {review count and average rating}
- **Product Hunt:** {launch date, upvotes}
- **Social media:** {follower counts, engagement level}
- **Job postings:** {number and type}
- **Web traffic signals:** {if available from Similarweb/press mentions}
- **Notable customers:** {logos or case studies}

### Strengths
- {strength 1 — based on evidence, not speculation}
- {strength 2}
- {strength 3}

### Weaknesses
- {weakness 1 — based on reviews, gaps, complaints}
- {weakness 2}
- {weakness 3}

### Threat Level: Low / Medium / High
- {why — with evidence}

---

After all profiles:

## Landscape Summary
- **Total competitors identified:** {number profiled + number found but not profiled}
- **Market concentration:** fragmented / consolidating / dominated by 1-2 players
- **Average funding level:** {across profiled competitors}
- **Common positioning themes:** {what most competitors emphasize}
- **Gaps in the market:** {what no competitor does well}

## Adjacent Solutions
Products that aren't direct competitors but compete for the same budget or solve an overlapping problem. These matter because customers often choose "good enough" adjacent tools over a dedicated solution.
- {adjacent solution 1} — what it does, how it overlaps, why someone might pick it instead
- {adjacent solution 2}
Include: broader platforms with partial feature overlap, manual/offline alternatives, tools from adjacent categories that could expand into this space.

## Data Gaps
- [What you couldn't find and why it matters]

Save to: {project-name}/raw/competitor-profiles.md
```

---

## Agent A2: Pricing Intelligence

```
Research task: Pricing reverse-engineering for competitors in {product category}
Context: {product summary from intake}
Competitors to analyze: {list from A1 if available, otherwise discover during research}

RESEARCH PROTOCOL:

ROUND 1 — Capture pricing pages (1 search per competitor):
- Visit each competitor's pricing page directly
- Screenshot or capture: tiers, prices, feature lists, CTAs
- Note: annual vs monthly pricing, currency, any free tier

ROUND 2 — Deep pricing analysis (2-3 searches):
- "{competitor name} pricing" (for third-party breakdowns)
- "{competitor name} pricing changes" (for pricing history)
- "{product category} pricing comparison {current year}"
- "{competitor name} enterprise pricing" (often hidden)

ROUND 3 — Value metric analysis (1-2 searches):
- "{product category} pricing model" (per-seat vs usage vs flat)
- "how much does {competitor name} cost" (real user discussions)

For EACH competitor, analyze:

## {Competitor Name} — Pricing Breakdown

### Pricing Model
- **Value metric:** {what they charge for — per seat / per usage / flat / hybrid}
- **Why this metric:** {how it aligns with value delivered}
- **How it scales:** {does price grow linearly with usage? Are there volume discounts?}

### Tier Structure
| | {Tier 1} | {Tier 2} | {Tier 3} | {Enterprise} |
|---|----------|----------|----------|-------------|
| Price (monthly) | | | | |
| Price (annual) | | | | |
| Annual discount | | | | |
| {Key feature 1} | | | | |
| {Key feature 2} | | | | |
| {Key feature 3} | | | | |
| {Key limit 1} | | | | |
| Target persona | | | | |

### Pricing Psychology
- **Anchoring:** {do they use a high-price tier to make mid-tier attractive?}
- **Decoy effect:** {is there a tier designed to push people to a specific plan?}
- **Charm pricing:** {$49 vs $50? $99 vs $100?}
- **Social proof on pricing:** {which tier is "most popular"?}
- **Free tier strategy:** {what's free and what's gated?}
- **Annual lock-in:** {discount size, refund policy}

### Switching Costs
- **Technical:** {data export? API migration? Integration rewiring?}
- **Contractual:** {annual contracts? Cancellation penalties?}
- **Emotional:** {brand loyalty? Learning curve for alternatives?}
- **Data portability:** {can you export your data easily?}

---

After all competitors:

## Pricing Landscape Summary
- **Dominant value metric:** {what most charge for}
- **Price range:** {lowest to highest for comparable tiers}
- **Median price point:** {for the most common tier}
- **Free tier prevalence:** {how many offer free plans}
- **Annual discount range:** {typical discounts}
- **Pricing whitespace:** {where there's room to position — underserved price points or models}
- **Switching cost patterns:** {are switching costs high or low in this market?}

## Data Gaps
- [Competitors with hidden/custom pricing]
- [Enterprise pricing that couldn't be found]

Save to: {project-name}/raw/pricing-intelligence.md
```
