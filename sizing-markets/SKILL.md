---
name: sizing-markets
description: Estimate TAM, SAM, and SOM for any market opportunity using top-down and bottom-up methodologies. Use when sizing a market, validating an investment thesis, evaluating a startup's market claims, or preparing investor-ready analysis. Trigger whenever Simon asks "how big is this market", "what's the TAM", "size this opportunity", "is this market big enough", or shares a company or sector with questions about market potential. Also use when market sizing is needed as part of startup evaluation, due diligence, or thesis development — even without an explicit request.
---

<!-- version: 1.0 | tested-on: claude-sonnet-4-6 -->

## Triggers

Use this skill when the user says or implies:
- "size this market", "what's the TAM for X", "how big is this market"
- "estimate the addressable market", "build a TAM/SAM/SOM"
- "is this market big enough for VC?", "validate the market opportunity"
- "what are the market claims in this deck?", "stress-test this TAM"
- Market sizing is needed as part of screening, due diligence, or thesis work — even without an explicit request

---

## Dependencies

- Web search tool (required — for current market data, analyst reports, and benchmarks)
- PDF skill (required — for final output delivery)
- No context files required

---

## Instructions

**Mode: Co-Worker.** This skill runs through three deliberate gates with Simon before delivering a final output. Do not skip gates.

---

### Goal

Produce a rigorous, investor-ready TAM/SAM/SOM analysis using both top-down and bottom-up methodologies. The output is a PDF report with explicit sourcing, clearly labelled assumptions, confidence levels, and a 2-3 year market projection.

---

### Process

**Step 1 — [GATE 1: Input confirmation]**

Before any research, pause and confirm the market scope with Simon. Ask:

- What is the market or product being sized? (Be specific about the problem space)
- Who are the target customers? (Segment, size, industry)
- What geography applies?
- What is the time horizon? (Current sizing, or a future year)
- Are there any known data sources, constraints, or comparable companies to anchor from?

Wait for Simon's response before proceeding. Do not make assumptions about scope.

---

**Step 2 — Research**

Using the confirmed scope, gather market data via web search. Prioritise high-quality sources in this order:
1. Tier 1 analyst reports: Gartner, Forrester, IDC, McKinsey Global Institute, BCG, Bain
2. Specialist data providers: CB Insights, PitchBook, Statista, Bloomberg, S&P Global
3. Public company filings: annual reports, 10-Ks, investor presentations, earnings transcripts
4. Government and trade bodies: national statistics offices, relevant regulatory agencies, industry associations
5. Academic and NGO research where primary data is cited

Avoid: blogs, press releases, self-reported startup statistics, and any source that does not cite primary data. If a secondary source cites a primary report, find and use the original.

For each source used, record: source name, publication date, specific data point, and URL or filing reference. Flag any data older than 3 years as potentially stale.

Gather enough data to support both a top-down and a bottom-up TAM calculation before moving to Step 3.

---

**Step 3 — Calculate TAM (both methods)**

Run both methodologies:

**Top-down:**
```
TAM = Total Market Category Size (from research)
Apply geographic filter → apply segment filter → document each step
```

**Bottom-up:**
```
TAM = Σ (Segment Size × Annual Revenue per Customer)
Build from customer count × average contract value or ARPU
```

Document sources and assumptions for every input. Label estimates vs. confirmed data points.

---

**Step 4 — [GATE 2: TAM sign-off]**

Present Simon with:
- Top-down TAM figure + key data source + one-line rationale
- Bottom-up TAM figure + key assumptions (customer count, pricing, frequency)
- Reconciliation: how far apart are the two figures? If >50% divergence, flag it explicitly and ask how Simon wants to resolve it
- Your recommended TAM figure with reasoning
- Any data gaps or wide confidence intervals worth flagging

Ask Simon to confirm the TAM and assumptions before continuing to SAM/SOM.

---

**Step 5 — Calculate SAM and SOM**

Using the confirmed TAM:

**SAM** — apply filters to narrow to what is realistically serviceable:
- Geographic constraints
- Product capability limits (what the product can actually serve today)
- Channel or distribution constraints
- Customer size, segment, or compliance requirements

Document each filter and the percentage applied.

**SOM** — estimate achievable market share:
- Default range: 2-5% of SAM for a new entrant in years 1-3
- Adjust up or down based on competitive intensity, go-to-market capacity, and any existing traction
- Show both a conservative and an optimistic scenario if the range is wide

---

**Step 6 — [GATE 3: Output framing]**

Before writing the report, ask Simon:
- What is this analysis being used for? (Investor pitch, IC memo, internal strategy, DD on a startup)
- Is there anything to emphasise or de-emphasise given the audience?

This determines the tone, structure emphasis, and depth of the final output.

---

**Step 7 — Write and deliver**

Invoke the PDF skill to produce the final output. Use the structure below exactly.

Save to: `Resources/Output files/sizing-markets_[market-name]_v1.pdf`

---

### Output Structure

```
1. Market Definition
   - Problem space and customer need
   - Geographic and segment boundaries
   - Key scoping decisions

2. TAM (Total Addressable Market)
   - Top-down estimate (source, methodology, figure)
   - Bottom-up estimate (assumptions, figure)
   - Reconciliation and recommended TAM
   - [Inference] / [Unverified] labels where applicable

3. SAM (Serviceable Addressable Market)
   - Filters applied and rationale for each
   - SAM figure and SAM as % of TAM

4. SOM (Serviceable Obtainable Market)
   - Competitive position and go-to-market basis
   - Conservative and optimistic scenarios
   - SOM as % of SAM

5. Market Summary Table
   | Metric | Current | 2-3 Year Projection |
   |--------|---------|---------------------|
   | TAM    |         |                     |
   | SAM    |         |                     |
   | SOM    |         |                     |

6. Growth Drivers & Trends
   - Technology, regulatory, demographic, or behavioural tailwinds/headwinds
   - Emerging segments or adjacent markets

7. Key Assumptions & Risks
   - Numbered list of critical assumptions
   - Confidence level for each: High / Medium / Low
   - How to validate the most uncertain ones
   - What would materially change the estimates

8. Sources (top 20)
   - Numbered list of up to 20 sources used, in order of relevance
   - Format: [Source name] — [Publication date] — [Data point it supports] — [URL or filing reference]
   - Include only sources that directly informed a figure or assumption in the analysis
```

---

## Failure Modes

- **Web search returns no usable data:** Notify Simon. Propose either proceeding with explicitly stated assumptions (labelled [Unverified]) or aborting. Do not fabricate data.
- **Top-down and bottom-up TAM diverge by >50%:** Flag at Gate 2. Do not average the two blindly. Ask Simon how to resolve before continuing.
- **Market too nascent for reliable data:** Propose switching to a value-theory methodology (problem cost × willingness to pay × addressable base). Get Simon's approval before proceeding.
- **PDF skill unavailable:** Deliver output as a markdown file. Flag the format downgrade to Simon and note the intended location.
- **Simon's scope inputs are ambiguous after Gate 1:** Ask one targeted follow-up question. Do not proceed with ambiguous inputs.
