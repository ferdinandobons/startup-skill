---
name: startup-design
description: Design, validate, and plan a startup from scratch. Covers market research, competitive analysis, business model, brand identity, product definition, financial projections, and validation experiments. Trigger when the user has a startup idea to explore, wants to validate a business concept, needs a business plan or lean canvas, asks for market sizing or competitive landscape, wants brand positioning or go-to-market strategy, or says anything like "I have an idea for..." or "is this idea worth pursuing". Also handles resuming from a previous checkpoint.
---

# Startup Design

A structured, multi-phase skill that takes a startup idea from raw concept to validated design. It produces a complete set of markdown documents organized by domain, with built-in progress tracking so work survives session interruptions.

## How It Works

The process has 8 phases executed sequentially. Each phase produces output files and updates the progress tracker. If a session is interrupted, resume from the last completed checkpoint.

```
INTAKE → BRAINSTORM → RESEARCH → STRATEGY → BRAND → PRODUCT → FINANCIAL → VALIDATION
```

### Modes

**Full Mode (default):** Execute all 8 phases in order. Best for thoroughly designing a startup from scratch.

**Fast Track Mode:** When the user says they want a "quick validation," "rapid assessment," or similar, or when time/budget is clearly limited, run a compressed version:
1. Phase 1 (Intake) — shortened to 1 round of questions
2. Phase 2 (Brainstorm) — 3 variations instead of 5-8
3. Phase 3 (Research) — Wave 1 + Wave 2 only (skip customer voice and distribution deep-dives)
4. Phase 4 (Strategy) — Lean Canvas only
5. Skip Phase 5 (Brand) and Phase 6 (Product)
6. Phase 7 (Financial) — Revenue model only, no full projections
7. Phase 8 (Validation) — Scorecard + top 3 experiments only

Fast Track produces fewer files but still gives the founder a clear go/no-go signal with evidence. Note in PROGRESS.md that Fast Track mode was used, so a future session can expand to full mode if the idea passes validation.

### Language

Default output language is **English**. If the user writes in another language or explicitly requests one, use that language for all outputs instead.

---

> **Reference:** Read `references/output-guidelines.md` once at the start. It defines the standard file header/footer (title, date, phase, confidence, flags), cross-phase referencing format, quality examples of good vs. bad output, and how to handle mid-process pivots.

## Phase 0: Resume Check

Before anything else, check if a `PROGRESS.md` file exists in the working directory (or a project subdirectory). If it does, read it and resume from the last incomplete phase. Tell the user: "I found progress from a previous session. You completed [phases]. Picking up from [next phase]."

If no progress file exists, start from Phase 1.

---

## Phase 1: Intake Interview

The quality of everything downstream depends on how much context you extract now. Don't rush this — a thorough intake saves hours of misdirection later.

### Core Questions

Ask these in a conversational flow, not as a rigid checklist. Group related questions naturally and adapt based on answers. Not every question applies to every startup — skip what's irrelevant.

**The Idea**
- What problem are you solving? Who has this problem?
- What's your proposed solution? How does it work?
- What triggered this idea? (personal pain, market observation, technical insight)
- Do you have any existing work? (prototypes, research, landing pages, waitlists)

**The Founder(s)**
- What's your background? Relevant domain expertise?
- Are you solo or do you have co-founders? What are their strengths?
- How much time can you dedicate? Full-time or side project?
- What's your budget/runway situation?

**The Market**
- Who is your ideal customer? Be as specific as possible.
- How do they currently solve this problem? (existing alternatives, workarounds)
- Do you know of direct competitors? Who are they?
- What geography/market are you targeting first?

**The Business**
- How do you plan to make money? (subscription, one-time, marketplace, freemium)
- Any idea of pricing?
- What does success look like in 6 months? 12 months? 3 years?
- What are your biggest unknowns or worries?

**Constraints & Preferences**
- Any technical constraints? (must be mobile-first, needs to integrate with X)
- Any strong opinions on brand/positioning? (premium vs accessible, playful vs serious)
- Regulatory considerations?

### Hard Questions

After the core questions, ask these deliberately uncomfortable questions. They surface blind spots early:
- "Why are you the right person to build this? What unfair advantage do you have?"
- "If Google/a well-funded competitor launched this tomorrow, what would you do?"
- "What's the strongest argument against this idea?"
- "Have you talked to potential customers? What did they actually say (not what you hoped they'd say)?"
- "What would make you walk away from this idea?"

Don't skip these — they set the tone for the entire process and signal that this is an honest assessment, not a cheerleading session.

### How to Interview

- Ask 3-5 questions at a time, not all at once
- Acknowledge and build on answers — show you're listening
- Probe vague answers: "You said 'small businesses' — can you narrow that down? Like, freelancers? 10-person agencies? Local retail?"
- After 2-3 rounds, summarize what you've understood and ask the user to confirm or correct

### Output

Save the consolidated intake to `{project-name}/00-intake/brief.md` with all captured information organized clearly. The project name should be derived from the startup idea (kebab-case, e.g., `pet-health-tracker`).

Create `PROGRESS.md` at the project root with: project name, start date, language, a checklist of all 8 phases (mark Phase 1 complete), and a Notes section for session state.

---

## Phase 2: Brainstorm

Before diving into research, explore the idea space. This prevents premature convergence on the first version of the idea.

### Process

1. **Diverge** — Generate 5-8 variations of the core idea. Push boundaries:
   - What if the target market was completely different?
   - What if the business model was inverted?
   - What if you solved a smaller/larger version of the problem?
   - What adjacent problems could you solve instead?
   - What would the "10x version" look like vs. the "simplest possible version"?

2. **Analyze** — For each variation, note:
   - What's exciting about it
   - What's risky or hard
   - How it changes the competitive landscape

3. **Converge** — Present the variations to the user. Help them identify which elements resonate. The goal isn't to pick one variation — it's to enrich the original idea with insights from the exploration.

4. **Refine** — Based on the user's reactions, crystallize the refined idea. Update the brief if the idea evolved significantly.

### Output

Save to `{project-name}/00-intake/brainstorm.md`. Update PROGRESS.md.

---

## Phase 2.5: Research Depth Assessment

After intake (and brainstorm if applicable), assess market complexity and present the Research Depth recommendation to the user.

> **Reference:** Read `references/research-scaling.md` for the complexity scoring matrix, tier definitions, wave configurations, and the user communication template.

### Process

1. Score three factors from the intake: market breadth (1-3), known competitors (1-3), geographic scope (1-3)
2. Sum the scores (range 3-9) and map to a tier: Light (3-4), Standard (5-7), Deep (8-9)
3. Present the Research Depth table to the user (see `research-scaling.md` for the exact template)
4. Wait for user response: **light**, **deep**, or **ok** to accept the recommendation
5. Record the selected tier in PROGRESS.md

The selected tier determines the number of agents per wave and search rounds per agent in Phase 3. See `research-scaling.md` for exact wave configurations per tier.

---

## Phase 3: Market Research

This is the most resource-intensive phase. It uses 4 sequential waves of web research, each building on the previous one's findings.

### Environment Detection

Check if the `Agent` tool is available (Claude Code) or not (Claude.ai, other environments):

- **Agent tool available:** Spawn subagents in parallel within each wave, as described below. This is faster (~3-5 min per wave).
- **Agent tool NOT available (Claude.ai, web):** Execute the research yourself, sequentially. For each wave, follow the same agent templates from the reference files, but run the searches one at a time in the main conversation. Cover the same topics and apply the same research principles — the output quality should be identical, it just takes longer. Do NOT skip any wave or reduce search depth because of the sequential mode.

### Web Search Availability

Phase 3 requires WebSearch. In Claude Code, the tool is always available — if the user hasn't pre-approved it, the system will prompt them for each search. If the user denies permission, or in environments where WebSearch doesn't exist at all, fall back to **Knowledge-Based Research Mode**: use your training data, clearly mark all findings with **[Knowledge-Based — not live data, verify independently]**, reduce confidence ratings by one level, and recommend the founder verify key claims manually. Note the mode in PROGRESS.md so future sessions know the research wasn't web-sourced.

> **References** — Read the relevant file for each wave:
> - `references/research-principles.md` — Cross-cutting rules (source quality, cross-referencing, quantification, handling search failures). Read this FIRST.
> - `references/research-wave-1-market.md` — Agent templates for Wave 1 (market sizing, trends, regulatory)
> - `references/research-wave-2-competitors.md` — Agent templates for Wave 2 (direct, indirect, GTM analysis)
> - `references/research-wave-3-customers.md` — Agent templates for Wave 3 (customer voice, demand, audience)
> - `references/research-wave-4-distribution.md` — Agent templates for Wave 4 (channels, geographic entry)
> - `references/research-synthesis.md` — How to synthesize raw findings into final deliverables
>
> Read only the principles file + the wave file you're currently executing. Don't load all wave files at once.

### Research Principles

- Each agent performs **5-8 web searches minimum**, drilling deeper with each round
- Cross-reference every key finding across 2-3 independent sources
- Rate source quality (Tier 1: analyst reports, Tier 2: tech press, Tier 3: blogs/social)
- Quantify everything — "$4.2B at 12.3% CAGR" not "the market is growing"
- Date all data and flag anything older than 18 months
- Note contradictions between sources rather than picking one

### Research Waves

**Wave 1: Market Landscape** (3 agents in parallel, or 3 sequential research blocks)
- A1: Market Sizing & Economics — TAM/SAM/SOM, unit economics benchmarks, market headwinds
- A2: Industry Trends & Timing — tech trends, investment/M&A activity, behavioral shifts, expert predictions
- A3: Regulatory & Compliance — current regulations, data privacy, upcoming changes, compliance costs
  *(Skip A3 if the startup has no regulatory exposure)*

Complete Wave 1 before starting Wave 2. Pass key findings as context.

**Wave 2: Competitive Analysis** (3 agents in parallel, or 3 sequential research blocks)
- B1: Direct Competitor Deep-Dives — full profiles on 5-8 competitors (product, pricing, funding, traction, strengths, weaknesses)
- B2: Indirect Competitors & Substitutes — alternative approaches, platform risk, switching costs
- B3: Competitor Go-to-Market — how competitors acquire customers, channel analysis, content strategy

Complete Wave 2 before starting Wave 3. Pass competitor list and GTM findings as context.

**Wave 3: Customer & Demand** (3 agents in parallel, or 3 sequential research blocks)
- C1: Customer Voice & Pain Points — Reddit, forums, reviews mining with verbatim quotes, pain hierarchy, language map
- C2: Demand Signals & Market Validation — search trends, pricing intelligence, Product Hunt signals, WTP evidence
- C3: Target Audience Profiling — personas, buying behavior, decision-making process, where to reach them

Complete Wave 3 before starting Wave 4.

**Wave 4: Distribution & Partnerships** (2 agents in parallel, or 2 sequential research blocks)
- D1: Distribution Channel Deep-Dive — channel ranking by ROI, SEO opportunity, partnership opportunities, first 90 days plan
- D2: Geographic & Market Entry — beachhead market recommendation, entry barriers, expansion path

### Raw → Synthesized

All agents save raw findings to `{project-name}/01-discovery/raw/`. After all waves complete, synthesize into 4 polished deliverables. The synthesis must:
- Connect dots across research areas (competitive gaps → customer pains → positioning opportunities)
- Highlight contradictions and explain which data to trust
- Rate confidence for each major claim (High / Medium / Low)
- Extract explicit strategic implications, not just facts

### Output Files

- `{project-name}/01-discovery/market-analysis.md` — Market size (TAM/SAM/SOM), growth, maturity, regulatory summary, timing assessment
- `{project-name}/01-discovery/competitor-landscape.md` — Competitor profiles, **structured comparison matrix** (table with columns: Name, Product, Pricing, Target, Funding, Traction, Key Strength, Key Weakness), positioning map, platform risk, vulnerability analysis
- `{project-name}/01-discovery/target-audience.md` — Persona(s), pain hierarchy, jobs-to-be-done, language map, buying behavior, channels
- `{project-name}/01-discovery/industry-trends.md` — Tech trends, investment signals, behavioral shifts, regulatory trajectory, strategic implications
- `{project-name}/01-discovery/confidence-dashboard.md` — Summary of data quality across all research. For each major claim, list: the claim, source tier (1/2/3), number of corroborating sources, confidence level (High/Medium/Low), and data age. This tells the founder where they're standing on solid ground vs. thin ice.

Update PROGRESS.md.

---

## Phase 3.5a: Research Verification

After synthesis completes and all deliverable files are written, run a verification pass to catch inconsistencies.

> **Reference:** Read `references/verification-agent.md` for the full verification protocol, universal checks, and skill-specific checks.

### Process

1. Spawn agent **V1: Verification** — it reads all deliverable files in `01-discovery/` and checks for: unlabeled claims, internal contradictions, confidence rating consistency, missing data gaps, missing flags, stale data, and duplicate-source false corroboration
2. V1 also runs startup-design-specific checks: cross-phase consistency (strategy reflects market data, product reflects customer pains, financial reflects business model, validation covers identified risks)
3. V1 produces `{project-name}/01-discovery/verification-report.md`
4. **If Critical issues found:** Pause and present issues to the user. Ask: fix first, or proceed as-is?
5. **If only Warnings/Info:** Show one-line summary and continue to Research Gate

In Claude.ai or when Agent tool is unavailable, run the verification checks yourself in the main conversation following the same protocol.

---

## Phase 3.5: Research Gate (Go/No-Go Checkpoint)

Before investing time in Strategy through Validation, pause and present the founder with an honest assessment based on research findings. This is a decision point, not a formality.

Present a brief summary: "Here's what the research found." Cover market size, competition intensity, customer demand signals, and timing. Then give a clear recommendation:
- **Green light** — Data supports proceeding. Note the strongest signals.
- **Yellow light** — Mixed signals. Specify what's concerning and what would need to be true for success.
- **Red light** — Data argues against this approach. Suggest pivots if the research revealed adjacent opportunities.

Ask the founder: "Based on this, do you want to continue to full strategy, pivot the idea, or stop here?" Respect their decision, but make sure it's an informed one. Save the gate assessment in `{project-name}/01-discovery/research-gate.md`.

---

## Phase 4: Strategy

With research in hand, define the strategic foundations. Each document should reference specific findings from Phase 3 — strategy disconnected from research is just guessing.

> **Reference:** Read `references/frameworks.md` for canonical definitions of Lean Canvas, April Dunford Positioning, Value Proposition Canvas, and RICE/MoSCoW prioritization. Use these to ensure consistent, accurate application of each framework.

### Lean Canvas

Build a complete Lean Canvas (1-page business model) in `02-strategy/lean-canvas.md`:
- Problem (top 3)
- Customer Segments
- Unique Value Proposition
- Solution
- Channels
- Revenue Streams
- Cost Structure
- Key Metrics
- Unfair Advantage

### Value Proposition

In `02-strategy/value-proposition.md`, define:
- The value proposition canvas (jobs-to-be-done, pains, gains)
- How the product addresses each pain and creates each gain
- The one-sentence value prop
- Proof points and credibility signals

### Business Model

In `02-strategy/business-model.md`, detail:
- Revenue model (how money comes in, pricing tiers)
- Unit economics (CAC, LTV, margins — even rough estimates)
- Scalability considerations
- Dependencies and key partnerships

### Positioning

In `02-strategy/positioning.md`, using April Dunford's positioning framework:
- Competitive alternatives (what happens if you don't exist)
- Unique attributes (what you have that alternatives don't)
- Value (what those attributes enable for customers)
- Target market (who cares the most)
- Market category (the context that makes the value obvious)

### Go-to-Market

In `02-strategy/go-to-market.md`:
- Launch strategy (where, how, to whom first)
- First 100 customers plan
- Growth channels ranked by expected impact and cost
- Partnerships and ecosystem plays
- Timeline with milestones

Update PROGRESS.md.

---

## Phase 5: Brand

> **Checkpoint:** Before starting, briefly present the strategy summary to the founder: positioning, target market, business model. Ask: "Does this reflect your vision? Anything to adjust before we build the brand on top of it?"

Translate strategy into brand identity. The brand should feel like a natural extension of the positioning — not an afterthought.

### Mission, Vision & Values

In `03-brand/mission-vision-values.md`:
- **Mission** — Why the company exists (present-tense, action-oriented)
- **Vision** — The world you're building toward (aspirational but credible)
- **Values** — 3-5 core values with brief explanations of what they mean in practice (not generic platitudes — values should help make decisions)

Generate 2-3 options for mission and vision for the user to choose from or remix.

### Tone of Voice

In `03-brand/tone-of-voice.md`:
- Brand personality traits (3-4 adjectives with definitions)
- Voice principles with "we are / we are not" examples
- Writing samples: how the brand sounds in different contexts (homepage headline, error message, social media post, customer email)
- Vocabulary guide: preferred terms vs. avoided terms

### Brand Personality

In `03-brand/brand-personality.md`:
- Brand archetype analysis (which archetype fits and why)
- Emotional attributes
- Visual direction suggestions (not full design, but adjectives and references)
- How the brand should feel compared to competitors

Update PROGRESS.md.

---

## Phase 6: Product

Define the product enough to start building or to brief a development team. Use the competitor feature analysis from `01-discovery/competitor-landscape.md` and customer pain hierarchy from `01-discovery/target-audience.md` to inform feature decisions — don't design in a vacuum.

> **Reference:** Use RICE or MoSCoW from `references/frameworks.md` for feature prioritization.

### MVP Definition

In `04-product/mvp-definition.md`:
- Core hypothesis the MVP tests
- Must-have features (the minimum set to test the hypothesis)
- Nice-to-have features (for v1.1, not v1.0)
- Explicitly out of scope (prevent scope creep)
- Success criteria: what results would validate the MVP

### Feature Prioritization

In `04-product/feature-prioritization.md`:
- Feature list with RICE or MoSCoW prioritization
- Dependencies between features
- Effort estimates (T-shirt sizing: S/M/L/XL)
- Recommended build order

### User Journey

In `04-product/user-journey.md`:
- End-to-end user journey map (from discovery to regular usage)
- Key touchpoints and emotions at each stage
- Drop-off risks and mitigation ideas
- The "aha moment" — when does the user first experience value?

Update PROGRESS.md.

---

## Phase 7: Financial

> **Checkpoint:** Before projections, confirm key assumptions with the founder: pricing, target customer volume, team size, timeline. These directly drive the numbers — getting them wrong here means the projections are fiction.

Ground the strategy in numbers. Be honest about assumptions — label everything as estimated and explain the reasoning. Pull unit economics benchmarks (CAC, LTV, churn, ACV) from `01-discovery/market-analysis.md` and competitor pricing from `01-discovery/competitor-landscape.md` to anchor projections in real data.

> **Reference:** Read `references/industry-benchmarks.md` for standard metrics by business model type (SaaS, marketplace, e-commerce, etc.). Compare the founder's projections against these benchmarks and flag any that fall outside normal ranges — both too pessimistic and too optimistic.

### Revenue Model

In `05-financial/revenue-model.md`:
- Pricing strategy with rationale
- Revenue projections (Month 1-12, Year 1-3) with assumptions stated
- Sensitivity analysis: what happens if key assumptions change by ±30%

### Cost Structure

In `05-financial/cost-structure.md`:
- Fixed costs (infrastructure, tools, salaries)
- Variable costs (per-user, per-transaction)
- One-time costs (development, legal, launch)
- Break-even analysis

### Projections

In `05-financial/projections.md`:
- 3 scenarios: conservative, base, optimistic
- Key assumptions for each scenario
- Cash flow timeline
- Funding needs and runway calculation

Update PROGRESS.md.

---

## Phase 8: Validation

This is the most actionable phase — it tells the founder exactly what to do next to test whether the idea works.

### Validation Playbook

In `06-validation/validation-playbook.md`:
- Ordered list of experiments to run, from cheapest/fastest to most expensive
- For each experiment:
  - What assumption it tests
  - How to run it (step-by-step)
  - What to measure
  - What result would validate vs. invalidate the assumption
  - Estimated time and cost
- Examples: landing page test, fake door test, concierge MVP, customer interviews, ad campaign test, wizard of oz, pre-sales

Tailor experiments to the specific idea — a B2B SaaS needs different validation than a consumer marketplace.

### Risk Analysis

In `06-validation/risk-analysis.md`:
- Risk matrix (likelihood × impact) for:
  - Market risks (no demand, timing, regulatory)
  - Product risks (can't build it, won't work)
  - Business risks (can't monetize, can't scale)
  - Team risks (missing skills, founder conflicts)
  - Financial risks (runway, CAC too high)
- For each high-priority risk: mitigation strategy and early warning signals

### Assumptions Tracker

In `06-validation/assumptions-tracker.md`:
- Every critical assumption the business plan rests on
- Current confidence level (high/medium/low)
- How to test each assumption
- Status: untested / testing / validated / invalidated

Format as a table for easy scanning and updating.

### Experiment Design

In `06-validation/experiment-design.md`:
- Detailed design for the top 3 recommended experiments
- Hypothesis, method, metrics, success criteria, timeline
- Templates the founder can use immediately (interview scripts, survey questions, landing page copy outline)

### Kill Criteria

In `06-validation/kill-criteria.md`, define 5-7 specific, measurable conditions under which the founder should stop or pivot. Tie each to a validation experiment. Be specific: "If fewer than 3/10 interview subjects say they'd pay $X" not "if there's no demand." This protects the founder from sunk-cost thinking.

### Idea Scorecard

At the end of the validation section, produce a summary scorecard in `06-validation/scorecard.md`:

| Dimension | Score (1-10) | Rationale |
|-----------|-------------|-----------|
| Problem severity | | |
| Market size | | |
| Competitive advantage | | |
| Feasibility | | |
| Business model clarity | | |
| Founder-market fit | | |
| Timing | | |
| **Overall** | | |

Be honest. If the idea has weaknesses, say so clearly. The goal is to help the founder make a good decision, not to validate their ego. Include a clear **Verdict** paragraph after the table with an unambiguous recommendation (see the scoring guide in the Radical Honesty Protocol).

Update PROGRESS.md — mark all phases complete.

---

## Final Deliverable

After all phases are complete, first print the **Final Assessment Dashboard** in the conversation (see `references/output-guidelines.md`, "Final Assessment Dashboard" section). This gives the founder an instant visual summary of all key findings before they dive into the files.

Then produce two final files:

**`README.md`** at the project root — executive summary:
- One-paragraph overview of the startup
- Key findings from research
- Strategic positioning summary
- Top 3 risks and how to mitigate them
- Confidence dashboard summary (what we know vs. what we're guessing)
- Links to all generated documents

**`action-plan-30-days.md`** — concrete weekly plan for the first month:
- **Week 1:** Customer discovery (who to contact, what to ask, how many conversations)
- **Week 2:** Validation experiments (which ones to run first, with specific steps)
- **Week 3:** MVP scoping (based on validation results, what to build/fake/skip)
- **Week 4:** Go/no-go decision and next phase planning
- Each week should have 3-5 specific, actionable tasks — not "do customer research" but "send 20 cold LinkedIn messages to [persona] using this template"

> **Anti-pattern check:** Before finalizing, scan the entire output for common founder anti-patterns and flag any you detect: "solution looking for a problem," "boiling the ocean" (too many features/markets at once), "premature scaling," "vanity metrics," "building in stealth too long," "ignoring unit economics." Include a brief **Anti-Patterns Detected** section in the README if any are present.

---

## Radical Honesty Protocol

> **Reference:** Read `references/honesty-protocol.md` at the start of every session for the full protocol. The key rules are summarized here.

This skill helps founders make good decisions, not feel good. Honesty is non-negotiable:

1. **Tell the truth.** If the market is too small or the idea has a fatal flaw, say so directly. Flag when founder assumptions contradict research data.
2. **Label claims.** Use **[Data]**, **[Estimate]**, **[Assumption]**, **[Opinion]** tags. Never present estimates as facts.
3. **Surface flags in every phase.** Include a **Red Flags** / **Yellow Flags** section at the end of every phase output.
4. **Clear verdict.** Scorecard must recommend: 8-10 proceed, 6-7 conditional, 4-5 concerns, 1-3 stop/pivot.
5. **Ground in evidence.** No data? Say so. Don't fabricate.
6. **Make it actionable.** Every document tells the founder what to do next.
7. **Track everything.** Update PROGRESS.md after each phase.

---

## Reference Files

The `references/` directory contains supporting documentation. Read only what you need for the current phase.

| File | When to Read | Lines |
|------|-------------|-------|
| `output-guidelines.md` | At the start of every session (once) | ~78 |
| `honesty-protocol.md` | At the start of every session (once) | ~69 |
| `research-principles.md` | Before starting Phase 3 (once) | ~54 |
| `research-wave-1-market.md` | When spawning Wave 1 agents | ~206 |
| `research-wave-2-competitors.md` | When spawning Wave 2 agents | ~220 |
| `research-wave-3-customers.md` | When spawning Wave 3 agents | ~233 |
| `research-wave-4-distribution.md` | When spawning Wave 4 agents | ~132 |
| `research-synthesis.md` | After all waves complete, before writing final files | ~104 |
| `research-scaling.md` | After intake, before Phase 3 | ~95 | Complexity scoring, tier definitions, wave configurations |
| `verification-agent.md` | After synthesis, before Phase 3.5 | ~100 | Verification protocol, universal + skill-specific checks |
| `frameworks.md` | During Phase 4 (Strategy), Phase 6 (Product), and Phase 8 (Validation) | ~110 |
| `industry-benchmarks.md` | During Phase 7 (Financial) | ~80 |
