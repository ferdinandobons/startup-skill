---
name: startup-design
description: |
  Comprehensive startup design and idea validation — from market research to brand identity to financial projections. Use this skill whenever the user wants to design a startup, validate a business idea, create a business plan, define brand positioning, analyze a market opportunity, or build a go-to-market strategy. Also trigger when the user mentions "startup," "business idea," "business plan," "market research," "lean canvas," "value proposition," "MVP," "go-to-market," "brand identity," "competitive analysis," or wants to evaluate whether an idea is worth pursuing. Even if the user just says "I have an idea for..." — this skill applies.
---

# Startup Design

A structured, multi-phase skill that takes a startup idea from raw concept to validated design. It produces a complete set of markdown documents organized by domain, with built-in progress tracking so work survives session interruptions.

## How It Works

The process has 7 phases executed sequentially. Each phase produces output files and updates the progress tracker. If a session is interrupted, resume from the last completed checkpoint.

```
INTAKE → BRAINSTORM → RESEARCH → STRATEGY → BRAND → PRODUCT → FINANCIAL → VALIDATION
```

## Language

Default output language is **English**. If the user writes in another language or explicitly requests one, use that language for all outputs instead.

---

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

### How to Interview

- Ask 3-5 questions at a time, not all at once
- Acknowledge and build on answers — show you're listening
- Probe vague answers: "You said 'small businesses' — can you narrow that down? Like, freelancers? 10-person agencies? Local retail?"
- After 2-3 rounds, summarize what you've understood and ask the user to confirm or correct

### Output

Save the consolidated intake to `{project-name}/00-intake/brief.md` with all captured information organized clearly. The project name should be derived from the startup idea (kebab-case, e.g., `pet-health-tracker`).

Create `PROGRESS.md` at the project root:

```markdown
# Startup Design Progress

**Project:** {project-name}
**Started:** {date}
**Language:** {language}

## Phases

- [x] Phase 1: Intake — completed {date}
- [ ] Phase 2: Brainstorm
- [ ] Phase 3: Market Research
- [ ] Phase 4: Strategy
- [ ] Phase 5: Brand
- [ ] Phase 6: Product
- [ ] Phase 7: Financial
- [ ] Phase 8: Validation

## Notes
{any relevant notes about session state}
```

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

## Phase 3: Market Research

This is the most resource-intensive phase. Use multiple subagents running in parallel to search the web, organized in waves to avoid context saturation.

### Research Waves

Each wave spawns 2-4 subagents in parallel. Wait for a wave to complete before starting the next, because later waves build on earlier findings.

**Wave 1: Market Landscape**
Spawn agents for:
- Market size and growth (TAM/SAM/SOM for the target market)
- Industry trends and recent developments
- Regulatory environment (if applicable)

Each agent should use WebSearch with specific, targeted queries. Example queries for a pet health app:
- "pet health technology market size 2025"
- "pet wellness app industry growth trends"
- "veterinary telemedicine market report"

**Wave 2: Competitive Analysis**
Based on Wave 1 findings, spawn agents for:
- Direct competitors (products solving the same problem)
- Indirect competitors (alternative approaches to the same problem)
- Potential future competitors (adjacent companies that could enter)

For each competitor, research: product offering, pricing, target market, strengths, weaknesses, funding, traction signals (reviews, social media presence, job postings).

**Wave 3: Customer & Demand**
Spawn agents for:
- Customer pain points (forums, Reddit, social media complaints)
- Existing demand signals (search volume, trending topics)
- Customer willingness to pay (pricing benchmarks in the space)

**Wave 4: Distribution & Channels**
Spawn agents for:
- How competitors acquire customers
- Relevant communities and platforms where target users gather
- Partnership and distribution opportunities

### Agent Instructions

When spawning research agents, give each a focused brief:

```
Research task: {specific topic}
Context: We're designing a startup that {one-sentence description}.
Target market: {market}

Search the web for current, factual data on: {specific questions}

Structure your findings as:
- Key data points (with sources where possible)
- Notable insights or surprises
- Gaps in available information

Save your findings to: {specific file path}
```

### Synthesizing Results

After all waves complete, read through all the raw research and synthesize into the output files. The synthesis is where you add value — don't just concatenate, but identify patterns, contradictions, and implications.

### Output Files

- `{project-name}/01-discovery/market-analysis.md` — Market size (TAM/SAM/SOM), growth trajectory, key drivers, market maturity stage
- `{project-name}/01-discovery/competitor-landscape.md` — Competitor matrix, positioning map, gaps in the market, competitive advantages to pursue
- `{project-name}/01-discovery/target-audience.md` — Persona(s), pain points, current alternatives, willingness to pay, where they hang out
- `{project-name}/01-discovery/industry-trends.md` — Macro trends, technology shifts, regulatory changes, timing considerations

Update PROGRESS.md.

---

## Phase 4: Strategy

With research in hand, define the strategic foundations. Each document should reference specific findings from Phase 3 — strategy disconnected from research is just guessing.

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

Define the product enough to start building or to brief a development team.

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

Ground the strategy in numbers. Be honest about assumptions — label everything as estimated and explain the reasoning.

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

Be honest. If the idea has weaknesses, say so clearly. The goal is to help the founder make a good decision, not to validate their ego.

Update PROGRESS.md — mark all phases complete.

---

## Final Deliverable

After all phases are complete, create a `README.md` at the project root that serves as an executive summary:
- One-paragraph overview of the startup
- Key findings from research
- Strategic positioning summary
- Top 3 risks and how to mitigate them
- Recommended next steps (first 30 days)
- Links to all generated documents

---

## Important Principles

1. **Be honest, not encouraging.** A skill that tells every founder their idea is great is worthless. Surface real risks, question weak assumptions, and point out when the market says "no." The most valuable thing you can do is help someone avoid spending a year on a doomed idea.

2. **Ground everything in evidence.** Every claim in the strategy and brand sections should trace back to something from the research phase. If you don't have data, say so explicitly.

3. **Make it actionable.** Every document should leave the founder knowing what to do next. Avoid abstract frameworks that don't connect to concrete actions.

4. **Respect the founder's time.** Don't generate filler. If a section isn't relevant to this particular startup, skip it and note why in PROGRESS.md.

5. **Track everything.** Always update PROGRESS.md after completing each phase. This is the user's lifeline if the session breaks.
