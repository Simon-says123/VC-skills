# Initial Screening Output Structure

**Version:** 1.0
**Last updated:** 2026-04-21
**Purpose:** Defines the canonical nine-section output format for IAGFV initial company screens. Claude reads this before generating any screen. Sections map directly to the evaluation dimensions in initial-screening-framework.md.

---

## Canonical Structure

### Section 1: Company Snapshot

Structured header block. All fields populated from public sources. Mark any field as [Unverified] if sourced from inference rather than confirmed data.

| Field | Detail |
|---|---|
| Company | Name |
| URL | Website |
| HQ | City, Country |
| Founded | Year |
| Stage | Last round type (e.g., Seed, Series A) |
| Last Round | Amount raised, date, lead investor |
| Total Funding | Cumulative raised to date |
| FTEs | Headcount (approximate if from LinkedIn) |
| One-liner | Single sentence: what the company does |

---

### Section 2: What They Do

2-3 sentences. Cover: the problem solved and for whom; how it is solved (product/technology approach); business model (SaaS, platform, marketplace, services, hybrid).

No marketing language. Describe the product as an informed outsider would — not as the company's website does.

*Maps to: Tech and Product dimension*

---

### Section 3: Traction Signals

Key metrics and proof points from public sources. Structure as a short list (3-6 items).

Common signals: revenue or ARR if disclosed or estimable; customer count, notable logos, or verticals served; growth indicators (hiring velocity, geographic expansion, product launches); notable investors or strategic backers; partnerships, pilots, or integration announcements; awards or accelerator participation only if genuinely signal-rich.

Every data point must cite its source. Label estimates clearly. Do not infer revenue from headcount or funding without flagging the assumption.

*Maps to: Traction dimension*

---

### Section 4: Team

Founder names, titles, and relevant background (2-3 sentences per founder). Founder-market fit assessment: insider, outsider, or hybrid — one sentence explaining the classification. Notable leadership hires or advisory board members only if genuinely relevant. Team composition signals: technical depth, commercial experience, domain expertise.

Focus on fit and capability, not pedigree.

*Maps to: Team dimension*

---

### Section 5: Market Context

Directional market framing — not a full market sizing exercise. Cover: market size (TAM, directional) and growth trajectory; key demand drivers or tailwinds; where the company sits in the competitive landscape; 2-3 closest competitors or alternatives; maturity of the category (emerging, growth, mature, consolidating).

One short paragraph plus a competitive context sentence. Point to existing IAGFV thesis work or Wiki pages if the market has been covered before.

*Maps to: TAM and Timing dimensions*

---

### Section 6: Strategic Relevance to IAG

Quick-hit assessment of the IAG connection. Cover: which IAGFV focus area(s) this falls under (InsurTech, Enterprise Tech, Mobility, Emerging Tech); which IAG divisions or BUs would benefit (RIA, IIA, NZ, Group); signal strength (High, Medium, Low, or Unclear); most likely integration or partnership pathway if apparent; existing investor involvement from IAG or peer carriers.

Do not force strategic fit where it does not exist. Unclear is a valid and honest assessment at screening stage.

*Maps to: Insurance Relevance and Investors dimensions*

---

### Section 7: Key Risks

Top 5 risks, ordered by severity. Each risk is 1-2 sentences, specific to this company.

Cover a mix of: product/technology risk (defensibility, replication); market risk (timing, adoption, regulatory); execution risk (team gaps, scaling complexity); competitive risk (incumbent response, well-funded competitors); business model risk (unit economics, customer concentration); funding/valuation risk (capital intensity, investor quality).

"Competition is a risk" is not acceptable. "Three well-funded Series B competitors (X, Y, Z) are targeting the same buyer persona in the same geography" is.

*Synthesises across all dimensions*

---

### Section 8: Key Questions

Eight questions that go beyond desk research — the questions a first meeting, reference call, or internal IAG validation would need to answer. Each question must be specific enough that a meeting agenda could be built around it.

**Questions 1-3: General venture investor lens**

Stress-test PMF, go-to-market defensibility, unit economics, and capital efficiency. Examples of the right level of specificity: how does the team plan to reduce CAC as they expand beyond their initial beachhead; what is the path to contribution margin positive; where does net revenue retention sit and what is driving churn.

**Questions 4-6: Product and moats**

Probe the durability of the product's differentiation and the strength of the competitive moat. Cover: what proprietary data, technical architecture, or network effects prevent a well-resourced incumbent or competitor from replicating the core product within 18-24 months; where does the moat compound over time and where does it erode; how defensible is the product if the underlying infrastructure (e.g., LLM providers, API partners) changes pricing or terms.

**Questions 7-8: IAGFV-specific lens**

Focus on strategic fit, integration pathway, and internal stakeholder appetite. Cover how the opportunity intersects with IAG's operations, data assets, or customer base, and which BU would need to champion a partnership or pilot for it to have real traction internally.

*Maps to: all dimensions*

---

### Section 9: Initial Take

2-3 sentences. The analyst's honest assessment at screening stage. Cover: overall lean (what is interesting about this opportunity); the biggest single question mark or concern; whether this warrants further time and attention.

Direct and opinionated. This is not a balanced summary. State the lean.

---

## Formatting Rules

- **Voice:** "We" / "us" throughout
- **Length:** 1-2 pages when rendered as PDF
- **Tone:** Informed, direct, evidence-based — not a pitch, not a pass note
- **Evidence:** Cite sources for all data points. Label inferences ([Inference]) and unverified claims ([Unverified])
- **No filler:** Every sentence carries information
- **No em dashes:** Use commas, semicolons, or restructure
- **No marketing language:** Describe what the product does, not what the company claims
- **Visually clean:** Minimal formatting. Structure earns its place through content, not decoration

---

## When to Use This Template

Use when: triaging an inbound deal or a company surfaced through sourcing; preparing for a first meeting with a founder; conducting company-level research as part of a broader thesis exercise; quickly assessing whether a company warrants deeper evaluation.

Do not use for: post-meeting deeper evaluation (use the opportunity brief template); full investment memos for IC (use the VC output template); market-level or thesis-level analysis (use the pipeline skills).

---

*IAGFV internal reference. Update when the output format evolves. Companion document: initial-screening-framework.md.*
