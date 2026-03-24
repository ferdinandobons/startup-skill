# Pitch Research Synthesis Protocol

## Before Writing

1. Read ALL raw files in `{project-name}/raw/` before writing anything
2. Read ALL prior session files (from startup-design, startup-competitors, startup-positioning) if they exist
3. Identify the strongest pitch elements — what's most impressive about this company?
4. Determine the optimal pitch order based on strengths
5. Check if the pitch was built with or without validated research data — this affects the scorecard

## Cross-Source Connections to Look For

These are pitch-specific patterns that emerge when you combine research with founder data:

- **Strong traction + weak insight = lead with traction** — the numbers speak for themselves
- **Weak traction + strong insight = lead with insight** — reframe the conversation around the thesis
- **Strong team + emerging market = lead with team** — investors bet on people in uncertain markets
- **Large market + clear model = lead with opportunity** — the math is compelling
- **Comparable success story + similar approach = use the analogy** — investors love pattern-matching
- **Investor fatigue in space + unique angle = differentiate the narrative** — show you're different
- **Strong "why now" + weak traction = lead with timing** — the wave is more impressive than the surfer
- **Competitive gaps + unique attributes = frame against competitors** — show the opening

## Confidence Rating

Apply to every major claim in the pitch materials:

- **High:** Multiple sources agree, data is recent, verifiable
- **Medium:** Some evidence but gaps, or data partially disagree
- **Low:** Limited data, mostly inferred, or data older than 12 months

In the pitch itself, only use High and Medium confidence claims. Low confidence items go in the appendix as "areas to strengthen."

---

## Pitch Construction Process

### Step 1: Identify Pitch DNA

Before writing anything, answer these questions:

1. **What's the single most impressive thing about this company?** (This determines pitch order)
2. **What's the 2-sentence description?** (This is non-negotiable — must be crystal clear)
3. **What's the unique insight?** (This separates a pitch from a product description)
4. **What's the "why now"?** (Timing thesis — what makes this moment right)
5. **What's the biggest weakness?** (Must have a prepared answer)

### Step 2: Assemble the Building Blocks

Map available data to the 8 pitch elements:

| Element | Source | Strength | Notes |
|---------|--------|----------|-------|
| What You Do | Intake / positioning-statement.md | | |
| Traction | Intake / scorecard.md | | |
| Unique Insight | Intake / research | | |
| Business Model | lean-canvas.md / revenue-model.md | | |
| Market Size | market-analysis.md / intake | | |
| Team | Intake | | |
| The Ask | Intake | | |
| Why Now | Wave 2 research / intake | | |

Strength ratings: Strong / Adequate / Weak / Missing

**Data Foundation Check:** Note whether each element is backed by validated research (from prior startup skills) or self-reported data (from intake only). This affects the scorecard in Phase 4.

### Step 3: Determine Pitch Order

Based on element strengths, select the template from `pitch-frameworks.md`:
- Strongest element is Traction → Traction-Led
- Strongest element is Team → Team-Led
- Strongest element is Insight → Insight-Led
- No clear standout → Pre-Traction (default)

### Step 4: Write the Narrative

Construct the pitch as a continuous story, not a collection of sections. Each element should flow naturally into the next. The narrative should feel like:

"Here's what we do. [Here's why it's working / Here's what we know / Here's who we are.] Here's the problem we're solving. Here's our solution. Here's how big this can get. Here's how we make money. Here's why we're the team to do it. Here's what we need."

### Step 5: Generate All Requested Formats

From the full narrative, derive each format by compression — not by rewriting from scratch. Each shorter format is a subset of the full pitch.

---

## Output File Templates

### pitch-full.md

```markdown
# Full Pitch Narrative: {product}
*Skill: startup-pitch | Generated: {date}*

## Pitch DNA
- **Lead element:** {traction/team/insight/market}
- **2-sentence opener:** {the opener}
- **Unique insight:** {one sentence}
- **Why now:** {timing thesis}
- **The ask:** {amount + milestones}
- **Data foundation:** {Validated (prior startup skills) / Self-reported (intake only)}

## Full Narrative (~10 minutes)

### Opening — What We Do
{2 sentences + specific example}

> **Speaker notes:** {delivery guidance — pace, emphasis, pauses}
> **Timing:** 0:00 - 0:45

### {Lead Element — varies by pitch type}
{Content}

> **Speaker notes:** {delivery guidance}
> **Timing:** 0:45 - 2:00

### Problem
{Problem description — severity, consequences, who suffers}

> **Speaker notes:** {delivery guidance}
> **Timing:** 2:00 - 3:00

### Solution
{How it works — describe the concrete user experience. What does the user SEE and DO? Not abstract features — the specific interaction that solves the problem. If the product exists, describe it as if showing a demo. If pre-launch, describe the intended experience vividly enough that the investor can picture it.}

> **Speaker notes:** {delivery guidance}
> **Timing:** 3:00 - 4:00

### Traction
{Metrics with timeframes — growth story. If no traction: skip this section, don't fake it.}

> **Speaker notes:** {delivery guidance}
> **Timing:** 4:00 - 5:00

### Market Size
{Bottom-up calculation — show the math: number of customers × price = addressable market. Beachhead + expansion path.}

> **Speaker notes:** {delivery guidance}
> **Timing:** 5:00 - 6:00

### Business Model
{One clear model — pricing, unit economics if available}

> **Speaker notes:** {delivery guidance}
> **Timing:** 6:00 - 6:30

### Why Now
{Timing thesis from Wave 2 research. Technology shift, behavioral change, regulatory move. If timing isn't strong, keep this brief or fold into another section.}

> **Speaker notes:** {delivery guidance}
> **Timing:** 6:30 - 7:00

### Team
{Accomplishments, not titles. For each person: name, role, most impressive specific result.}

> **Speaker notes:** {delivery guidance}
> **Timing:** 7:00 - 7:30

### The Ask
{Amount + milestones + timeframe. Be direct and confident.}

> **Speaker notes:** {delivery guidance}
> **Timing:** 7:30 - 8:00

### Close
{Final sentence — memorable, forward-looking. Leave them wanting to talk more.}

## Transition Sentences
{How each section flows into the next — so the pitch feels like a story, not a checklist}

## Red Flags
- {issues investors might raise}

## Yellow Flags
- {concerns to prepare for}

## Sources
- {key data sources used in the pitch}
```

### pitch-5min.md

```markdown
# Five-Minute Pitch: {product}
*Skill: startup-pitch | Generated: {date}*

## The Narrative (~5 minutes)

{Each element trimmed to its core claim + one supporting proof point. No secondary arguments — just the strongest version of each element.}

### Opening — What We Do (0:00 - 0:30)
{2 sentences + example}

### {Lead Element} (0:30 - 1:15)
{Core claim + proof}

### Problem + Solution (1:15 - 2:30)
{Problem in 2 sentences → solution as concrete experience}

### Market + Business Model (2:30 - 3:30)
{Bottom-up math + one-sentence model}

### Why Now + Team (3:30 - 4:30)
{Timing thesis + team accomplishments}

### The Ask (4:30 - 5:00)
{Amount + milestones + timeframe}

## Speaker Notes
{Pacing guidance — where to breathe, where to let silence work}

## Red Flags
- {concerns}

## Sources
- {key sources}
```

### pitch-2min.md

```markdown
# Two-Minute Pitch: {product}
*Skill: startup-pitch | Generated: {date}*

## The Script (~300 words)

{Word-for-word script, broken into natural paragraphs. Each paragraph = one element.}

## Delivery Notes
- **Opener pace:** Slow and clear — this is where understanding happens
- **Emphasis points:** {words/phrases to stress}
- **Natural pauses:** {where to breathe and let it sink in}
- **Energy peak:** {which sentence should have the most energy}
- **Close:** Confident, direct, unhurried

## Structure Breakdown
- **0:00 - 0:20:** What we do (2 sentences + example)
- **0:20 - 0:40:** Strongest signal (traction/insight/team)
- **0:40 - 1:00:** Problem + solution
- **1:00 - 1:20:** Market + business model
- **1:20 - 1:40:** Why us + why now
- **1:40 - 2:00:** The ask

## The Email Test
{Paraphrase of the pitch in one paragraph — what someone should be able to repeat after hearing it once}

## Red Flags
- {concerns}

## Sources
- {key sources}
```

### pitch-1min.md

```markdown
# Elevator Pitch: {product}
*Skill: startup-pitch | Generated: {date}*

## Formal Version (~150 words)
{For investor events, demo days, formal introductions. Structured: What We Do → Insight → Ask.}

## Casual Version (~100 words)
{For networking, dinner parties, hallway conversations. Conversational tone, no pitch structure visible. Sounds like you're telling a friend about your company.}

## When Someone Asks "So What Do You Do?"
{The 2-sentence answer + example that leads to "tell me more"}

## Delivery Notes
- Don't rush. 1 minute is longer than it feels.
- End with a question, not a statement — "Would that be useful for [your company]?" invites conversation.
- Match energy to context. Formal events: crisp, confident. Casual: relaxed, curious.

## Red Flags
- {concerns}
```

### pitch-email.md

```markdown
# Investor Email Pitch: {product}
*Skill: startup-pitch | Generated: {date}*

## Subject Line Candidates
| Subject Line | Angle | Best For |
|---|---|---|
| "{subject 1}" | {angle} | {investor type} |
| "{subject 2}" | {angle} | {investor type} |
| "{subject 3}" | {angle} | {investor type} |

## Cold Email (~500 words)

{Hook — one sentence that makes them read the next line}

{What we do — 2 sentences + example}

{Traction or insight — the strongest signal, with numbers}

{Why now — one sentence timing thesis}

{The ask — specific and direct}

{Close — easy next step, not "let me know your thoughts"}

## Follow-Up Email (~200 words)

{Shorter, references the first email. Adds one new data point. Clear CTA.}

## Personalization Notes
- **For angel investors:** Lead with the problem and your personal connection to it
- **For VCs:** Lead with traction or market size
- **For accelerators:** Lead with team and speed of execution
- **For strategic partners:** Lead with mutual opportunity

## Red Flags
- {email-specific concerns}

## Sources
- {key sources}
```

### pitch-appendix.md

```markdown
# Pitch Appendix: {product}
*Skill: startup-pitch | Generated: {date}*

## Top 10 Investor Questions (with Prepared Answers)

### Q1: {Most likely question}
**Short answer:** {2-3 sentences — for verbal delivery}
**Detailed answer:** {full explanation with data — for follow-up emails}
**Source:** {where the data comes from}

[Repeat for Q2-Q10]

## Objection Handling

### "{Objection 1}"
**Why they ask this:** {investor's concern}
**Response:** {how to address it honestly}
**Supporting data:** {evidence}

[Repeat for each common objection]

## Known Weaknesses
{Honest assessment of pitch gaps — with plans to address each. Identifying weaknesses proactively is stronger than hoping investors won't notice.}

## Financial Backup
{Detailed numbers if available from prior sessions. If not: note "Financial projections not yet validated — consider running startup-design for detailed modeling."}

## Competitive Detail
{Deeper competitive analysis for Q&A — from prior sessions if available. If not: note "Competitive landscape not fully mapped — consider running startup-competitors for battle cards."}

## Red Flags
- {appendix-specific concerns}

## Yellow Flags
- {areas needing more data}

## Data Gaps & Limitations
- {what data is missing — every pitch has blind spots, be explicit}

## Sources
- {all data sources used across all deliverables, with tier ratings}
```

## Post-Synthesis Verification

After writing all pitch deliverables (before the scorecard/review phase), run the Verification Agent protocol. See `references/verification-agent.md` for the full process. The verification step checks all deliverables for unlabeled claims, internal contradictions, confidence rating consistency, and startup-pitch-specific coherence (pitch claims vs. source data, cross-format consistency, pitch vs. appendix alignment, honesty checks).

---

### pitch-scorecard.md

```markdown
# Pitch Scorecard: {product}
*Skill: startup-pitch | Generated: {date}*

## Data Foundation
**Built with:** {Validated research (startup-design/competitors/positioning) / Self-reported data (intake only)}
{If self-reported: "Note: This pitch was built without validated research data. Scores in Market Sizing, Traction Honesty, and competitive Q&A may improve significantly after running startup-design or startup-competitors."}

## Scoring Rubric

| Dimension | Score (1-10) | Rationale |
|-----------|-------------|-----------|
| **Clarity** | | {Can someone explain what you do after hearing 2 sentences?} |
| **Strength Sequencing** | | {Is the most impressive element in the first 60 seconds?} |
| **Traction Honesty** | | {Are numbers accurate, timeframed, and real? Or acknowledged as missing?} |
| **Insight Quality** | | {Is the insight genuinely non-obvious and specific?} |
| **Market Sizing** | | {Is the math bottom-up with clear assumptions?} |
| **Business Model** | | {One model, clearly stated?} |
| **Team Credentials** | | {Specific, verifiable accomplishments?} |
| **Ask Clarity** | | {Amount + milestones + timeframe, stated with confidence?} |
| **Overall** | | |

## Verdict
- **65-80:** Investor-ready. Go pitch.
- **50-64:** Investor-ready with caveats. Address the weak dimensions first.
- **35-49:** Needs work. Iterate on the weakest areas before pitching.
- **Below 35:** Major gaps. Consider running startup-design or startup-positioning to strengthen the foundation.

## Weak Dimensions (Score < 7)
For each:
- **Dimension:** {name}
- **What's weak:** {specific problem}
- **How to fix:** {actionable suggestion}
- **Data needed:** {what information would strengthen this}

## Delivery Readiness
- [ ] 2-sentence opener practiced until effortless
- [ ] All numbers memorized (not read from notes)
- [ ] Prepared answers for top 5 investor questions
- [ ] Know the biggest weakness and how to address it
- [ ] Practiced with at least one person (or investor roleplay)

## Red Flags
- {scorecard-specific concerns}

## Yellow Flags
- {areas to watch}
```
