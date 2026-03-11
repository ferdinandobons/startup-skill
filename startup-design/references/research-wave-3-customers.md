# Wave 3: Customer & Demand (3 agents)

Read `research-principles.md` first. Wave 3 agents receive competitor findings from Wave 2 as context.

---

## Agent C1: Customer Voice & Pain Points

```
Research task: Deep customer research — real voices discussing {problem}
Context: We're designing a startup that {one-sentence description}.
Target customer: {customer description}
Key competitors found: {list from Wave 2}

The goal is to hear how real people talk about this problem in their own words. This directly informs positioning, copywriting, and product decisions.

RESEARCH PROTOCOL:

ROUND 1 — Reddit deep-dive (3-4 searches):
- "site:reddit.com {problem keywords}"
- "site:reddit.com {industry} frustration"
- "site:reddit.com {existing solution} complaints"
- Browse top posts in relevant subreddits: r/{industry}, r/{role}, r/{related topic}
For each relevant thread: capture the original post, top comments, and upvote counts (upvotes = agreement).

ROUND 2 — Professional forums (2-3 searches):
- "site:news.ycombinator.com {problem keywords}"
- "{problem} forum discussion"
- "{industry} community {problem}"
- Check industry-specific forums (e.g., Stack Overflow for devtools, Bogleheads for finance)

ROUND 3 — Review mining (2-3 searches):
- "{existing solution} reviews" on G2, Capterra, TrustRadius
- Focus on 1-3 star reviews — these reveal unmet needs
- "{existing solution} worst thing about"

ROUND 4 — Social media sentiment (1-2 searches):
- "site:twitter.com {problem keywords}" OR "site:linkedin.com {problem keywords}"
- "{problem} rant" OR "{problem} hate"

OUTPUT FORMAT:
# Customer Voice Research: {problem}

## Verbatim Quotes (Top 20)
Capture exact quotes that express the pain. For each:
- Quote (verbatim)
- Source (Reddit, G2, etc. — with thread/review link if possible)
- Context (who is this person? what role/industry?)
- Upvotes/agreement signals
- Pain category (see below)

## Pain Categories (grouped from quotes)
For each category:
- Name of pain (e.g., "Time wasted on manual process")
- Frequency: how often does this come up across all sources?
- Intensity: mild annoyance vs. hair-on-fire problem?
- Current workarounds people mention
- Quotes that best represent this pain

## Jobs-to-Be-Done (extracted from customer voice)
- Functional jobs: what are they trying to accomplish?
- Social jobs: how do they want to be perceived?
- Emotional jobs: how do they want to feel?

## Language Map
Words and phrases customers actually use to describe:
- The problem: [list exact words]
- The desired outcome: [list exact words]
- Their frustrations: [list exact words]
This language should be used verbatim in positioning and copy — it resonates because it mirrors their own words.

## Unmet Needs (things people ask for that don't exist yet)
- [Need 1 — evidence from quotes]
- [Need 2 — evidence from quotes]

## Data Gaps
- [Communities you couldn't access or find]
- [Customer segments with no voice data]

Save to: {project-name}/01-discovery/raw/customer-voice.md
```

---

## Agent C2: Demand Signals & Market Validation

```
Research task: Quantitative demand signals for {product category}
Context: We're designing a startup that {one-sentence description}.

RESEARCH PROTOCOL:

ROUND 1 — Search demand (2-3 searches):
- Google Trends for: "{product category}", "{problem} solution", "{competitor name}"
- "{product category} search volume"
- "keyword research {product category}"
Capture: trend direction (rising/flat/declining), seasonal patterns, geographic hotspots.

ROUND 2 — Product launch signals (2 searches):
- Search Product Hunt for similar products — upvotes, comments, maker responses
- Search Indie Hackers for people building in this space — revenue numbers if shared
- Check beta list / landing page tools for pre-launch products in the space

ROUND 3 — Pricing intelligence (3-4 searches):
- Visit pricing pages of top 5 competitors (directly)
- "{product category} pricing comparison {current year}"
- "{product category} how much do companies spend"
- "{customer type} software budget survey"
Capture: exact pricing tiers from each competitor in a comparison table.

ROUND 4 — Willingness to pay signals (1-2 searches):
- "{product category} survey willingness to pay"
- "{problem} worth paying for"
- Check subreddits and forums for discussions about pricing of similar tools

OUTPUT FORMAT:
# Demand Signals: {product category}

## Search Demand
- Google Trends summary: [rising / stable / declining over what period]
- Peak months (if seasonal): [months]
- Geographic hotspots: [regions/countries with highest interest]
- Related rising queries: [list — these reveal adjacent opportunities]

## Product Launch Signals
| Product | Platform | Date | Upvotes/Reception | Key Takeaway |
|---------|----------|------|-------------------|-------------|
| ... | ... | ... | ... | ... |

## Pricing Landscape
| Competitor | Free Plan | Starter | Pro | Enterprise | Model |
|-----------|-----------|---------|-----|-----------|-------|
| ... | ... | ... | ... | ... | ... |

- Median price point: $X/mo
- Price range: $X - $Y/mo
- Most common model: [subscription / per-user / usage-based]
- Pricing trends: [racing to bottom? premium tier growing? usage-based gaining?]

## Willingness to Pay Assessment
- Evidence for strong WTP: [list]
- Evidence for weak WTP: [list]
- Recommended pricing range for our startup: $X - $Y/mo
- Rationale: [why this range, based on competitor benchmarks and value delivered]

## Market Validation Score
- Search demand: Strong / Moderate / Weak
- Competitive activity: High / Medium / Low (high = proven market; low = unproven)
- Customer spending: Growing / Stable / Declining
- Overall demand signal: [assessment]

## Data Gaps
- [Keywords with no trend data]
- [Competitors with hidden pricing]

Save to: {project-name}/01-discovery/raw/demand-signals.md
```

---

## Agent C3: Target Audience Profiling

```
Research task: Deep target audience research for {customer description}
Context: We're designing a startup that {one-sentence description}.

RESEARCH PROTOCOL:

ROUND 1 — Demographic & firmographic data (2-3 searches):
- "{customer type} demographics statistics"
- "how many {customer type} in {geography}"
- "{customer type} company size distribution"
Capture: population size, segmentation data, geographic distribution.

ROUND 2 — Behavioral patterns (2-3 searches):
- "{customer type} software adoption habits"
- "{customer type} buying process for {product category}"
- "how do {customer type} discover new tools"
Capture: where they research, who influences them, decision-making process.

ROUND 3 — Day-in-the-life (2 searches):
- "{role} daily challenges"
- "{role} workflow {industry}"
Capture: what their day looks like, where our product fits in their workflow.

ROUND 4 — Decision-making (1-2 searches):
- "{product category} buying criteria"
- "who decides on {product category} at {company type}"
Capture: who are the buyers, influencers, blockers? What's the typical sales cycle?

OUTPUT FORMAT:
# Target Audience Profile: {customer description}

## Primary Persona
- **Name:** {fictional representative name}
- **Role:** {job title}
- **Company:** {company type, size, industry}
- **Demographics:** {age range, location, education}
- **Goals:** {what they're trying to achieve}
- **Frustrations:** {specific pains related to our problem}
- **Current tools:** {what they use today}
- **Quote:** {a representative quote from customer voice research}

## Buying Behavior
- **How they discover tools:** {channels, sources}
- **Who's involved in the decision:** {buyer, influencer, approver, blocker}
- **Decision criteria:** {top 5 factors ranked}
- **Typical budget:** {what they spend on similar tools}
- **Sales cycle length:** {days/weeks/months}
- **Common objections:** {why they might say no}

## Secondary Persona (if applicable)
[Same structure as primary]

## Anti-Persona (who is NOT our customer)
- {description of who we should NOT target and why}

## Where to Reach Them
| Channel | Density | Cost | Notes |
|---------|---------|------|-------|
| {specific subreddits} | ... | Free | ... |
| {specific LinkedIn groups} | ... | ... | ... |
| {specific conferences} | ... | ... | ... |
| {specific newsletters} | ... | ... | ... |
| {specific podcasts} | ... | ... | ... |
| {specific communities} | ... | ... | ... |

## Data Gaps
- [Audience segments with no data]
- [Behavioral data you couldn't find]

Save to: {project-name}/01-discovery/raw/target-audience.md
```
