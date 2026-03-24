# Verification Agent Protocol

After synthesis completes, spawn a **Verification Agent (V1)** that audits all deliverables for consistency, accuracy, and completeness. This step catches issues that individual agents and synthesis can miss.

## When to Run

- After synthesis is complete and all deliverable files are written
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

## Skill-Specific Checks: startup-competitors

In addition to the universal checks above, verify:

### Battle Card vs. Report Consistency
- Every competitor in the battle cards must appear in the `competitors-report.md` Key Players table
- Strengths/weaknesses in battle cards must not contradict the competitor profiles in the report
- Threat levels must be consistent between battle cards and the report

### Matrix vs. Profiles Alignment
- Every competitor in `competitive-matrix.md` must have a profile in `competitors-report.md`
- Feature ratings (Strong/Adequate/Weak/Missing) in the matrix must be supported by evidence in the report or battle cards
- Gap analysis items must connect to actual findings, not assumptions

### Pricing Landscape vs. Profiles Consistency
- Pricing data in `pricing-landscape.md` must match pricing mentioned in battle cards
- Value metrics must be consistent across the pricing landscape and competitor profiles
- Switching cost assessments must align between pricing landscape and battle cards

### Cross-Deliverable Coherence
- Strategic opportunities in the report must be supported by evidence from at least two deliverables (e.g., pricing gap + customer complaint)
- Strategic risks must be traceable to specific competitor data
- Moat assessment must reference specific competitors and evidence

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
- [ ] Battle cards consistent with report (skill-specific)
- [ ] Matrix aligned with profiles (skill-specific)
- [ ] Pricing landscape consistent with profiles (skill-specific)
- [ ] Opportunities backed by multi-source evidence (skill-specific)
```

## Flow Control

- **If Critical issues > 0:** Pause. Show the user: "Verification found {N} critical issues that could affect decision-making." List them. Ask: "Should I fix these before continuing, or proceed as-is?"
- **If only Warnings/Info:** Show a one-line summary: "Verification complete: {N} warnings, {N} info items. See `verification-report.md` for details." Continue.
