---
name: startup-design
description: Design, validate, and plan a startup from scratch. Covers market research, competitive analysis, business model, brand identity, product definition, financial projections, and validation experiments. Trigger when the user has a startup idea to explore, wants to validate a business concept, needs a business plan or lean canvas, asks for market sizing or competitive landscape, wants brand positioning or go-to-market strategy, or says anything like "I have an idea for..." or "is this idea worth pursuing". Also handles resuming from a previous checkpoint.
---

# Startup Design

A structured, multi-phase skill that takes a startup idea from raw concept to validated design. It produces a complete set of markdown documents organized by domain, with built-in progress tracking so work survives session interruptions.

## How It Works

The process has 8 numbered phases executed sequentially, plus a Pre-Flight Check (Phase 0.5) and a Customer Discovery gate (Phase 3.7). Each phase produces output files and updates the progress tracker. If a session is interrupted, resume from the last completed checkpoint.

```
PRE-FLIGHT → INTAKE → BRAINSTORM → RESEARCH → [Research Gate] → CUSTOMER DISCOVERY → [Interview Gate] → STRATEGY → BRAND → PRODUCT → FINANCIAL → VALIDATION
```

### Modes

**Full Mode (default):** Execute all phases in order, including Pre-Flight and Customer Discovery. Best for thoroughly designing a startup from scratch.

**Fast Track Mode:** When the user says they want a "quick validation," "rapid assessment," or similar, or when time/budget is clearly limited, run a compressed version:
1. Phase 0.5 (Pre-Flight Check) — always run, takes 5 minutes
2. Phase 1 (Intake) — shortened to 1 round of questions; capture any prior customer conversations
3. Phase 2 (Brainstorm) — 3 variations instead of 5-8
4. Phase 3 (Research) — Wave 1 + Wave 2 only (skip customer voice and distribution deep-dives)
5. Phase 3.5 (Research Gate) — go/no-go checkpoint
6. Phase 3.7 (Customer Discovery) — if founder has 5+ prior conversations, document them; if not, run at least 3 interviews before proceeding
7. Phase 4 (Strategy) — Lean Canvas only
8. Skip Phase 5 (Brand) and Phase 6 (Product)
9. Phase 7 (Financial) — Revenue model only, Stage A (assumption-based), no full projections
10. Phase 8 (Validation) — Scorecard + top 3 experiments only

Fast Track produces fewer files but still gives the founder a clear go/no-go signal with evidence. Note in PROGRESS.md that Fast Track mode was used, so a future session can expand to full mode if the idea passes validation.

### Language

Default output language is **English**. If the user writes in another language or explicitly requests one, use that language for all outputs instead.

---

> **Reference:** Read `references/output-guidelines.md` once at the start. It defines the standard file header/footer (title, date, phase, confidence, flags), cross-phase referencing format, quality examples of good vs. bad output, and how to handle mid-process pivots.

## Phase 0: Resume Check

Before anything else, check if a `PROGRESS.md` file exists in the working directory (or a project subdirectory). If it does, read it and resume from the last incomplete phase. Tell the user: "I found progress from a previous session. You completed [phases]. Picking up from [next phase]."

If no progress file exists, start from Phase 1.

---

## Phase 0.5: Pre-Flight Check

Before investing time in the full process, run a fast sanity check — 2-3 targeted searches, 5 minutes maximum. The goal is to surface any immediately disqualifying signals so the founder knows them upfront.

**Run these three checks:**

**1. Dominant solution check** — Does a well-funded, widely-adopted solution to this exact problem already exist? Search: `"{problem domain} software"`, `"{problem} tool site:producthunt.com"`, `"{problem} app reviews"`. If a clear market leader with 10k+ customers exists, flag it immediately — this is not a reason to stop, but the founder needs to know the competitive reality before starting.

**2. Precedent failure check** — Has a company tried this exact idea and failed publicly? Search: `"{startup idea} startup failed"`, `"{problem} startup shutdown"`, `"why {product category} failed"`. Prior failures are not disqualifying — they're learnings. But unknown prior failures are landmines.

**3. Regulatory/legal instant kill** — Is there an obvious legal reason this idea cannot exist? (E.g., specific financial regulations, data privacy laws in the target geography, licensing requirements.) A quick search prevents building toward a wall.

**Output:** A short message to the founder (3-5 bullet points max) with what was found. Use this format:

```
## Pre-Flight Check

✅ No dominant incumbent found — space appears open.
⚠️  [CompanyX] tried a similar approach in 2021 and shut down in 2023.
    Key reason: [one sentence]. Worth understanding before proceeding.
✅ No obvious regulatory blockers identified for [target market].

→ Ready to proceed to intake. The above is context, not a verdict.
```

Keep it brief. This is a heads-up, not a full analysis. The project directory and PROGRESS.md don't exist yet at this point — present the findings in the conversation, then save them to `{project-name}/00-intake/preflight.md` during the Phase 1 output step, once the project directory is created.

---

## Phase 1: Intake Interview

The quality of everything downstream depends on how much context you extract now. Don't rush this — a thorough intake saves hours of misdirection later.

> **Reference:** Read `references/intake-questions.md` for the full question set (idea, founders, market, business, constraints), the hard questions that surface blind spots, and interviewing technique.

Cover all five question areas plus the hard questions — they set the tone for the entire process and signal that this is an honest assessment, not a cheerleading session. Ask 3-5 questions at a time in a conversational flow, probe vague answers, and after 2-3 rounds summarize what you've understood and ask the user to confirm or correct.

### Output

Save the consolidated intake to `{project-name}/00-intake/brief.md` with all captured information organized clearly. The project name should be derived from the startup idea (kebab-case, e.g., `pet-health-tracker`).

Create `PROGRESS.md` at the project root with: project name, start date, language, a checklist of all phases including Pre-Flight (0.5) and Customer Discovery (3.7) — mark Pre-Flight and Phase 1 complete — and a Notes section for session state. Also save the Pre-Flight findings from Phase 0.5 to `00-intake/preflight.md` now that the directory exists.

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

Full agent briefs, search strategies, and output destinations live in the wave reference files — read the relevant file when spawning each wave:

- **Wave 1: Market Landscape** (3 agents) — A1 Market Sizing & Economics, A2 Industry Trends & Timing, A3 Regulatory & Compliance *(skip A3 if no regulatory exposure)*
- **Wave 2: Competitive Analysis** (3 agents) — B1 Direct Competitor Deep-Dives, B2 Indirect Competitors & Substitutes, B3 Competitor Go-to-Market
- **Wave 3: Customer & Demand** (3 agents) — C1 Customer Voice & Pain Points, C2 Demand Signals & Market Validation, C3 Target Audience Profiling
- **Wave 4: Distribution & Partnerships** (2 agents) — D1 Distribution Channels, D2 Geographic & Market Entry

Each wave must complete before the next starts. Pass key findings forward as context (Wave 1 findings to Wave 2 agents, competitor list and GTM findings to Wave 3, and so on). Agents run in parallel within a wave, or as sequential research blocks without the Agent tool.

### Raw → Synthesized

All agents save raw findings to `{project-name}/01-discovery/raw/`. After all waves complete, synthesize into 4 polished deliverables.

Synthesis is reasoning, not formatting — it's where the raw research becomes a decision. Before writing anything, think hard about how the pieces fit together: which sources conflict and which to trust, what the evidence actually supports versus what the founder hopes, and what it all means for *this* specific startup. This is the highest-leverage thinking in the whole process and every downstream phase inherits its quality, so if the model supports extended thinking, this is the place to spend it. A weak synthesis produces a tidy document that restates the inputs; a strong one reaches the non-obvious conclusions a sharp analyst would draw from the same evidence.

The synthesis must:
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

Reason it through before writing the verdict. Weigh the strongest signals against the red flags rather than averaging them into a noncommittal "it depends" — one fatal flaw can outweigh five promising signals, and one exceptional signal can justify proceeding despite rough edges. The founder is about to spend real time and money on your read of the evidence, so think hard about what the data genuinely supports.

Present a brief summary: "Here's what the research found." Cover market size, competition intensity, customer demand signals, and timing. Then give a clear recommendation:
- **Green light** — Data supports proceeding. Note the strongest signals.
- **Yellow light** — Mixed signals. Specify what's concerning and what would need to be true for success.
- **Red light** — Data argues against this approach. Suggest pivots if the research revealed adjacent opportunities.

Ask the founder: "Based on this, do you want to continue to full strategy, pivot the idea, or stop here?" Respect their decision, but make sure it's an informed one. Save the gate assessment in `{project-name}/01-discovery/research-gate.md`.

---

## Phase 3.7: Customer Discovery (Interviews)

Research tells you what the market looks like from the outside. Customer interviews tell you what the problem feels like from the inside. This is the single highest-signal validation step in the entire process — and the only one that requires real calendar time (typically 1-2 weeks).

> **Reference:** Read `references/customer-interview.md` for the full interview protocol, question structure, notes template, and synthesis guide.

### When to run this phase

Run this phase after the Research Gate green- or yellow-lights the idea. If the gate returned a red light and the founder chose to stop, skip this phase.

Because interviews interrupt the session flow, present the founder with an explicit choice:

- **Run interviews now (recommended)** — pause here, conduct the interviews over the coming days, and resume from this checkpoint (PROGRESS.md preserves the state).
- **Defer and continue** — proceed to Strategy on research data alone. State the consequences plainly: financial projections stay Stage A (assumption-based), the Final Assessment Dashboard will show "Customer Interviews: 0 conducted · deferred", and interviews become the #1 experiment in the Phase 8 validation playbook. A strategy built without customer contact is a hypothesis, not a validated direction — say this honestly, then respect the founder's decision without nagging.

**Exception — Fast Track Mode:** If the founder reported 5+ prior customer conversations in intake, document those conversations using the interview template and proceed. Flag all claims as `[Founder-reported]`. If fewer than 5 conversations happened, recommend running fresh interviews — minimum 5 in Full Mode, minimum 3 in Fast Track.

### Process

1. **Identify who to interview** — Using the primary persona from `01-discovery/target-audience.md`, define the exact profile. 5 interviews minimum.
2. **Conduct interviews** — Follow the protocol in `references/customer-interview.md`. Aim for 25-30 minutes each, problem-focused, no product pitching.
3. **Document each interview** — Save to `{project-name}/00-intake/interviews/interview-{N}.md` using the template from the reference file.
4. **Synthesize** — After all interviews, write `{project-name}/00-intake/interview-synthesis.md` covering: problem confirmation rate, behavior signals (who paid/built workarounds), key phrases, and assumption audit.

### Interview Gate: Proceed vs. Reassess

After synthesis, present a brief finding to the founder and apply this gate:

**Proceed to Phase 4 if:**
- 4+ of 5 interviewees confirm the core problem clearly and unprompted
- At least 2 show behavior signals (paid for something, built a workaround, actively searched)
- Problem language is consistent across interviews

**Pause and reassess if:**
- 3 or fewer of 5 confirm the problem (scale proportionally if more interviews were run)
- Everyone says "interesting" but no behavior signals exist
- The problem they describe doesn't match the proposed solution

Present the synthesis and gate result to the founder. If the result calls for reassessment, suggest specific pivots if the interviews pointed to an adjacent problem worth solving. Let the founder decide: pivot the idea, narrow the target, or stop.

Update PROGRESS.md with the interview gate result.

---

## Phase 4: Strategy

With research in hand, define the strategic foundations. Each document should reference specific findings from Phase 3 — strategy disconnected from research is just guessing.

> **References:** Read `references/frameworks.md` for canonical definitions of Lean Canvas, April Dunford Positioning, Value Proposition Canvas, and RICE/MoSCoW. Read `references/output-specs.md` (Phase 4 section) for the required structure of each file.

Produce in `02-strategy/`:
- `lean-canvas.md` — complete 9-block Lean Canvas
- `value-proposition.md` — value proposition canvas (jobs, pains, gains), one-sentence value prop, proof points
- `business-model.md` — revenue model, unit economics, scalability, dependencies and partnerships
- `positioning.md` — April Dunford's five components
- `go-to-market.md` — launch strategy, first 100 customers plan, ranked growth channels, milestones

Update PROGRESS.md.

---

## Phase 5: Brand

> **Checkpoint:** Before starting, briefly present the strategy summary to the founder: positioning, target market, business model. Ask: "Does this reflect your vision? Anything to adjust before we build the brand on top of it?"

Translate strategy into brand identity. The brand should feel like a natural extension of the positioning — not an afterthought.

> **Reference:** Read `references/output-specs.md` (Phase 5 section) for the required structure of each file.

Produce in `03-brand/`:
- `mission-vision-values.md` — mission, vision, 3-5 working values; generate 2-3 options for the user to choose from or remix
- `tone-of-voice.md` — personality traits, voice principles with "we are / we are not" examples, writing samples, vocabulary guide
- `brand-personality.md` — brand archetype, emotional attributes, visual direction, how the brand should feel vs. competitors

Update PROGRESS.md.

---

## Phase 6: Product

Define the product enough to start building or to brief a development team. Use the competitor feature analysis from `01-discovery/competitor-landscape.md` and customer pain hierarchy from `01-discovery/target-audience.md` to inform feature decisions — don't design in a vacuum.

> **References:** Use RICE or MoSCoW from `references/frameworks.md` for prioritization. Read `references/output-specs.md` (Phase 6 section) for the required structure of each file.

Produce in `04-product/`:
- `mvp-definition.md` — core hypothesis, must-have features, nice-to-haves, explicit out-of-scope, success criteria
- `feature-prioritization.md` — RICE/MoSCoW list, dependencies, T-shirt effort estimates, build order
- `user-journey.md` — end-to-end journey map, touchpoints and emotions, drop-off risks, the "aha moment"

Update PROGRESS.md.

---

## Phase 7: Financial

> **Checkpoint:** Before projections, confirm key assumptions with the founder: pricing, target customer volume, team size, timeline. These directly drive the numbers — getting them wrong here means the projections are fiction.

Ground the strategy in numbers. Be honest about assumptions — label everything as estimated and explain the reasoning. Pull unit economics benchmarks (CAC, LTV, churn, ACV) from `01-discovery/market-analysis.md` and competitor pricing from `01-discovery/competitor-landscape.md` to anchor projections in real data.

> **Reference:** Read `references/industry-benchmarks.md` for standard metrics by business model type (SaaS, marketplace, e-commerce, etc.). Compare the founder's projections against these benchmarks and flag any that fall outside normal ranges — both too pessimistic and too optimistic.

### Two-stage financial model

Financial projections at this point exist in one of two states depending on whether customer interviews (Phase 3.7) produced validated demand signals:

**Stage A — Assumption-Based (default, pre-revenue validation):**
Used when no real traction data exists. Label every number clearly as `[Assumption — unvalidated]`. The purpose is to map the financial structure and identify which assumptions are most sensitive, not to produce reliable forecasts.

**Stage B — Evidence-Based (if interview gate passed with strong behavior signals):**
Used when interviews confirmed willingness-to-pay, existing spend on workarounds, or pre-sales interest. Anchor projections to actual signals: "3/5 interviewees said they currently pay ~$200/month for a partial solution" is better data than a benchmark. Label these numbers as `[Estimate — grounded in interview data]`.

At the top of every financial file, include a one-line stage declaration:

```
**Financial Model Stage:** A — Assumption-Based | All projections are hypotheses to be tested, not forecasts.
```
or
```
**Financial Model Stage:** B — Evidence-Based | Key assumptions anchored to {N} customer interviews.
```

### Revenue Model

In `05-financial/revenue-model.md`:
- Pricing strategy with rationale
- Revenue projections (Month 1-12, Year 1-3) with every assumption stated explicitly
- Sensitivity analysis: what happens if key assumptions change by ±30%
- **For Stage A:** clearly mark which assumptions need validation experiments before the model becomes reliable

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
- **Assumption sensitivity table:** list the top 5 assumptions that, if wrong, would most change the projections. For each: current assumption, what happens if it's 50% worse, and how to validate it.

Update PROGRESS.md.

---

## Phase 8: Validation

This is the most actionable phase — it tells the founder exactly what to do next to test whether the idea works.

> **Reference:** Read `references/output-specs.md` (Phase 8 section) for the required structure of each file.

Produce in `06-validation/`:
- `validation-playbook.md` — experiments ordered cheapest-first, each with assumption tested, method, metrics, and pass/fail criteria; if interviews were deferred in Phase 3.7, they are experiment #1
- `risk-analysis.md` — likelihood × impact matrix across market, product, business, team, and financial risks, with mitigations and early warning signals
- `assumptions-tracker.md` — every critical assumption with confidence, test method, and status, as a table
- `experiment-design.md` — detailed design plus ready-to-use templates for the top 3 experiments
- `kill-criteria.md` — 5-7 specific, measurable stop/pivot conditions tied to experiments
- `scorecard.md` — 1-10 scores across 7 dimensions plus an unambiguous **Verdict** paragraph

Be honest. If the idea has weaknesses, say so clearly. The goal is to help the founder make a good decision, not to validate their ego.

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

| File | When to Read | ~Lines | Purpose |
|------|-------------|--------|---------|
| `output-guidelines.md` | At the start of every session (once) | ~126 | File headers/footers, cross-references, quality examples, pivot handling |
| `honesty-protocol.md` | At the start of every session (once) | ~69 | Honesty rules, data labels, anti-patterns |
| `research-principles.md` | Before starting Phase 3 (once) | ~54 | Source quality, cross-referencing, data gaps |
| `research-wave-1-market.md` | When spawning Wave 1 agents | ~206 | Agent templates for market sizing, trends, regulatory |
| `research-wave-2-competitors.md` | When spawning Wave 2 agents | ~220 | Agent templates for direct, indirect, GTM analysis |
| `research-wave-3-customers.md` | When spawning Wave 3 agents | ~233 | Agent templates for customer voice, demand, audience |
| `research-wave-4-distribution.md` | When spawning Wave 4 agents | ~132 | Agent templates for channels, geographic entry |
| `research-synthesis.md` | After all waves complete, before writing final files | ~110 | How to synthesize raw findings into deliverables |
| `research-scaling.md` | After intake, before Phase 3 | ~122 | Complexity scoring, tier definitions, wave configurations |
| `verification-agent.md` | After synthesis, before Phase 3.5 | ~117 | Verification protocol, universal + skill-specific checks |
| `intake-questions.md` | During Phase 1 (Intake) | ~60 | Full question set, hard questions, interviewing technique |
| `output-specs.md` | During Phases 4, 5, 6, and 8 | ~180 | File-by-file specs for Strategy, Brand, Product, Validation |
| `customer-interview.md` | Before Phase 3.7 (Customer Discovery) | ~189 | Interview protocol, question structure, synthesis guide |
| `frameworks.md` | During Phase 4 (Strategy), Phase 6 (Product), and Phase 8 (Validation) | ~107 | Lean Canvas, Dunford, VPC, RICE/MoSCoW definitions |
| `industry-benchmarks.md` | During Phase 7 (Financial) | ~66 | Standard metrics by business model type |
