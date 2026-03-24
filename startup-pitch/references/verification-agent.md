# Verification Agent Protocol

After pitch construction completes, spawn a **Verification Agent (V1)** that audits all deliverables for consistency, accuracy, and completeness. This step catches issues that individual agents and synthesis can miss.

## When to Run

- After all pitch deliverables are written (before the scorecard/review phase)
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

## Skill-Specific Checks: startup-pitch

In addition to the universal checks above, verify:

### Pitch Claims vs. Source Data
- Every numerical claim in the pitch narratives (traction, market size, revenue, growth rate) must be traceable to either intake data or prior session files
- If the pitch was built on startup-design data, verify that market size numbers match `market-analysis.md`
- If built on startup-competitors data, verify competitive claims match `competitors-report.md`
- Flag any number in the pitch that doesn't appear in any source file

### Cross-Format Consistency
- The 2-sentence opener must be identical (or a faithful compression) across all pitch formats
- Market size, traction numbers, and the ask must be consistent across pitch-full, pitch-5min, pitch-2min, pitch-1min, and pitch-email
- The unique insight must be the same concept across all formats (phrased differently but same core idea)
- Team credentials must not vary between formats (no inflated version in one, modest in another)

### Pitch vs. Appendix Alignment
- Every objection in `pitch-appendix.md` must have a corresponding answer
- Known weaknesses in the appendix must match the Red/Yellow Flags in pitch files
- Q&A answers must not contradict claims made in the pitch narratives
- If competitive backup references battle cards, verify the competitor names and claims match

### Honesty Checks
- Flag any traction claim without a timeframe ("10K users" without "in X months")
- Flag top-down TAM without bottom-up math
- Flag team credentials that are titles without accomplishments
- Flag "no competition" or equivalent claims

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
- [ ] Pitch claims traceable to source data (skill-specific)
- [ ] Cross-format consistency verified (skill-specific)
- [ ] Pitch and appendix aligned (skill-specific)
- [ ] Honesty checks passed (skill-specific)
```

## Flow Control

- **If Critical issues > 0:** Pause. Show the user: "Verification found {N} critical issues that could affect decision-making." List them. Ask: "Should I fix these before continuing, or proceed as-is?"
- **If only Warnings/Info:** Show a one-line summary: "Verification complete: {N} warnings, {N} info items. See `verification-report.md` for details." Continue to scorecard/review phase.
