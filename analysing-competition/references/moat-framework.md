# Moat Framework

Canonical reference for the Moat Assessment section of any competitive analysis.
Load this file before scoring moats. Apply all six types to every assessment.

---

## Scoring guide

| Score | Meaning |
|-------|---------|
| **Strong** | Demonstrably compounds over time; measurable lock-in or reinforcement mechanism; validated by customer behaviour (not founder claims) |
| **Moderate** | Present but not yet durable; depends on continued execution; could be eroded by a well-resourced competitor within 2–3 years |
| **Weak** | Claimed but not substantiated; feature-level advantage; reversible with funding or engineering effort |
| **None** | No evidence of a structural advantage; product is replicable |

A moat must pass the **lock-in test**: does it make it harder to leave, or harder for a competitor to win, over time? If not, it is not a moat — it is a feature.

---

## The six moat types

### 1. Network effects
**Definition:** The product becomes more valuable as more users or participants join.

**What to look for:**
- Direct network effects: more users → better product for each user (e.g. messaging, marketplaces)
- Data network effects: more usage → better model → better product (e.g. fraud detection, pricing engines)
- Indirect network effects: more suppliers attract more buyers, or vice versa

**Red flags:**
- "Network effects" claimed for a product with no multi-sided or data loop — this is marketing language
- Network effects that only work at scale the company hasn't yet reached
- Single-tenant SaaS with no data sharing or cross-customer learning

**Scoring signal:** If removing one customer makes the product marginally worse for others, that's a real network effect. If it doesn't, it isn't.

---

### 2. Proprietary data
**Definition:** The company accumulates data through its operations that competitors cannot replicate and that meaningfully improves product quality or decision accuracy.

**What to look for:**
- Exclusive data sources (e.g. claims data only accessible through insurer partnerships)
- Longitudinal data that improves model accuracy over time
- Data network effects that compound with scale

**Red flags:**
- Data that is publicly available or purchasable from a third party
- "We have lots of data" with no explanation of what it improves or why competitors can't access similar data
- Proprietary data that hasn't been turned into a product advantage yet

**Scoring signal:** Ask: could a well-funded competitor buy or replicate this data in 18 months? If yes, it is not a durable moat.

---

### 3. Switching costs
**Definition:** Customers face meaningful cost — financial, operational, or contractual — when moving to a competitor.

**What to look for:**
- Deep integrations into core systems (claims platforms, policy admin, ERP)
- Data portability constraints
- Workflow dependencies: staff trained on the product, processes rebuilt around it
- Multi-year contracts with significant migration costs

**Red flags:**
- Switching costs that exist in theory but haven't been tested in practice (no churned customer data)
- SaaS products with simple CSV export and no system integrations
- "Stickiness" described in terms of UI familiarity rather than technical or operational lock-in

**Scoring signal:** Ask: what would it cost a customer (time, money, disruption) to move to the nearest competitor? If the answer is "a few weeks and a data migration," the switching cost is weak.

---

### 4. Brand
**Definition:** Customers pay a premium or extend trust based on the company's reputation, not just its product specs.

**What to look for:**
- Category-defining position ("the Veeva of X")
- Trust premium in regulated or high-stakes categories (insurance, healthcare, financial services)
- Brand that shortens sales cycles or reduces CAC demonstrably

**Red flags:**
- Brand as a moat for a company under 5 years old in a competitive B2B category — almost never real at this stage
- "We're known in the market" without evidence of pricing power or reduced sales friction
- Brand claimed for a product no one outside the company's network has heard of

**Scoring signal:** Brand moats take 7–10 years to build in enterprise B2B. Score this as Weak or None for most early-stage companies unless there is clear evidence of pricing premium or CAC advantage.

---

### 5. Regulatory
**Definition:** The company holds licences, certifications, or regulatory relationships that competitors cannot quickly replicate.

**What to look for:**
- Insurance carrier licences, Lloyd's of London stamp, FCA authorisation, or equivalent
- Accreditations required for procurement in regulated sectors (SOC 2, ISO 27001, HIPAA — note: these are table stakes, not moats)
- Regulatory relationships built through years of co-design with a government body

**Red flags:**
- Compliance certifications (SOC 2, ISO 27001) cited as moats — these are prerequisites, not advantages
- Regulatory approval cited in markets where the regulatory bar is low or where competitors are already approved
- Pending regulatory status treated as a current moat

**Scoring signal:** The moat is real only if obtaining the same regulatory position would take a competitor more than 12–18 months of active effort, not just time.

---

### 6. Distribution
**Definition:** The company has access to a customer channel that competitors cannot easily replicate.

**What to look for:**
- Embedded distribution through an existing platform (e.g. built into a claims management system used by 200 carriers)
- Exclusive or preferential channel partnerships
- A founder or team with pre-existing relationships that translate into a pipeline competitors can't access
- OEM or white-label arrangements with large incumbents

**Red flags:**
- Distribution advantage dependent on a single partnership that could be withdrawn
- "We know everyone in the industry" — relationship advantages don't survive a founder departure
- Channel described but no evidence it has translated into closed deals

**Scoring signal:** Distribution moats are often the most underrated at early stage and the most fragile at growth stage. Score based on evidence of closed deals through the channel, not claims about access.

---

## Common patterns and what they mean

| Pattern | What it signals |
|---------|----------------|
| Strong proprietary data + switching costs | Classic enterprise SaaS moat; durable if data is genuinely exclusive |
| Network effects only | High ceiling but binary — valueless if scale isn't reached; assess critical mass threshold |
| Regulatory only | Narrow moat; protects only for as long as the regulatory environment holds |
| Distribution only | Can be first-mover advantage, but fragile without product lock-in underneath |
| "Better product" with no structural moat | Execution advantage; temporary by definition; assess team's ability to stay ahead |
| Multiple weak moats | Often better than one strong moat; assess whether they compound |
| No moat identified | Normal at pre-Series A; the question is whether the trajectory is toward moat-building |
