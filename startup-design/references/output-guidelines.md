# Output Guidelines

## Standard File Header

Every output file should start with a consistent header:

```markdown
# [Document Title]

**Phase:** [Phase number and name]
**Project:** [project-name]
**Date:** [generation date]
**Confidence:** [Overall confidence: High / Medium / Low]

---
```

This makes it easy for the founder to navigate the deliverables and immediately understand the reliability of each document.

## Standard File Footer

Every output file should end with:

```markdown
---

## Flags

**Red Flags:**
- [List any red flags, or "None identified"]

**Yellow Flags:**
- [List any yellow flags, or "None identified"]

## Sources
- [Key sources referenced in this document with tier ratings]
```

## Cross-Phase Referencing

When a document references findings from another phase, use explicit callouts:

**Good:**
> "The target persona (see `01-discovery/target-audience.md`, Persona 1: Mid-market CFO) has an average tool budget of $2,000/month [Data, Gartner 2025]."

**Bad:**
> "As mentioned earlier, the target customer has budget for this."

Always include:
- The file path being referenced
- The specific finding (not a vague reference)
- The data label ([Data], [Estimate], etc.)

## Quality Examples

### Good vs. Bad Output

**Market Analysis — Bad:**
> "The market presents interesting opportunities for growth. There are several competitors but the space is not overcrowded. Timing seems favorable."

**Market Analysis — Good:**
> "The global invoice automation market is $4.2B [Data, MarketsAndMarkets 2025] growing at 12.3% CAGR [Data, Grand View Research 2025]. However, the SMB segment — our target — represents only $340M [Estimate, derived from 8.1% SMB share reported by Ardent Partners]. Three well-funded competitors (Tipalti $270M raised, Stampli $68M, Vic.ai $52M) already serve this segment [Data, Crunchbase]. **[Yellow Flag]** The market may be too small for a new entrant competing head-on; a niche positioning is needed."

**Scorecard — Bad:**
> | Market size | 7 | Good market size |

**Scorecard — Good:**
> | Market size | 5 | TAM is $4.2B but our serviceable segment (SMB invoice automation) is ~$340M [Estimate]. At 5% penetration that's $17M ARR — viable for a bootstrapped business but below typical VC thresholds. [Yellow Flag] |

## Handling Pivots

If the founder wants to change direction after seeing research or strategy outputs (different target market, different business model, different positioning):

1. **Don't restart from scratch.** Much of the research and analysis may still apply.
2. **Update the brief** (`00-intake/brief.md`) with a "Pivot Notes" section documenting what changed and why.
3. **Re-run only the affected phases.** If the pivot is about target market, re-run Phase 3 (customer research waves) and Phase 4 (strategy). If it's about business model, re-run Phase 4 and Phase 7.
4. **Mark re-run phases** in PROGRESS.md: `- [x] Phase 4: Strategy — re-run after pivot {date}`
5. **Keep old versions.** Rename the previous output to `{filename}.pre-pivot.md` before generating the new version. This preserves the decision trail.
