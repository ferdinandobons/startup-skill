# Intake Brief: Invoice Recon AI

**Date:** 2026-03-06
**Project Codename:** invoice-recon-ai

---

## The Problem

Mid-size companies (50-500 employees) are still using Excel spreadsheets to reconcile invoices manually. This process is slow, error-prone, and expensive in terms of labor hours. Finance teams spend significant time matching invoices to purchase orders, flagging discrepancies, and chasing down approvals -- work that is repetitive and rule-based enough to automate, yet complex enough that simple macros fail.

## The Solution

A B2B SaaS platform that uses AI/ML to automate invoice reconciliation. The product would ingest invoices (from email, uploads, or integrations), match them against purchase orders and bank statements, flag discrepancies, and streamline the approval workflow. The ML pipeline would learn from corrections over time, improving accuracy per customer.

## Origin of the Idea

Founder-market fit driven. The founding CEO spent 10 years as a CFO in corporate finance and has lived this pain firsthand. The idea sits at the intersection of deep domain knowledge and a specific technical capability (ML pipelines), brought by the technical co-founder who built ML systems at Stripe.

## The Founders

| Role | Background | Strengths |
|------|-----------|-----------|
| CEO / Domain Lead | Former CFO, 10 years in corporate finance | Deep understanding of the reconciliation workflow, financial controls, compliance requirements, and buyer personas. Can speak the language of the customer. |
| CTO / Technical Lead | ML pipeline engineer, ex-Stripe | Production ML experience at scale, familiarity with financial data, engineering credibility. Stripe background signals competence in fintech-adjacent infrastructure. |

**Commitment level:** Not explicitly stated -- assumed full-time given the savings commitment, but should be confirmed.

**Budget/Runway:** $80,000 in personal savings for bootstrapping. At a lean burn rate (~$10-15k/month for two founders plus infrastructure), this gives roughly 5-8 months of runway before needing revenue or external funding.

## The Market

**Target Customer:**
- US-based mid-size companies, 50-500 employees
- Companies still using Excel for invoice reconciliation (i.e., have not adopted a dedicated AP automation or ERP reconciliation module)
- Likely industries: professional services, manufacturing, distribution, healthcare -- sectors with high invoice volumes but not enough scale to justify enterprise ERP

**Current Alternatives:**
- Manual Excel reconciliation (the status quo they are displacing)
- Enterprise ERP modules from SAP, Oracle, NetSuite (expensive, complex implementations)
- AP automation tools (Bill.com, Tipalti, Coupa) -- which handle payments but may not focus specifically on reconciliation intelligence
- Accounting software with basic matching (QuickBooks, Xero) -- limited ML capability

**Geography:** US market first.

## The Business Model

- **Revenue model:** SaaS subscription
- **Pricing:** $500/month per company
- **Implied assumptions:** At $500/mo, they need 200 customers to hit $1.2M ARR. The price point suggests a mid-market play -- low enough to avoid lengthy enterprise procurement cycles, high enough to support a sales-assisted motion.

## Key Concerns

**Primary worry:** Large ERP players (SAP, Oracle) could add AI-powered reconciliation as a feature within their existing platforms. This is a legitimate "feature vs. product" risk.

**Initial assessment of this risk:**
- ERP vendors move slowly. Their AI features tend to be bolted on, not deeply integrated.
- Mid-size companies using Excel are, by definition, NOT current ERP customers. SAP and Oracle adding a feature only helps their existing install base.
- The real competitive threat is more likely from AP automation vendors (Bill.com, Tipalti) or accounting platforms (QuickBooks, Xero) that serve this segment and could add ML reconciliation.
- Speed of execution and depth of specialization are the defenses. A purpose-built tool will outperform a bolted-on feature for years.

## Open Questions (Targeted Follow-Ups Needed)

These are gaps in the intake that would strengthen the strategy work:

1. **Commitment level:** Are both founders going full-time? When is the target start date (or have you already started)?

2. **Existing work:** Do you have any prototype, waitlist, landing page, or letters of intent? Have you done any customer discovery interviews yet?

3. **Sales motion:** Given the $500/mo price point, are you envisioning self-serve sign-up, sales-assisted, or outbound sales? Your CFO background suggests you could sell directly to peers.

4. **Integration requirements:** Which accounting systems and ERPs do your target customers currently use? QuickBooks? Xero? NetSuite? This determines your integration priority and technical scope.

5. **Data sensitivity:** Invoice data is financially sensitive. Have you thought about compliance requirements (SOC 2, data residency, etc.)? This affects both timeline and cost.

6. **Success milestones:** What does success look like at 6 months, 12 months, and 3 years? How many paying customers would validate the concept for you?

7. **Funding plans:** Is the $80k meant to get to revenue, or to get to a fundable milestone for a seed round? This changes the strategy significantly.

8. **Technical approach:** Will the ML model need training data? How do you plan to handle the cold-start problem (no historical data from new customers)?

---

## Summary

This is a well-conceived idea with strong founder-market fit. A former CFO and a Stripe ML engineer targeting a specific, painful workflow (Excel-based invoice reconciliation) for an underserved segment (mid-size companies too big for basic tools, too small for enterprise ERP) is a credible founding story. The $500/mo price point is reasonable for the segment, though it may need validation. The primary strategic question is not whether ERPs will add this feature (they will, eventually) but whether the founders can build a moat through specialization, data network effects, and speed of execution before that happens.
