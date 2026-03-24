---
name: startup-pitch
description: Build investor-ready pitch scripts in multiple formats (10-min, 5-min, 2-min, 1-min elevator, investor email). Produces pitch narratives, Q&A preparation, pitch scoring rubric, and optional investor roleplay practice. Use when the user wants to create a pitch, prepare for investor meetings, craft a startup pitch, write a fundraising narrative, or practice their pitch. Triggers for "pitch deck", "investor pitch", "pitch my startup", "fundraising deck", "seed deck", "how to pitch", "investor meeting", "demo day", "prepare pitch", "pitch script", "elevator pitch for investors", "pitch practice", "practice my pitch", "investor roleplay", or any request to present a startup to investors, accelerators, or partners. Works standalone — no prior startup-design session needed, but leverages its output if available.
---

# Startup Pitch

Build investor-ready pitch content in multiple formats. Uses a structured 7-element framework combined with a problem-solution-insight foundation to produce pitch narratives that are clear, compelling, and fundable.

## How It Works

```
INTAKE → RESEARCH (2 parallel waves) → PITCH CONSTRUCTION → REVIEW & PRACTICE
```

The process: understand the company deeply, research the investor audience and competitive framing, then construct the pitch. Typical runtime: 15-20 minutes in Claude Code (parallel agents), 30-40 minutes in Claude.ai (sequential).

### Core Philosophy

Three principles govern every output this skill produces:

1. **Clarity over sophistication.** "80% accurate and 100% clear beats the reverse." If a grandmother can't understand what you do, investors won't either. Eliminate jargon, acronyms, and marketing language.
2. **Lead with what's impressive.** You earn each additional minute of investor attention. Don't bury traction after 5 sections of problem setup — put the strongest signal right after "what you do."
3. **Make investors talk.** A pitch isn't a monologue. The more investors talk, the more they convince themselves. Structure the narrative to invite conversation, not shut it down.

### Language

Default output language is **English**. If the user writes in another language or explicitly requests one, use that language for all outputs instead.

---

## Phase 1: Intake

Short and focused — 1-2 rounds of questions. The goal is enough context to build a compelling pitch.

### Recommended Prior Work

A pitch built on validated data is significantly stronger than one built on self-reported answers. If you haven't already, consider running **startup-design** first — it provides market research, competitive analysis, business model, financial projections, and a validation scorecard that become the foundation of a much more credible pitch.

Not required. startup-pitch works standalone. But the quality difference is noticeable.

### Check for Prior Work

Before asking questions, check if prior sessions have been completed. Look for these files in the working directory or subdirectories:

**From startup-design:**
- `00-intake/brief.md` — product description and context
- `01-discovery/market-analysis.md` — market size, TAM/SAM/SOM
- `01-discovery/competitor-landscape.md` — competitor profiles
- `01-discovery/target-audience.md` — customer personas, pain points
- `02-strategy/lean-canvas.md` — business model summary
- `02-strategy/positioning.md` — positioning framework
- `05-financial/revenue-model.md` — revenue projections
- `06-validation/scorecard.md` — idea scorecard

**From startup-competitors:**
- `competitors-report.md` — competitive landscape
- `battle-cards/` — per-competitor profiles
- `pricing-landscape.md` — pricing analysis

**From startup-positioning:**
- `positioning-doc.md` — positioning document
- `positioning-statement.md` — positioning statements, elevator pitch
- `competitive-alternatives.md` — alternatives map
- `messaging-implications.md` — messaging hierarchy

If these files exist, read them and extract the pitch building blocks: product description, problem/solution, traction, team, market size, business model, positioning, competitive landscape. Tell the user: "I found data from a previous session. I'll use it to build your pitch."

Skip redundant intake questions. Go straight to pitch-specific questions if prior data is sufficient.

### What to Ask (if no prior data exists)

**Round 1 — The essentials (all required for a pitch):**
- What does your company do? (2 sentences max — this becomes the opening)
- What problem are you solving and for whom?
- What's your unique insight? (What do you know that others don't?)
- What traction do you have? (users, revenue, growth rate — with timeframes). If none: say so honestly, we'll build the pitch around insight and team instead.
- What's your business model? (one sentence — how do you make money?)
- Who's on the team? (names, roles, key accomplishments — not titles)
- How much are you raising and what will you do with it?

**Round 2 — Sharpening (only if needed):**
- What's your market size? (or enough data to calculate it)
- Who are your main competitors? What's your advantage?
- What milestones will you hit in 18-24 months with this funding?

**Pitch-specific questions:**
- Who is the audience? (VCs, angels, accelerator, demo day, specific fund?)
- What formats do you need? (10-min narrative, 2-min verbal, email pitch, all of them?)

Don't over-interview. A founder with clear answers to Round 1 has enough to build a strong pitch.

### The 2-Sentence Test

Before moving to research, crystallize the company description into exactly 2 sentences + one specific example. This is the foundation of the entire pitch.

Test: send it to a smart friend — could they paraphrase it back correctly? If not, simplify further.

> **Anti-pattern:** "We leverage AI-powered machine learning to optimize cross-functional synergies in the B2B SaaS vertical."
> **Better:** "We help sales teams find which leads will actually buy. Our tool analyzes email replies and tells reps exactly who to call next — last month one customer closed 40% more deals."

### Output

Save to `{project-name}/intake.md` — consolidated context for pitch construction. Project name: kebab-case (e.g., `ai-sales-assistant`).

Create `{project-name}/PROGRESS.md` with: project name, skill name (`startup-pitch`), start date, language, requested formats, target audience, research mode (Live / Knowledge-Based), and a phase checklist. Update it after each phase completes.

---

## Phase 1.5: Research Depth Assessment

After intake, assess market complexity and present the Research Depth recommendation to the user.

> **Reference:** Read `references/research-scaling.md` for the complexity scoring matrix, tier definitions, wave configurations, and the user communication template.

### Process

1. Score three factors from the intake: market breadth (1-3), known competitors (1-3), geographic scope (1-3)
2. Sum the scores (range 3-9) and map to a tier: Light (3-4), Standard (5-7), Deep (8-9)
3. Present the Research Depth table to the user (see `research-scaling.md` for the exact template)
4. Wait for user response: **light**, **deep**, or **ok** to accept the recommendation
5. Record the selected tier in PROGRESS.md

The selected tier determines the number of agents per wave and search rounds per agent in Phase 2. See `research-scaling.md` for exact wave configurations per tier.

---

## Phase 2: Research

Two parallel research waves exploring investor audience and competitive/market framing. Together they provide the raw material for a pitch that resonates with the target audience.

### Environment Detection

Check if the `Agent` tool is available:

- **Agent tool available (Claude Code):** Spawn all agents within each wave in parallel. This is faster.
- **Agent tool NOT available (Claude.ai, web):** Execute research sequentially, following the same templates. Same depth, just slower.

### Web Search

If WebSearch is unavailable, fall back to **Knowledge-Based Mode**: use training data, mark findings with **[Knowledge-Based — verify independently]**, and reduce confidence ratings by one level. Note the mode in PROGRESS.md.

> **Reference:** Read `references/research-principles.md` before starting any wave. It defines source quality tiers, cross-referencing rules, and how to handle data gaps.

### Wave 1: Audience & Narrative Intelligence

> **Reference:** Read `references/research-wave-1-audience-narrative.md` for agent templates.

Two agents (or two sequential blocks):

**A1: Investor & Audience Intelligence** — Research the target audience (VC firms, angels, accelerators). What are they investing in? What thesis do they follow? What metrics matter at this stage? What are red flags for them? What's the current fundraising climate in this space? Build an audience profile that shapes how the pitch is framed.

**A2: Comparable & Narrative Research** — Find comparable companies that pitched successfully in this space. What story did they tell? What analogies worked? What "X for Y" framing resonated? What market trends can the pitch ride? Find the narrative hooks — the facts, trends, or insights that make investors lean forward.

Complete Wave 1 before starting Wave 2. Pass key findings (audience expectations, comparable narratives) as context.

### Wave 2: Competitive Framing & Why Now

> **Reference:** Read `references/research-wave-2-competitive-framing.md` for agent templates.

Two agents (or two sequential blocks):

**B1: Competitive Framing for Pitch** — How competitors position themselves to investors. What narratives have worked for funded competitors? Where are the gaps in their stories that this pitch can exploit? What objections will investors raise based on the competitive landscape? Build a "pitch-aware" competitive frame.

**B2: Why Now & Market Timing** — Research the timing thesis. What technology shift, behavioral change, or regulatory move makes this the right moment? Find data to support the "why now" — trend charts, adoption curves, policy changes. Assess whether the timing narrative is genuinely strong or forced.

---

### Post-Research Checkpoint

After both waves complete, before synthesis, briefly present what the research found to the user: the investor audience profile, the strongest narrative hooks, the competitive framing angle, and the "why now" thesis. Ask: "Does this align with your pitch vision? Anything to adjust before I build the pitch?"

Keep it to one message — this is a quick alignment check, not a full report.

---

## Phase 3: Pitch Construction

> **Reference:** Read `references/pitch-frameworks.md` for the complete framework, including the integration matrix.
> **Reference:** Read `references/research-synthesis.md` for synthesis protocol and output templates.

Build the pitch using the integrated framework. The construction combines a problem-solution-insight foundation with a structured 7-element approach — see the integration matrix in `pitch-frameworks.md` for how they connect.

### The Foundation: Problem → Solution → Insight

Every pitch must communicate three things clearly:
1. **Problem** — The initial conditions. What's broken? Who suffers?
2. **Solution** — The experiment. What are you building to fix it?
3. **Insight** — Why this will work. What non-obvious truth powers this?

The insight is what separates a pitch from a product description. Without it, you're just another company doing X.

### The 8 Elements (Pitch Order)

The pitch is constructed using these elements, but the ORDER depends on what's most impressive about the company:

1. **What You Do** — 2 sentences + specific example. Impossible to misunderstand.
2. **[Lead with strength]** — Whatever is most impressive goes here: traction, team, insight, or market.
3. **Traction** — Metrics WITH timeframes. "0 to 1,000 users in 8 weeks" not "1,000 users."
4. **Unique Insight** — What do you know that others don't?
5. **Business Model** — One clear model. Not a menu of options.
6. **Market Size** — Bottom-up math. "50,000 customers × $50K ACV = $2.5B" not "$50B TAM."
7. **Team** — Specific accomplishments, not titles.
8. **The Ask** — Amount + milestones + timeframe.

### Pitch Ordering Logic

Determine the lead element based on founder strengths:
- **Strong traction?** → Lead with traction right after "What You Do"
- **Impressive team?** → Lead with team credentials
- **Breakthrough insight?** → Lead with the insight that creates an "aha" moment
- **Huge market?** → Lead with market opportunity

The default order for pre-traction companies: What You Do → Insight → Problem → Solution → Market → Business Model → Team → Ask.

### Construction Rules

- **No jargon.** If the user's pitch contains industry jargon, flag it and provide plain-language alternatives.
- **Specific > generic.** Replace every vague claim with a specific fact, number, or example.
- **Show, don't tell.** For the Solution section: describe what a user SEES and DOES — the concrete experience, not abstract features. "The rep opens the dashboard, sees 3 leads highlighted in green with a confidence score. They click one, see the email thread summary, and call. 30 seconds from login to action." This is far more powerful than "Our AI-powered platform surfaces high-intent leads."
- **Test the 2-sentence description.** If someone hearing it for the first time couldn't explain it back, simplify.

### ⏸ PAUSE — User Review

Present the pitch narrative structure to the user before generating final deliverables. Show: the opening (2 sentences + example), the ordering rationale, and the key narrative arc. Ask: "Does this story feel right? Is the ordering correct? Anything that's missing or should change?"

### Output Files

Every deliverable file must start with a standardized header: `# {Title}: {product}` followed by `*Skill: startup-pitch | Generated: {date}*`. Every deliverable must end with Red Flags, Yellow Flags, and Sources sections.

Generate all requested formats. If the user didn't specify, generate all of them.

**`{project-name}/pitch-full.md`** — Full pitch narrative (~10 minutes):
- Opening (2 sentences + example)
- Complete narrative following the ordered elements
- Speaker notes for each section (what to emphasize, where to pause, where to invite conversation)
- Transition sentences between sections
- Closing and ask

**`{project-name}/pitch-5min.md`** — Compressed narrative (~5 minutes):
- All 8 elements, trimmed to core claim + one supporting proof point
- Speaker notes focused on pacing

**`{project-name}/pitch-2min.md`** — Verbal pitch (~2 minutes, ~300 words):
- Word-for-word script
- The 2-sentence opener + strongest proof point + insight + ask
- Delivery notes (pace, emphasis, pauses)

**`{project-name}/pitch-1min.md`** — Elevator pitch (~1 minute, ~150 words):
- Two versions: formal (investor event) and casual (networking)
- What You Do + Insight + Ask only

**`{project-name}/pitch-email.md`** — Investor cold email (~500 words):
- Subject line candidates (3 options)
- Email body: hook → what you do → traction/insight → why now → ask → close
- Follow-up email template
- Personalization notes per investor type

**`{project-name}/pitch-appendix.md`** — Q&A preparation:
- Top 10 likely investor questions with prepared answers
- Objection handling (competitive threats, market risks, team gaps)
- Known weaknesses with honest answers and mitigation plans
- Financial and competitive backup (if available from prior sessions)

### Raw Data

Each agent saves its raw output to `{project-name}/raw/`. Agents must NOT write directly to deliverable paths — raw and synthesized output are separate.

Raw research files:
- `investor-audience.md`
- `comparable-narratives.md`
- `competitive-framing.md`
- `why-now-timing.md`

---

## Phase 3.5: Pitch Verification

After all pitch deliverables are written, before scoring and review, run a verification pass.

> **Reference:** Read `references/verification-agent.md` for the full verification protocol, universal checks, and skill-specific checks.

### Process

1. Spawn agent **V1: Verification** — it reads all deliverable files and checks for: unlabeled claims, internal contradictions, confidence rating consistency, missing data gaps, missing flags, stale data, and duplicate-source false corroboration
2. V1 also runs startup-pitch-specific checks: pitch claims vs. source data, cross-format consistency, pitch vs. appendix alignment, honesty checks (traction without timeframes, top-down TAM, titles without accomplishments)
3. V1 produces `{project-name}/verification-report.md`
4. **If Critical issues found:** Pause and present issues to the user. Ask: fix first, or proceed as-is?
5. **If only Warnings/Info:** Show one-line summary and continue to review phase

In Claude.ai or when Agent tool is unavailable, run the verification checks yourself in the main conversation following the same protocol.

---

## Phase 4: Review & Practice

After generating the pitch deliverables, review quality and optionally practice with investor roleplay.

### Step 1: Pitch Scoring Rubric

Review the completed pitch against each dimension. Score honestly — a high score on a weak pitch is useless in front of real investors.

Save to `{project-name}/pitch-scorecard.md`:

| Dimension | Score (1-10) | Rationale |
|-----------|-------------|-----------|
| **Clarity** — Can someone explain what you do after hearing 2 sentences? | | |
| **Strength Sequencing** — Is the most impressive element in the first 60 seconds? | | |
| **Traction Honesty** — Are numbers accurate, timeframed, and real? | | |
| **Insight Quality** — Is the insight genuinely non-obvious and specific? | | |
| **Market Sizing** — Is the math bottom-up with clear assumptions? | | |
| **Business Model** — One model, clearly stated? | | |
| **Team Credentials** — Specific, verifiable accomplishments? | | |
| **Ask Clarity** — Amount + milestones + timeframe, stated with confidence? | | |
| **Overall** | | |

**Verdict:**
- **65-80:** Investor-ready. Go pitch.
- **50-64:** Investor-ready with caveats. Address the weak dimensions first.
- **35-49:** Needs work. Iterate on the weakest areas before pitching.
- **Below 35:** Major gaps. Consider running startup-design first to strengthen the foundation.

For each dimension scoring below 7: explain what's weak and suggest a specific fix.

### Step 2: Iteration Loop

Present the scorecard to the user. For each dimension that scored below 7:
1. Explain the weakness
2. Ask: "How do we fix this? Do you have more data, or should we reframe?"
3. Iterate on the relevant pitch sections
4. Re-score after changes

### Step 3: Investor Roleplay (Optional)

After the scorecard review, offer practice: "Would you like to practice the pitch? I can play an investor and give you feedback."

If the user accepts:

**Choose an investor persona:**
- **Angel Investor** — Technical, focused on founders + idea. Asks "why you?" and probes domain expertise. Friendly but direct.
- **Seed VC** — Traction-obsessed, looking for product-market fit signals. Asks about metrics, retention, growth rate. Wants to see momentum.
- **Series A VC** — Scalability + market size obsessed. Asks about unit economics, competitive moats, expansion path. Thinking about the next round already.
- **Accelerator Partner** — Looking for coachability + speed of execution. Asks about what you've learned, how fast you ship, what you'd do with mentorship.

**Roleplay flow:**
1. The user delivers their pitch (any format)
2. Stay in character as the chosen investor persona
3. Ask 3-5 questions that this type of investor would ask — drawn from the appendix but adapted to the persona
4. Push back on weak points — investors do this, and the founder needs practice handling it
5. After the Q&A, break character and provide feedback:
   - What landed well
   - Where the investor would have tuned out
   - Which answers were strong vs. unconvincing
   - Specific suggestions for improvement

**Multiple rounds:** The user can practice multiple times with different personas. Each round surfaces different weaknesses.

### Step 4: Delivery Tips

Include practical delivery advice in the scorecard file:
- **The 60-second rule:** You earn each additional minute. If the first 60 seconds aren't compelling, the rest doesn't matter.
- **Invite conversation.** Pause after the insight. If an investor starts talking, let them — they're selling themselves.
- **Own the numbers.** If asked about a metric, know the exact figure and how you calculated it.
- **Handle "I don't know" well.** "I don't know, but here's how I'd find out" beats a fabricated answer.
- **Practice the 2-sentence opener** until it's effortless. This is the single most important part of the pitch.

Update PROGRESS.md — mark all phases complete.

---

## Honesty Protocol

> **Reference:** Read `references/honesty-protocol.md` for full protocol and anti-pattern details.

A pitch that overpromises destroys founder credibility. Core rules apply (label claims, quantify, declare gaps), plus pitch-specific additions:

1. **No inflated metrics.** If traction is weak, the pitch should acknowledge it and pivot to insight, team, or speed of execution. Fabricated traction will surface in due diligence and kill the deal.
2. **Honest market sizing.** Bottom-up math only. Top-down TAM without justification is a red flag to investors — they've seen it thousands of times.
3. **Real team credentials.** Specific, verifiable accomplishments. "Built X that did Y" — not vague titles or puffed-up bios.
4. **Flag pitch weaknesses.** Every pitch has gaps. Identifying them proactively (and having a plan to address them) is stronger than pretending they don't exist.
5. **Label claims.** Use **[Data]**, **[Estimate]**, **[Assumption]**, **[Opinion]** tags in supporting materials.

| Anti-Pattern | What It Looks Like | What to Say |
|---|---|---|
| Inflated TAM | "$50B market" with no math | "Show the bottom-up calculation. Investors do the math." |
| Vanity traction | "10K signups" with no activation | "Signups aren't traction. What % actually use the product?" |
| Jargon overload | "AI-powered blockchain synergy" | "What does it actually DO? Say it in words a 10-year-old understands." |
| No insight | Describing a product, not a thesis | "Why will THIS approach work? What do you know that others don't?" |
| Weak team | Titles without achievements | "What have you DONE? Accomplishments, not positions." |
| Vague ask | "We're raising a round" | "How much? For what milestones? In what timeframe?" |
| "No competition" | "We're the first to do this" | "What do customers do TODAY instead? That's your competition." |

---

## Reference Files

Read only what you need for the current phase.

| File | When to Read | ~Lines | Purpose |
|------|-------------|--------|---------|
| `honesty-protocol.md` | Start of session | ~62 | Full honesty protocol with pitch anti-patterns |
| `research-principles.md` | Before starting Phase 2 | ~64 | Source quality, cross-referencing, data gaps |
| `research-wave-1-audience-narrative.md` | When running Wave 1 | ~164 | Agent templates for investor + narrative research |
| `research-wave-2-competitive-framing.md` | When running Wave 2 | ~159 | Agent templates for competitive framing + why now |
| `pitch-frameworks.md` | During Phase 3 | ~261 | Complete pitch framework with integration matrix |
| `research-synthesis.md` | After waves complete | ~417 | Synthesis protocol and output templates |
| `research-scaling.md` | After intake, before Phase 2 | ~75 | Complexity scoring, tier definitions, wave configurations |
| `verification-agent.md` | After pitch construction | ~80 | Verification protocol, universal + skill-specific checks |
