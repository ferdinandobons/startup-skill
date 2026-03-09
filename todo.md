# Startup Plugin — Skill Roadmap

## Taxonomy

Skills in the `startup` plugin are organized in 3 categories:

| Category | Description | Purpose |
|----------|-------------|---------|
| **Design** | Full process from idea to validated plan | The core engine |
| **Analyze** | Deep analysis of a single dimension | Standalone tools, usable without startup-design |
| **Build** | Tools for executing after validation | Post-design, the idea passed and the founder wants to move forward |

## Skill Map

```
startup (plugin)
│
├── DESIGN
│   └── startup-design              ✅ v1.1.0 — full startup design (8 phases)
│
├── ANALYZE
│   ├── startup-competitors         ✅ created — deep competitive intelligence
│   └── startup-positioning         ⬜ to do — positioning strategy (full April Dunford process)
│
└── BUILD
    └── startup-pitch               ⬜ to do — structured pitch deck
```

## Skills to Create

### startup-positioning (ANALYZE)

**What it does:** Dedicated positioning process using April Dunford's complete framework. startup-design uses positioning in a single page as part of the Strategy phase. This skill goes much deeper.

**Why it's valuable standalone:** Positioning is the #1 problem for early-stage startups. Many founders already have a product but don't know how to position it. They don't need 8 phases — they need to understand *who they are, who they're for, and why they're different*.

**What it covers (that startup-design doesn't):**
- Deep interview about product, customers, and competitors
- Competitive alternatives analysis (not just "who are the competitors" but "what happens if you don't exist")
- Unique attributes mapping with evidence
- Value chain: attributes → benefits → customer value
- Target market segmentation with prioritization
- Market category selection (or creation of a new category)
- Positioning statement + messaging framework
- Positioning testing with real scenarios

**Output:** A complete positioning document + reusable messaging framework for landing pages, pitch decks, and ads.

---

### startup-pitch (BUILD)

**What it does:** Generates a structured pitch deck with narrative, data, and slide-by-slide content. Can use data from startup-design if available, or start from scratch.

**Why it's valuable post-design:** After an idea is validated with startup-design, the founder needs to present it — to investors, co-founders, early customers, accelerators. The pitch deck is the most requested deliverable.

**What it covers:**
- Pitch narrative design (problem → solution → traction → ask)
- Slide-by-slide content (title, body, data, speaker notes)
- Support for different formats: investor pitch, customer pitch, accelerator application
- Length adaptation: 5-slide lightning, 10-slide standard, 15-slide detailed
- Data and numbers pulled from research (if startup-design was executed)
- Appendix slides for deep-dives
- Oral presentation script

**Output:** Complete content for every slide in markdown, ready to be transferred to Keynote/Google Slides/Figma.
