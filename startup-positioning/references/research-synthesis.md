# Positioning Research Synthesis Protocol

## Before Writing

1. Read ALL raw files in `{project-name}/raw/` before writing anything
2. Look for patterns that repeat across multiple sources
3. Identify contradictions — explain which source to trust and why
4. Connect the dots across Wave 1 and Wave 2

## Cross-Wave Connections to Look For

These are positioning-specific patterns that emerge when you combine raw research:

- **Customer pain + alternative limitation = positioning opportunity** — your product addresses the pain where alternatives fall short
- **Best-fit customer characteristics + category expectations = right market frame** — the category where your best customers already shop
- **Customer language + switching triggers = messaging foundation** — position in the words customers already use
- **Trend + buyer expectation shift = timing advantage** — position now while the frame is forming
- **Multiple alternatives failing at the same job = underserved JTBD** — opportunity to own a job that nobody does well

## Confidence Rating

Apply to every major claim in the final deliverables:

- **High:** Multiple Tier 1/2 sources agree, recent data, matches customer voice
- **Medium:** Some evidence but gaps, or sources partially disagree
- **Low:** Limited data, mostly inferred, or data older than 12 months

---

## Dunford's 5+1 Components — Detailed Synthesis Process

Work through each component in order. Each one builds on the last.

### 1. Competitive Alternatives

- Pull from `raw/alternative-mapping.md`
- Organize by job-match relevance (closest job match first)
- Include non-obvious alternatives — the "do nothing" option is often the real competitor
- Common mistake: Only listing direct competitors. The founder already knows those. The value is surfacing alternatives they haven't considered.
- For each alternative, note: what job it solves, how well, and where it breaks down

### 2. Unique Attributes

- This step is COLLABORATIVE — present what research reveals, then ask the founder to confirm and add
- Look for attributes in: product capabilities, technical architecture, team expertise, business model, speed, integrations, data access
- Be specific: "Drag-and-drop workflow builder requiring zero code" not "easy to use"
- Test each attribute: Is it truly unique? Or do alternatives have it too?
- If alternatives have it, it's not a positioning attribute — it's table stakes
- Aim for 5-10 candidates; the best positioning uses 3-5

### 3. Value Themes

- For each unique attribute, ask: "So what? What does this enable for the customer?"
- Chain: Attribute → "which means that..." → customer outcome
- Group related attributes into 2-3 themes maximum (more than 3 dilutes the message)
- USE THE LANGUAGE MAP from customer intelligence — frame value in the words customers already use
- Test: Would a customer care about this? Would they pay for it?
- If a value theme doesn't connect to a real customer pain from Wave 2, drop it

**Category language vs. Customer language check:**
Customers often describe their problem using words that would position the product in the wrong category. Example: founders search "validate my startup idea" (customer language), but "validation tool" triggers the wrong buyer expectations (instant score, shallow analysis). When this tension exists:
- Document both the customer verbs and the category nouns
- Recommend bridging in copy: use customer verbs + category nouns (e.g., "validate your startup idea" as the action, "validated strategy" as the outcome)
- Flag this explicitly in the messaging-implications deliverable so copywriters know which words are customer-language (use as verbs) and which are category-language (use as outcomes/nouns)

### 4. Best-Fit Customers

- Pull from `raw/customer-intelligence.md` — best-fit customer profile
- Define by characteristics that make them CARE MORE, not demographics
- Good: "Mid-market teams with 5-15 people who outgrew spreadsheets but can't afford enterprise tools"
- Bad: "Companies with 50-200 employees in the US"
- The right best-fit customers: get value fast, don't haggle price, become champions
- Cross-check: do these customers actually experience the pains your value themes address?

### 5. Market Category

- Pull from `raw/market-categories.md`
- Present 2-3 top candidates with pros/cons for each
- Recommend one with clear reasoning
- The right category makes the value OBVIOUS without explanation
- If unsure between two: default to the one where the product has the strongest existing proof points
- Consider: existing category, subcategory, or new category (new is highest risk)
- **Separate three things clearly:** (1) the category label (what the product IS), (2) the value anchor (what you compare value TO), (3) the distribution descriptor (HOW to get it). These are different and serve different purposes in copy. Example: category = "AI Startup Strategy Toolkit", value anchor = "what a $10K consultant delivers", distribution = "open-source Claude skill"

### 6. Trend Overlay (Optional)

- Pull from `raw/trends-timing.md`
- Only include if a trend genuinely amplifies the positioning
- "None" is a valid and often better answer than a forced trend
- A bad trend overlay makes positioning feel gimmicky
- Good test: Would the positioning still work without the trend? If yes, the trend is a bonus. If no, the positioning is too dependent on hype.

---

## Validation Tests

Run all three tests on the synthesized positioning. If any test fails, iterate on the 5+1 components before finalizing.

### Test 1: Neumeier Onliness Statement

Basic form:
> "Our [product] is the only [category] that [key differentiator]."

Extended (6 elements):
> - **WHAT:** The category
> - **HOW:** The point of radical differentiation
> - **WHO:** The target audience
> - **WHERE:** The market geography
> - **WHY:** The need it fulfills
> - **WHEN:** The underlying trend

If the basic statement isn't convincing — if "only" feels like a stretch — the positioning needs more work. Go back to components 2-3 and sharpen.

### Test 2: Moore Positioning Statement

> **For** [target customer]
> **who** [statement of need/opportunity],
> **the** [product name] **is a** [market category]
> **that** [statement of key benefit].
> **Unlike** [primary competitive alternative],
> **our product** [statement of primary differentiation].

Every field must be fillable with confidence. If any field is vague or generic, the component it draws from needs work.

### Test 3: Ries/Trout Mental Ladder

- Can you state the position in 10 words or fewer?
- Does it claim ONE clear rung (not "best at everything")?
- Is that rung available (not already owned by a stronger competitor)?
- Would a customer use these words to describe you to a colleague?

If any test fails, iterate on the 5+1 components. Do not ship weak positioning.

---

## Output File Templates

### positioning-doc.md

```markdown
# Market Positioning: {product}
*Skill: startup-positioning | Generated: {date}*

## Executive Summary
{Positioning in 3 sentences: who you are, for whom, why you win.}

## 1. Competitive Alternatives
{What customers would do if your product didn't exist. Full map from research.}

### Alternative Landscape
| Alternative | Type | Job Match | Where It Falls Short |
|---|---|---|---|

> **Confidence:** High/Medium/Low — {reasoning}

## 2. Unique Attributes
| Attribute | Evidence | Defensible? |
|---|---|---|

> **Confidence:** High/Medium/Low — {reasoning}

## 3. Value Themes
### Theme 1: {name}
- **Attributes:** {which unique attributes drive this}
- **Customer outcome:** {in their language}
- **Evidence:** {from research}

### Theme 2: {name}
[same structure]

> **Confidence:** High/Medium/Low — {reasoning}

## 4. Best-Fit Customers
**Profile:** {characteristics that predict high value and fast adoption}
**Evidence:** {from customer intelligence}
**Why they care more:** {what makes this value theme critical for them vs. others}

> **Confidence:** High/Medium/Low — {reasoning}

## 5. Market Category
**Chosen category:** {name} ({type: existing / subcategory / new})
**Why this frame:** {reasoning — how it makes unique value obvious}
**Buyer expectations:** {what this category signals to buyers}
**Risk:** {what expectations might work against you}

> **Confidence:** High/Medium/Low — {reasoning}

## 6. Trend Overlay
{Trend and how it amplifies positioning — or "None. The positioning stands on its own."}
**Would the positioning work without this trend?** {Yes/No + reasoning. If No, the positioning is too trend-dependent — revisit.}

> **Confidence:** High/Medium/Low — {reasoning}

## Positioning Strength Assessment
| Component | Strength | Notes |
|---|---|---|
| Competitive Alternatives | Strong/Moderate/Needs Work | {brief} |
| Unique Attributes | ... | ... |
| Value Themes | ... | ... |
| Best-Fit Customers | ... | ... |
| Market Category | ... | ... |
| Overall | ... | ... |

## Strategic Recommendations
{next steps for implementing the positioning}

**Social proof warning:** Do not fabricate or pre-write social proof quotes. Only use quotes from published, verifiable sources. Placeholder quotes damage credibility more than no quotes at all. Build social proof by encouraging early users to share results publicly, then reference those real posts.

## Red Flags
- {issues that could undermine this positioning}

## Yellow Flags
- {concerns to monitor}

## Data Gaps & Limitations
- {what data is missing and how to fill it}

## Sources
- {key sources with tier ratings}
```

### positioning-statement.md

```markdown
# Positioning Statements: {product}
*Skill: startup-positioning | Generated: {date}*

## Moore Positioning Statement
For [target customer] who [need/opportunity], [product] is a [category] that [key benefit]. Unlike [primary alternative], our product [primary differentiation].

## Neumeier Onliness Statement
[product] is the only [category] that [key differentiator].

## Onliness Statement (Extended)
- **WHAT:** {category}
- **HOW:** {point of differentiation}
- **WHO:** {target audience}
- **WHERE:** {market}
- **WHY:** {need it fulfills}
- **WHEN:** {underlying trend}

## Elevator Pitch (30 seconds)
{Conversational version of the positioning — what you'd say at a dinner party}

## Tagline Candidates

| Tagline | Angle | Best For | Possible Misread |
|---------|-------|----------|-----------------|
| {tagline 1} | {angle} | {context} | {how could a reader misinterpret this?} |
| {tagline 2} | {angle} | {context} | {possible objection or wrong reading} |

For each tagline, actively ask: "What could a skeptical reader think when reading this? What objection does it trigger?" If the misread is serious (e.g., sounds condescending, makes an assumption about the reader's situation, or positions in the wrong category), flag it and suggest a safer alternative.

## One-Liner Variants

Provide context-specific versions:
- **For GitHub README:** {lead with open-source, end with free}
- **For marketplace listing:** {lead with what user can DO, list deliverables}
- **For social media:** {hook + transformation + differentiator}
- **For elevator pitch:** {conversational, 30 seconds}

## Freemium Positioning (if applicable)

If the product has or plans a freemium model:

**Free tier message:** {how to communicate that free is complete, not limited}
**Premium tier message:** {how to communicate premium extends, not unlocks}
**Upgrade trigger:** {natural moment when user would want premium}

Anti-pattern: never make the free tier feel "incomplete" to push premium. The free tier should deliver full value for its scope. Premium adds a different scope (e.g., strategy vs. execution), not "more of the same."

## Validation Notes
- Onliness Test: {Pass/Fail + notes}
- Moore Template: {Pass/Fail + notes}
- Mental Ladder: {Pass/Fail + notes}
- Overall Positioning Strength: Strong / Moderate / Needs Work
```

### competitive-alternatives.md

```markdown
# Competitive Alternatives Map: {product}
*Skill: startup-positioning | Generated: {date}*

## The Job to Be Done
{Core job customers are hiring for}

## Direct Competitors
[table or structured sections from raw data]

## Adjacent Alternatives
[from raw data]

## Manual / Status Quo
[from raw data]

## Your Unique Attributes vs. Each Alternative
| Alternative | What They Offer | Where You Win | Where They Win |
|---|---|---|---|

## Switching Cost Analysis
| Alternative | Technical | Contractual | Emotional | Net Switching Barrier |
|---|---|---|---|---|
| {name} | H/M/L | H/M/L | H/M/L | {summary} |

## Key Positioning Insights
- {what the alternative landscape tells us about positioning}

## Red Flags
- {issues in the competitive alternative landscape}

## Yellow Flags
- {concerns to monitor}

## Sources
- {key sources with tier ratings}
```

### market-category-analysis.md

```markdown
# Market Category Analysis: {product}
*Skill: startup-positioning | Generated: {date}*

## Candidate Categories
### {Category 1}: {type}
[from raw data + synthesis]

## Recommendation
{Chosen category with reasoning}

## Implementation
- **Category label:** {exact words to use}
- **Tagline direction:** {how to frame it}
- **Buyer expectation alignment:** {what expectations you meet, which you need to manage}

## Red Flags
- {issues that could undermine the category choice}

## Yellow Flags
- {concerns to monitor}

## Data Gaps
- {what data is missing about category dynamics}

## Sources
- {key sources with tier ratings}
```

## Post-Synthesis Verification

After writing all deliverables, run the Verification Agent protocol. See `references/verification-agent.md` for the full process. The verification step checks all deliverables for unlabeled claims, internal contradictions, confidence rating consistency, and startup-positioning-specific coherence (positioning statement vs. research data, JTBD vs. customer intelligence, cross-deliverable messaging consistency, validation test integrity).

---

### messaging-implications.md

```markdown
# Messaging Implications: {product}
*Skill: startup-positioning | Generated: {date}*

## Messaging Hierarchy

What to communicate first, second, third. Every piece of copy should follow this priority:

1. {Primary message — the outcome, what the user gets}
2. {Secondary — time/effort, how fast or easy}
3. {Tertiary — key differentiator}
4. {Fourth — cost/access}
5. {Fifth — specific deliverables or features}
6. {Sixth — value anchor or comparison}

Not every piece of copy needs all levels. But when present, they should appear in this order.

## Category Label

**Always use:** "{exact category phrase}"

Use this exact phrase consistently across: website, GitHub, marketplace, social bios, README.

## Value Anchor

**"{value anchor phrase}"** — used in supporting copy to set perceived value. This is NOT the category label. The category describes WHAT it is. The value anchor describes WHAT IT'S WORTH.

Where to use: body copy, comparison sections, pricing context.
Where NOT to use: headlines, category descriptions, taglines (unless carefully tested).

## Customer Language vs. Category Language

| Customer says (use as verbs) | Category says (use as nouns/outcomes) |
|------------------------------|--------------------------------------|
| {e.g., "validate my idea"} | {e.g., "validated strategy"} |

Bridge in copy: use customer verbs with category nouns.

## Words to Use / Avoid

| Use | Instead of | Why |
|-----|-----------|-----|
| {preferred term} | {avoided term} | {reason from positioning} |

## Social Proof Guidelines

Do not fabricate or pre-write social proof. Only use quotes from published, verifiable sources. Placeholder quotes damage credibility more than no quotes at all. If no real social proof exists yet, omit the section entirely and note it as a gap to fill.

## Freemium Positioning (if applicable)

**Free tier message:** {how to communicate that free is complete, not limited}
**Premium tier message:** {how to communicate premium extends, not unlocks}
**Upgrade trigger:** {natural moment when user would want premium}

Anti-pattern: never make the free tier feel "incomplete" to push premium. The free tier should deliver full value for its scope. Premium adds a different scope (e.g., strategy vs. execution), not "more of the same."

## Red Flags
- {messaging risks}

## Sources
- {key sources}
```
