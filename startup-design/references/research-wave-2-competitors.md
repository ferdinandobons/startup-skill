# Wave 2: Competitive Analysis (3 agents)

Read `research-principles.md` first. Wave 2 agents receive findings from Wave 1 as context — pass them a summary of market size, key players identified, and relevant trends.

---

## Agent B1: Direct Competitor Deep-Dives

```
Research task: Deep analysis of direct competitors for {product description}
Context: We're designing a startup that {one-sentence description}.
Market context from Wave 1: {brief summary of market size, key players found}

RESEARCH PROTOCOL — for each competitor (aim for 5-8 direct competitors):

ROUND 1 — Identify competitors (3-4 searches):
- "{problem} software/app/tool {current year}"
- "best {product category} tools {current year}"
- "{known competitor 1} vs {known competitor 2} alternatives"
- "G2 {product category} grid"
- "{product category} Product Hunt"

ROUND 2 — Deep-dive each competitor (2-3 searches per competitor):
- Visit their website directly: capture pricing, features, positioning
- "{competitor name} review" on G2, Capterra, TrustRadius
- "{competitor name} funding crunchbase" OR "{competitor name} investors"
- "{competitor name} employees linkedin" (for team size signals)
- "{competitor name} complaints" OR "{competitor name} problems reddit"

ROUND 3 — Competitive dynamics (2 searches):
- "{product category} market share"
- "{competitor 1} vs {competitor 2}" comparison articles

For EACH competitor, build a complete profile:

COMPETITOR PROFILE TEMPLATE:
## {Competitor Name}
- **Website:** {url}
- **Founded:** {year}
- **Headquarters:** {location}
- **Team size:** {estimate from LinkedIn/Crunchbase}
- **Funding:** {total raised, last round, investors}
- **Stage:** bootstrapped / seed / Series A / Series B+ / public

### Product
- **Core offering:** {what they sell}
- **Key features:** {top 5 features}
- **Tech stack signals:** {any public info on their technology}
- **Integrations:** {what they connect with}

### Pricing
- **Model:** {subscription / per-user / usage-based / freemium}
- **Tiers:** {list each tier with price and what's included}
- **Free plan:** yes/no, what's included
- **Enterprise:** custom pricing? sales-led?

### Market Position
- **Target customer:** {who they serve}
- **Positioning:** {how they describe themselves — capture their actual tagline}
- **Key differentiator:** {what they claim makes them unique}

### Traction Signals
- **G2/Capterra reviews:** {count and average rating}
- **Product Hunt:** {upvotes if launched there}
- **Social media:** {follower counts on LinkedIn, Twitter}
- **Job postings:** {number and type — engineering heavy = building; sales heavy = scaling}
- **Notable customers:** {logos or case studies on their site}

### Strengths (based on reviews and positioning)
- {strength 1}
- {strength 2}

### Weaknesses (based on negative reviews, missing features, complaints)
- {weakness 1}
- {weakness 2}

### Threat Level to Our Startup: Low / Medium / High
- {why}

---

After all profiles, add:

## Competitive Landscape Summary
- **Market concentration:** fragmented / consolidating / dominated by 1-2 players
- **Gaps in the market:** {what no competitor does well}
- **Positioning opportunities:** {where we can differentiate}
- **Competitive moat assessment:** {how defensible is this market}

## Data Gaps
- [Competitors you suspect exist but couldn't find info on]
- [Data points missing for specific competitors]

Save to: {project-name}/01-discovery/raw/direct-competitors.md
```

---

## Agent B2: Indirect Competitors & Substitutes

```
Research task: Indirect competitors, substitutes, and alternative approaches for {problem}
Context: We're designing a startup that {one-sentence description}.
Direct competitors found: {list from Agent B1 if available, otherwise "to be determined"}

RESEARCH PROTOCOL:

ROUND 1 — Alternative approaches (2-3 searches):
- "how do {customer type} currently handle {problem}"
- "{problem} without software"
- "{problem} excel template" OR "{problem} manual process"
- "{problem} outsource"

ROUND 2 — Adjacent products (2-3 searches):
- "{adjacent category} that also does {related function}"
- "{large platform} {related feature}" (e.g., "Salesforce reporting" if you're building analytics)
- "open source {product category}"

ROUND 3 — Platform risk (1-2 searches):
- "{major platform} adding {our feature}"
- "{major platform} AI features {current year}"

OUTPUT FORMAT:
# Indirect Competitors & Substitutes

## Status Quo Solutions (what people do today without a dedicated tool)
For each:
- What it is
- How common it is
- Why people stick with it (cost, familiarity, "good enough")
- Where it breaks down (the pain that creates our opportunity)

## Adjacent Products
For each:
- Product name and what it primarily does
- How it partially solves our problem
- What it's missing (our wedge)
- Risk: could they add our feature?

## Platform Risk Assessment
- Which major platforms could absorb our functionality?
- How likely is this? (based on roadmap signals, acquisitions, public statements)
- Timeline estimate
- Mitigation strategies

## Open Source & Free Alternatives
- What exists
- Quality and adoption level
- Why someone would pay for our solution instead

## Switching Cost Analysis
- What keeps people on current solutions?
- What would make them switch?
- Estimated effort to migrate to our product

## Data Gaps
- [List anything you couldn't find]

Save to: {project-name}/01-discovery/raw/indirect-competitors.md
```

---

## Agent B3: Competitor Go-to-Market Analysis

```
Research task: How competitors in {product category} acquire and retain customers
Context: We're designing a startup that {one-sentence description}.
Key competitors: {list top 3-5 from Agent B1}

RESEARCH PROTOCOL:

ROUND 1 — Marketing channels (2-3 searches per competitor):
- Check competitor websites for blog, resources, webinars, case studies
- "{competitor name} marketing strategy"
- Search for competitor ads (Google Ads transparency, Facebook Ad Library)
- Check their social media activity and content frequency

ROUND 2 — Sales motion (2 searches):
- "{competitor name} sales team" linkedin
- "{product category} sales cycle length"
- Look for: self-serve signup vs. demo request vs. "contact sales"

ROUND 3 — Content & SEO (2 searches):
- "{product category} blog" — who ranks for key terms?
- Check competitors on Similarweb or similar tools for traffic estimates

OUTPUT FORMAT:
# Competitor Go-to-Market Analysis

For each competitor:
## {Competitor Name} — GTM Breakdown
- **Primary acquisition channel:** {SEO / paid ads / outbound sales / partnerships / community / PLG}
- **Sales motion:** {self-serve / sales-assisted / enterprise sales}
- **Content strategy:** {blog frequency, topics, quality assessment}
- **Social presence:** {which platforms, posting frequency, engagement level}
- **Paid advertising:** {visible ads? what channels? what messaging?}
- **Partnership plays:** {integrations, co-marketing, channel partners}
- **Pricing as GTM:** {freemium? free trial? money-back guarantee?}

## Channel Opportunity Map
| Channel | Competitor Saturation | Our Opportunity | Estimated CAC |
|---------|----------------------|-----------------|---------------|
| SEO/Content | High/Medium/Low | ... | ... |
| Paid Search | ... | ... | ... |
| Social/Community | ... | ... | ... |
| Outbound Sales | ... | ... | ... |
| Partnerships | ... | ... | ... |
| Product-Led Growth | ... | ... | ... |

## Key Takeaway
- What's working for competitors?
- What channels are underexploited?
- Where can we win with limited budget?

## Data Gaps
- [List anything you couldn't find]

Save to: {project-name}/01-discovery/raw/competitor-gtm.md
```
