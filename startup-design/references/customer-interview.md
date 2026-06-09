# Customer Interview Protocol

Before building strategy, brand, or product, validate assumptions with real people.
This document is read during **Phase 3.7: Customer Discovery** — between research synthesis and strategy.

The goal is not to confirm your idea. The goal is to find out if the problem you think exists actually exists, how painful it is, and whether the people who have it are willing to do something about it.

---

## Why interviews beat surveys (and AI research)

Web research tells you what people have already said publicly. Interviews tell you what they actually do, struggle with, and would pay for. The two are often different. A customer who writes a glowing review on G2 may use a tool for 5 minutes a month; one who complains on Reddit may be a daily power user desperate for something better. Only conversation reveals the difference.

Rule of thumb: **5 honest conversations beat 500 data points** when you're trying to understand whether a problem is real and worth solving.

---

## Who to interview

Target people who match the persona identified in `01-discovery/target-audience.md`. Be specific:

- **Right:** "B2B SaaS sales managers at 20-200 person companies who currently use a CRM"
- **Wrong:** "Anyone who might need this"

If the target-audience file identified multiple personas, start with the one most likely to be an early adopter — the person with the sharpest pain, not the broadest appeal.

**Minimum viable sample:** 5 interviews. Patterns start emerging at 5; beyond 12-15, you get diminishing returns at this stage.

**How to find them:**
- LinkedIn: search by role + industry + company size, message directly
- Reddit/Slack/Discord: communities where your target hangs out (surfaced in Wave 3 research)
- Warm network: founders, former colleagues, friends-of-friends who match the persona
- Twitter/X: people who complain about the problem in public

**Incentives:** 20-30 minutes of their time. Offer a gift card ($15-25) if the persona is hard to reach. Never pay for opinions on your product — it biases answers.

---

## The interview structure (25-30 minutes)

### Opening (2 minutes)

"I'm researching how [persona type] handle [problem domain]. I'm not selling anything — I'm trying to understand the problem before building a solution. I'll ask you about your current experience. There are no right or wrong answers. Is it okay if I take notes?"

This framing removes social pressure to be nice about an idea you haven't mentioned yet.

### Part 1: Context (5 minutes)

Understand their world before you ask about the problem.

- "Walk me through a typical week in your role. What takes up most of your time?"
- "What tools do you use for [relevant domain]?"
- "How long have you been doing this?"

Don't ask leading questions. Don't mention your solution. Listen for the words they use to describe their work — these become the language map for messaging later.

### Part 2: The problem (10 minutes)

This is the core of the interview. Go deep.

- "Tell me about the last time you had to deal with [problem domain]. Walk me through what happened."
- "How often does this come up?"
- "What do you do today to handle it?"
- "What's the most frustrating part of that process?"
- "What have you tried? What didn't work?"
- "If you could wave a magic wand and fix one thing about this, what would it be?"

**Do NOT ask hypotheticals like "would you use a tool that..."** — hypothetical answers are worthless. People are notoriously bad at predicting their own behavior. Stick to past behavior and current workarounds.

### Part 3: Behavior signals (8 minutes)

- "Have you ever paid for something to solve this? What, and how much?"
- "Have you ever built a workaround yourself — a spreadsheet, a script, anything custom?"
- "Have you looked for a solution? What did you find? Why didn't it work?"
- "Who else in your organization deals with this problem?"

**Paying, building workarounds, or actively searching are the strongest signals.** Someone who "would theoretically be interested" is not a customer. Someone who already pays for an imperfect solution is.

### Part 4: Wrap-up (3 minutes)

- "Is there anything about this I didn't ask that you think is important?"
- "Is there anyone else you'd recommend I talk to who has this problem?"
- "Would it be okay if I followed up with a quick question later?"

---

## How to listen

**The Mom Test rule (Rob Fitzpatrick):** People will not tell you your idea is bad because they don't want to hurt your feelings. They'll say "that's interesting" and "I could see that being useful." These phrases mean nothing. Anchor to behavior, not opinion.

- Watch for **energy**: does their voice change when they describe the problem? Frustration = real pain.
- Watch for **specificity**: "sometimes it's annoying" vs. "last Tuesday I spent 3 hours fixing this manually and still got it wrong." The second is a real problem.
- Watch for **volunteered solutions**: if they tell you what they wish existed without you asking, pay close attention.
- Watch for **workarounds**: any system, hack, or manual process they've built is evidence the problem is real and unsolved.

---

## After each interview: notes template

Save each interview summary to `{project-name}/00-intake/interviews/interview-{N}.md`:

```markdown
# Customer Interview {N}

**Date:** {date}
**Interviewee:** {role, company size, industry} — do NOT record name unless consented
**Duration:** {minutes}

## Context
{2-3 sentences about their role and world}

## Problem signals
- {Quote or paraphrase of key pain expressed}
- {Quote or paraphrase}

## Current solution/workaround
{What they do today. Is it paid? Self-built? Manual?}

## Behavior signals
- [ ] Currently pays for a solution (what, how much: {details})
- [ ] Has built a workaround themselves ({details})
- [ ] Has actively searched for alternatives ({details})
- [ ] Has complained publicly about this ({details})

## Key phrases (use their exact words)
- "{exact quote}"
- "{exact quote}"

## Surprises or unexpected findings
{Anything that contradicted your assumptions}

## Follow-up
- [ ] Okay to follow up: {yes/no}
- [ ] Referred me to: {details or none}
```

---

## Synthesis: what to look for across interviews

After 5+ interviews, look for patterns in `{project-name}/00-intake/interview-synthesis.md`:

**Problem validation:**
- Do at least 4 of 5 interviewees describe the same core problem unprompted? (the Interview Gate threshold)
- Do they use similar language to describe it?
- Is the pain acute (happens often, costs time/money/stress) or mild (annoying but ignorable)?

**Demand signals:**
- Has anyone already paid for a partial solution?
- Has anyone built a workaround?
- Did anyone ask "when can I try it?" without being prompted?

**Assumption audit:**
Update the assumptions tracker in `06-validation/assumptions-tracker.md`. For each assumption the intake generated, note: **Confirmed**, **Contradicted**, or **Unclear**.

**Red flags from interviews:**
- 3 or fewer of 5 confirm the problem exists → the problem may be invented, not discovered
- Nobody has paid for anything related → willingness-to-pay is unproven
- All interviewees say "I'd use it" but nobody has ever tried to solve it → low urgency
- The problem they describe is different from the one you designed for → pivot needed

---

## When to proceed vs. when to stop

**Proceed to Phase 4 (Strategy) if:**
- 4+ of 5 interviewees confirm the problem clearly and unprompted
- At least 2 have paid for a related solution or built a workaround
- The problem language is consistent across interviews (sign that it's a real, shared pain)

**Pause and reassess if:**
- 3 or fewer of 5 confirm the problem
- Everyone says "interesting" but nobody has ever tried to solve it
- The problem they describe doesn't match your proposed solution

**Document the outcome** in `{project-name}/00-intake/interview-synthesis.md` and update `PROGRESS.md`. If the interviews surface a significant pivot, trigger the pivot protocol from `output-guidelines.md`.

---

## Fast Track mode

If the founder has already spoken to 5+ potential customers before starting this process:

1. Ask: "Can you summarize what you heard? Key pains, exact quotes if you remember them, and whether anyone had already paid for something."
2. Document their answers in `interview-synthesis.md` directly.
3. Flag that interviews are founder-reported, not independently conducted: add `[Founder-reported — verify independently]` to any claims derived from this.
4. Skip the interview structure above and proceed to Phase 4.

If the founder has spoken to fewer than 5 people, recommend running fresh interviews — minimum 5 in Full Mode, minimum 3 in Fast Track. Document any prior conversations as `[Founder-reported]` context anyway.
