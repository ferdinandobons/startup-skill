# Verification Agent Protocol

After synthesis completes, spawn a **Verification Agent (V1)** that audits all deliverables for consistency, accuracy, and completeness. This step catches issues that individual agents and synthesis can miss.

## When to Run

- After all positioning deliverables are written
- Before presenting the final output to the user
- Uses one agent: **V1: Verification**

## Agent Task

The V1 agent reads ALL deliverable files (not raw files) and checks them against the rules below. It produces a `verification-report.md` in the project directory.

## Universal Checks

These apply to every skill in the startup plugin:

### 1. Claims Without Source
Every quantitative claim must have a data label: **[Data]**, **[Estimate]**, **[Assumption]**, or **[Opinion]**. Flag any number, percentage, or factual assertion without a label.

### 2. Internal Contradictions
Cross-check numbers and statements across deliverable files. Flag when:
- The same metric appears with different values in two files
- A claim in one file contradicts a claim in another
- Confidence ratings disagree (e.g., "High confidence" in one file, different data in another suggests Medium)

### 3. Confidence Rating Consistency
Verify that confidence ratings match the evidence:
- A claim with only one Tier 3 source cannot be rated **High**
- A claim with multiple Tier 1 sources should not be rated **Low**
- Every major section must have a confidence rating

### 4. Data Gaps Declared
Every deliverable must have a Data Gaps section. Flag:
- Files missing the Data Gaps section entirely
- Sections where data is clearly thin but no gap is declared
- Gaps mentioned in raw files that didn't make it into the synthesized deliverables

### 5. Flags Present
Every deliverable must end with Red Flags and Yellow Flags sections. Flag:
- Files missing these sections
- Files with "No flags identified" where the content clearly contains risks

### 6. Stale Data
Flag any data point older than 18 months that isn't marked as potentially outdated.

### 7. Duplicate Sources
Flag when the same source is used as "independent corroboration" in multiple places. Two claims both citing the same blog post don't have independent verification.

## Skill-Specific Checks: startup-positioning

In addition to the universal checks above, verify:

### Positioning Statement vs. Research
- The Moore positioning statement must use the exact best-fit customer profile from `positioning-doc.md` Component 4
- The category in the statement must match the recommended category from `market-category-analysis.md`
- The differentiator must map to a verified unique attribute from Component 2
- The Neumeier Onliness Statement must pass: does "only" genuinely hold up given the competitive alternatives in `competitive-alternatives.md`?

### JTBD vs. Customer Intelligence
- Jobs-to-be-done referenced in the positioning must have evidence in `competitive-alternatives.md`
- Best-fit customer characteristics must connect to actual pain points from customer intelligence research
- Value themes must trace back to real customer language from the language map

### Cross-Deliverable Coherence
- The messaging hierarchy in `messaging-implications.md` must reflect the positioning priority from `positioning-doc.md`
- Category label must be consistent across all deliverables
- Words to use/avoid must not contradict the language used in positioning statements
- Freemium positioning (if present) must be consistent across `positioning-statement.md` and `messaging-implications.md`

### Validation Test Results
- If Neumeier Onliness Test is marked "Pass" but the basic statement contains qualifiers or hedging, flag it
- If Moore Template is marked "Pass" but any field is vague or generic, flag it
- If Mental Ladder test is marked "Pass" but the position requires more than 10 words to state, flag it

## Output: verification-report.md

```markdown
# Verification Report: {project-name}
*Generated: {date}*

## Summary
- **Critical issues:** {count}
- **Warnings:** {count}
- **Info:** {count}

## Critical Issues
Issues that could mislead decision-making. The process pauses here for user review.

### {Issue title}
- **File(s):** {affected files}
- **Section:** {section name}
- **Problem:** {description}
- **Suggested fix:** {how to resolve}

## Warnings
Issues that reduce quality but don't block decisions.

### {Issue title}
- **File(s):** {affected files}
- **Problem:** {description}
- **Suggested fix:** {how to resolve}

## Info
Minor improvements and observations.

- {observation}
- {observation}

## Verification Checklist
- [ ] All quantitative claims labeled
- [ ] No internal contradictions found
- [ ] Confidence ratings consistent with evidence
- [ ] Data gaps declared in all deliverables
- [ ] Red/Yellow flags present in all deliverables
- [ ] No stale data unmarked
- [ ] No duplicate-source false corroboration
- [ ] Positioning statements match research data (skill-specific)
- [ ] JTBD consistent with customer intelligence (skill-specific)
- [ ] Cross-deliverable coherence verified (skill-specific)
- [ ] Validation tests genuinely pass (skill-specific)
```

## Flow Control

- **If Critical issues > 0:** Pause. Show the user: "Verification found {N} critical issues that could affect decision-making." List them. Ask: "Should I fix these before continuing, or proceed as-is?"
- **If only Warnings/Info:** Show a one-line summary: "Verification complete: {N} warnings, {N} info items. See `verification-report.md` for details." Continue.
