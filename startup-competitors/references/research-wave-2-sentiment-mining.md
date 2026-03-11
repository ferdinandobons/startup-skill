# Wave 2: Customer Sentiment Mining

Read `research-principles.md` first.

---

## Agent B1: Review Mining

```
Research task: Mine customer reviews for competitors in {product category}
Context: {product summary from intake}
Competitors to analyze: {list from Wave A}

Review mining reveals what customers actually experience — not what competitor marketing promises. The gap between promise and reality is where opportunities live.

HANDLING SCARCE REVIEWS:
Some markets (especially B2B, niche, or emerging categories) have very few formal reviews on G2/Capterra. When this happens:
1. Expand to additional platforms: App Store, Play Store, Trustpilot, Google Maps reviews (for physical products/services), industry-specific review sites
2. Search for case studies and testimonials on competitor websites — extract the language used
3. Search for "{competitor name} experience" or "{competitor name} honest review" on blogs and YouTube
4. Lean more heavily on forum mining (Wave B2) for unfiltered opinions
5. Declare the scarcity explicitly in Data Gaps — "only X reviews found across platforms" is valuable information itself (it signals market immaturity or low switching)
Always include at least 2-3 verbatim quotes per competitor, even if they come from blog posts, tweets, or forum comments rather than formal review platforms.

RESEARCH PROTOCOL:

ROUND 1 — Aggregate review platforms (2 searches per competitor):
- "{competitor name} reviews G2"
- "{competitor name} reviews Capterra" OR "Trustradius"
- "{competitor name} reviews Product Hunt"
- "{competitor name} app store reviews" (if mobile product)

ROUND 2 — Negative review deep-dive (1-2 searches per competitor):
- "{competitor name} complaints"
- "{competitor name} problems reddit"
- "{competitor name} worst things"

ROUND 3 — Feature request patterns (1-2 searches):
- "{competitor name} feature request"
- "{competitor name} missing features"
- "{product category} wishlist"

For EACH competitor, extract:

## {Competitor Name} — Review Analysis

### Review Volume & Ratings
- **G2:** {count} reviews, {avg} stars
- **Capterra:** {count} reviews, {avg} stars
- **TrustRadius:** {count} reviews, {avg} stars
- **Product Hunt:** {upvotes}, {comment sentiment}
- **App Store / Play Store:** {if applicable}

### What People Love (top 3-5 themes)
For each theme:
- **Theme:** {e.g., "Easy onboarding"}
- **Frequency:** mentioned in ~{X}% of positive reviews
- **Verbatim quotes:**
  - "{exact quote}" — {source, date}
  - "{exact quote}" — {source, date}

### What People Hate (top 3-5 themes)
For each theme:
- **Theme:** {e.g., "Pricing feels unfair at scale"}
- **Frequency:** mentioned in ~{X}% of negative reviews
- **Severity:** annoyance / blocker / deal-breaker
- **Verbatim quotes:**
  - "{exact quote}" — {source, date}
  - "{exact quote}" — {source, date}

### Most Requested Features
- {feature 1} — mentioned {X} times
- {feature 2} — mentioned {X} times
- {feature 3} — mentioned {X} times

### Churn Signals
Reasons people leave this competitor:
- {reason 1 — with evidence}
- {reason 2 — with evidence}
- {reason 3 — with evidence}

---

After all competitors:

## Cross-Competitor Pain Patterns
| Pain Theme | {Comp 1} | {Comp 2} | {Comp 3} | {Comp 4} | Opportunity |
|-----------|----------|----------|----------|----------|-------------|
| {pain 1} | severity | severity | severity | severity | {implication} |
| {pain 2} | ... | ... | ... | ... | ... |

Pains shared across multiple competitors = structural market problems = biggest opportunities.

## Data Gaps
- [Competitors with few reviews]
- [Platforms not checked]

Save to: {project-name}/raw/review-mining.md
```

---

## Agent B2: Forum & Community Mining

```
Research task: Mine forums and communities for customer voice about {product category}
Context: {product summary from intake}
Competitors: {list from Wave A}

Forum mining captures unfiltered opinions that people won't write in formal reviews. It also reveals the exact language customers use — gold for positioning and copywriting.

RESEARCH PROTOCOL:

ROUND 1 — Reddit (3-4 searches):
- "site:reddit.com {product category} recommendations"
- "site:reddit.com {competitor name} alternative"
- "site:reddit.com {problem statement} tool"
- "site:reddit.com switching from {competitor name}"

ROUND 2 — Indie communities (2-3 searches):
- "site:indiehackers.com {product category}"
- "site:news.ycombinator.com {product category}"
- "{product category} forum discussion"

ROUND 3 — Q&A and niche (2 searches):
- "site:quora.com best {product category}"
- "{product category} community Slack Discord"

ROUND 4 — Migration stories (1-2 searches):
- "switched from {competitor name} to"
- "migrating from {competitor name}"
- "why I left {competitor name}"

OUTPUT FORMAT:

## Forum & Community Findings

### Discussion Themes
For each major theme found:
- **Theme:** {what people are discussing}
- **Volume:** {approximate number of threads/comments}
- **Sentiment:** positive / negative / mixed
- **Key threads:**
  - [{thread title}]({url}) — {key takeaway}

### Language Map
The exact words customers use — organized for reuse in positioning and copy:

**To describe the problem:**
- "{exact phrase}" — used in {X} threads
- "{exact phrase}" — used in {X} threads

**To describe desired solution:**
- "{exact phrase}"
- "{exact phrase}"

**To describe frustrations with competitors:**
- "{exact phrase}" — about {competitor}
- "{exact phrase}" — about {competitor}

**To describe switching triggers:**
- "{exact phrase}"
- "{exact phrase}"

### "What do you use for X?" Threads
| Thread | Top Recommended | Runner Up | Common Criteria |
|--------|----------------|-----------|-----------------|
| {title} | {tool} ({why}) | {tool} | {what people care about} |

### Migration Stories
For each migration story found:
- **From:** {competitor} → **To:** {competitor}
- **Why they switched:** {reason}
- **What they gained:** {benefit}
- **What they lost:** {trade-off}
- **Would they switch again?** {yes/no and why}

### Churn Signal Summary
Aggregated reasons people leave competitors:
| Reason | Competitors Affected | Frequency | Severity |
|--------|---------------------|-----------|----------|
| {reason} | {which ones} | common / occasional | high / medium |

## Data Gaps
- [Communities not found or not active for this category]
- [Competitors with no forum presence]

Save to: {project-name}/raw/forum-mining.md
```
