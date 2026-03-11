# Wave 2: Market Frame & Trends

Read `research-principles.md` first.

---

## Agent B1: Market Category Analysis

```
Research task: Identify and evaluate candidate market categories for {product description}
Context: {product summary from intake}
Competitive alternatives: {summary from Wave 1 alternative mapping}
Customer intelligence: {summary from Wave 1 customer intelligence}

GOAL:
Identify 3-5 candidate market categories the product could position into.
The right category triggers the right buyer expectations — it is the frame
of reference that tells buyers what to compare you to and what to expect.

THREE CATEGORY OPTIONS (from Dunford):
- Head-to-head (existing category): You're a better version of something
  buyers already know (e.g., "CRM" or "project management"). Buyers have
  established expectations. Win by being clearly better on dimensions that
  matter.
- Big fish/small pond (subcategory): Take an existing category and add a
  qualifier that makes you the leader of a narrower space (e.g., "CRM for
  real estate agents", "AI-powered recruiting platform"). Best when existing
  categories don't highlight your unique strength.
- Category creation: Define an entirely new category. Rare, expensive, and
  risky — but powerful when nothing else frames your value well. Only
  recommend if the evidence is overwhelming.

RESEARCH PROTOCOL:

ROUND 1 — How competitors frame themselves (4-5 searches):
- "{competitor 1} tagline" OR "{competitor 1} about page"
- "{competitor 2} LinkedIn description"
- "G2 {product category} category"
- "Capterra {product category} software directory"
- "{competitor} meta description site:{competitor domain}"
Capture: self-described categories, taglines, how they explain what they are.

ROUND 2 — How analysts define the space (3-4 searches):
- "Gartner {product category} market guide {current year}"
- "Forrester {product category} wave {current year}"
- "{product category} market map {current year}"
- "{product category} buyer guide {current year}"
Capture: analyst-defined categories, segment names, market boundaries.

ROUND 3 — How buyers search for solutions (3-4 searches):
- "how to choose a {product category}"
- "best {product category} for {customer type} {current year}"
- "{problem} software buyer guide"
- "what is {product category}" OR "{category term} vs {category term}"
Capture: category terms buyers use, search phrasing, buyer expectations.

ROUND 4 — Category dynamics (3-4 searches):
- "{product category} market size {current year}"
- "{product category} market growth" OR "{product category} trends"
- "{product category} consolidation" OR "{product category} fragmentation"
- "new {product category} startups {current year}"
Capture: growth trajectory, competitive density, room for new entrants.

For EACH candidate category, capture:

### {Category Name}
- **Type:** Existing / Subcategory / New
- **Buyer expectations:** {what buyers assume a product in this category includes}
- **Current leaders:** {who owns this category in buyers' minds}
- **Competitive density:** Low / Medium / High — {count of notable players}
- **Growth trajectory:** Growing / Stable / Declining — {evidence}
- **Pros:** {what expectations work in your favor}
- **Cons:** {what expectations work against you, table stakes you lack}
- **Dunford fit:** Does this frame make your unique strengths OBVIOUS? {yes/no + reasoning}

---

Output format:

# Market Category Analysis: {product}
*Generated: {date}*

## How Competitors Frame Themselves
| Competitor | Self-Described Category | Tagline | G2/Capterra Category |
|---|---|---|---|
| ... | ... | ... | ... |

## Candidate Categories

### Category 1: {name}
- **Type:** Existing / Subcategory / New
- **Buyer expectations:** {what buyers assume this category includes}
- **Current leaders:** {who dominates}
- **Competitive density:** Low / Medium / High — {count of notable players}
- **Growth:** Growing / Stable / Declining — {evidence}
- **Pros:** {what works in your favor}
- **Cons:** {what works against you, table stakes you lack}
- **Dunford fit:** Does this frame make your unique value obvious? {yes/no + reasoning}

[Repeat for 3-5 candidates]

## Category Comparison
| Category | Type | Leaders | Density | Your Fit | Risk |
|---|---|---|---|---|---|
| ... | ... | ... | ... | Strong/Moderate/Weak | H/M/L |

## Recommendation
{Which category and why. If subcategory: what qualifier? If none fits well: explain why and whether category creation is warranted.}

## Data Gaps
- {what couldn't be found, how to fill it}

Save to: {project-name}/raw/market-categories.md
```

---

## Agent B2: Trend & Timing Analysis

```
Research task: Identify market trends and timing signals for {product description}
Context: {product summary from intake}
Category candidates: {from Agent B1 or best-guess category from intake}
Customer intelligence: {summary from Wave 1 customer intelligence}

GOAL:
Identify market trends that could strengthen (or weaken) the product's
positioning, and assess whether the timing is right.

KEY PRINCIPLE:
Only include trends that genuinely change how buyers evaluate solutions.
"AI is hot" is not useful. "Buyers now expect AI-powered automation in
[category], and 60% of RFPs require it" is useful. Every trend must connect
to a concrete positioning implication.

RESEARCH PROTOCOL:

ROUND 1 — Industry trend reports (4-5 searches):
- "{product category} trends {current year}"
- "{industry} market outlook {current year}"
- "{product category} predictions {current year}"
- "Gartner top trends {industry} {current year}"
- "{product category} state of the market {current year}"

ROUND 2 — Technology adoption signals (3-4 searches):
- "{relevant technology} adoption rate {current year}"
- "Gartner Hype Cycle {industry} {current year}"
- "{relevant technology} enterprise adoption"
- "{product category} AI adoption" OR "{product category} automation trends"
Focus on: where the relevant technology sits on the adoption curve — is it
mainstream, early majority, or bleeding edge?

ROUND 3 — Behavioral and regulatory shifts (3-4 searches):
- "{customer type} buying behavior changes {current year}"
- "{industry} new regulations {current year}"
- "{industry} compliance requirements {current year}"
- "{customer type} generational shift" OR "{customer type} workflow changes"
Focus on: changes in how buyers work, buy, or comply that affect what they
need from solutions.

ROUND 4 — Timing signals (3-4 searches):
- "{product category} early adopter success stories"
- "{product category} failed startups" OR "{product category} too early"
- "{product category} market readiness"
- "{similar product} traction {current year}"
Focus on: is the market ready NOW? Are there predecessors that failed on
timing? Are early adopters already seeing results?

For EACH trend, capture:

### {Trend Name}
- **Type:** Technology / Behavioral / Regulatory / Economic
- **Evidence:** {what data supports this — cite sources}
- **Strength:** Strong / Emerging / Speculative
- **Direction for positioning:** Tailwind (helps) / Headwind (hurts) / Neutral
- **Timing:** Early / On-time / Late
- **Positioning implication:** {how this should affect positioning}

---

Output format:

# Trend & Timing Analysis: {product/market}
*Generated: {date}*

## Relevant Trends

### Trend 1: {name}
- **Type:** Technology / Behavioral / Regulatory / Economic
- **Evidence:** {what data supports this — cite sources}
- **Strength:** Strong / Emerging / Speculative
- **Direction for positioning:** Tailwind (helps) / Headwind (hurts) / Neutral
- **Timing:** Early / On-time / Late
- **Positioning implication:** {how this should affect positioning}

[Repeat for each relevant trend]

## Timing Assessment
{Overall assessment: Is NOW the right time for this positioning? What's the 12-18 month trajectory?}

## Trend Overlay Recommendation
{Which trend(s), if any, should be referenced in the positioning? Only recommend trends that genuinely amplify the value proposition. "None" is a valid answer — forced trend alignment weakens positioning.}

## Data Gaps
- {what couldn't be found}

Save to: {project-name}/raw/trends-timing.md
```
