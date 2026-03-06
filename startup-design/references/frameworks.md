# Strategic Frameworks Reference

Use this document when applying frameworks during Phase 4 (Strategy) and Phase 8 (Validation). These are the canonical definitions — follow them to ensure consistency.

---

## Lean Canvas (Ash Maurya)

A 1-page business model adapted from the Business Model Canvas for startups. Fill in this order for best results:

1. **Problem** — Top 3 problems your customers have. List existing alternatives for each.
2. **Customer Segments** — Target customers. Identify early adopters separately.
3. **Unique Value Proposition** — Single, clear, compelling message that turns an unaware visitor into an interested prospect. Follow the formula: "We help [customer] [solve problem] by [mechanism]."
4. **Solution** — Top 3 features that address the top 3 problems. Keep it minimal.
5. **Channels** — Path to customers. Distinguish between inbound (SEO, content, referrals) and outbound (ads, sales, partnerships).
6. **Revenue Streams** — Revenue model, pricing, lifetime value, gross margin.
7. **Cost Structure** — Customer acquisition costs, distribution costs, hosting, people, etc.
8. **Key Metrics** — The 3-5 numbers that tell you how the business is doing. Use the pirate metrics framework (AARRR): Acquisition, Activation, Retention, Revenue, Referral.
9. **Unfair Advantage** — Something that cannot be easily copied or bought. Examples: insider knowledge, personal authority, community, network effects, proprietary data, existing platform.

---

## April Dunford's Positioning Framework

From "Obviously Awesome." Positioning defines how your product is the best in the world at providing something that a well-defined set of customers cares a lot about.

**The 5 components (work through in this order):**

1. **Competitive Alternatives** — What would customers do if your solution didn't exist? Not just direct competitors — include manual processes, spreadsheets, hiring someone, doing nothing. This grounds the positioning in reality.

2. **Unique Attributes** — What do you have that the alternatives don't? Be specific and factual. Not "better UX" but "drag-and-drop workflow builder that requires zero code." Capabilities, features, expertise, integrations, data, speed, etc.

3. **Value** — What do those attributes enable for the customer? Map each attribute to a customer benefit. Attributes are features; value is the outcome. "Drag-and-drop builder" → "Non-technical teams can build workflows without waiting for engineering."

4. **Target Customer** — Who cares the most about this value? The best customers are those for whom your unique value is critical, not just nice-to-have. Define by characteristics that make them care more than others.

5. **Market Category** — The context you position your product in so the value is obvious. Three options:
   - **Existing category**: You're a better version of something people already buy (e.g., "CRM for real estate agents")
   - **New sub-category**: You take an existing category and add a qualifier (e.g., "AI-powered recruiting platform")
   - **New category**: Rare and expensive to do. Only if nothing else frames your value well.

---

## Value Proposition Canvas (Strategyzer)

Two sides that must fit together:

### Customer Profile (right side)
- **Jobs-to-be-done** — What the customer is trying to accomplish. Include functional jobs (tasks), social jobs (how they want to be perceived), and emotional jobs (how they want to feel).
- **Pains** — What annoys, frustrates, or blocks them before, during, or after getting a job done. Include risks, undesired outcomes, and obstacles.
- **Gains** — What outcomes and benefits customers want. Include required gains (must-haves), expected gains (standard), desired gains (nice-to-have), and unexpected gains (delighters).

### Value Map (left side)
- **Products & Services** — What you offer (features, services, support).
- **Pain Relievers** — How your offering alleviates specific customer pains. Map each to a specific pain.
- **Gain Creators** — How your offering creates specific customer gains. Map each to a specific gain.

**Fit** exists when your pain relievers and gain creators match the most important pains and gains.

---

## RICE Prioritization (Intercom)

Score features to decide build order. Each feature gets four scores:

- **Reach** — How many customers will this affect per quarter? Use a concrete number (e.g., 500 users/quarter).
- **Impact** — How much will this move the needle for each person reached? Score: 3 = massive, 2 = high, 1 = medium, 0.5 = low, 0.25 = minimal.
- **Confidence** — How sure are you about reach and impact estimates? Score: 100% = high confidence (data-backed), 80% = medium, 50% = low (gut feel).
- **Effort** — How many person-months will this take? Higher effort = lower priority.

**Formula:** `RICE = (Reach × Impact × Confidence) / Effort`

Sort features by RICE score descending. The highest scores should be built first.

---

## MoSCoW Prioritization

Simpler alternative to RICE. Categorize every feature into one bucket:

- **Must have** — Without these, the product doesn't solve the core problem. Non-negotiable for MVP.
- **Should have** — Important but not critical. The product works without them, but it's notably weaker.
- **Could have** — Nice to have. Include if time/budget allows, but cut first when scope is tight.
- **Won't have (this time)** — Explicitly out of scope. Important to name these to prevent scope creep.

---

## Risk Matrix

Used in Phase 8 (Validation) for risk analysis. Plot each risk on two axes:

**Likelihood:** How probable is this risk?
- High (>60% chance)
- Medium (20-60%)
- Low (<20%)

**Impact:** If it happens, how bad is it?
- Critical — Business fails or pivots required
- Major — Significant delay or revenue loss
- Moderate — Manageable but painful
- Minor — Inconvenience, easily absorbed

**Priority quadrants:**
1. High likelihood + Critical/Major impact → Address immediately, design mitigation
2. Low likelihood + Critical impact → Monitor, have contingency plan
3. High likelihood + Minor impact → Accept and manage
4. Low likelihood + Minor impact → Acknowledge and move on
