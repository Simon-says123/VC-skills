---
name: evaluating-startups
description: "Use when a startup has passed initial screening and is entering deeper evaluation. Produces three outputs: a 6-page Evaluation Report (full research base), an Opportunity Brief (IC-ready distillation), and a Sources document. Triggers include: write an opp brief, opportunity brief for [company], evaluate this deeper, let's do a proper eval, prepare this for the team, this one's worth going deeper on, or any time a deal is moving toward IC discussion post-first-meeting. Do not trigger for initial triage — use screening-startups for that. Co-Worker mode: four mandatory Simon-in-the-loop gates."
---

<!-- version: 2.0 | tested-on: claude-sonnet-4-6 | calls: pdf -->

# Evaluating Startups

## Triggers

Use post-first-meeting or when a deal has moved past initial screening and is entering deeper evaluation. Specific phrases: "write an opp brief", "opportunity brief for [company]", "evaluate this deeper", "prepare this for the team", "let's do a proper eval on this", "this one's worth going deeper on", or when a deal is moving toward IC discussion.

Do not trigger for initial triage or pre-meeting research — that is the screening-startups skill.

---

## Dependencies

- Web search and web fetch tools (required)
- PDF skill (required)
- `references/startup-evaluation-framework.md` — 8-dimension research guide
- `references/analytical-frameworks.md` — 5 frameworks with selection guide
- `references/evaluation-report-template.md` — 6-page report structure
- `references/opportunity-brief-template.md` — IC-ready brief structure
- `Context/professional/company context.md` — ventures team lens and fund parameters
- `Context/professional/IAG_Insights_Group.md` — IAG divisions and KPIs
- `Wiki/CoE-Venture-Investment/founder-evaluation.md` — team assessment criteria
- Prior screening PDF for this company if one exists

---

## Instructions

**Mode: Co-Worker**

Four mandatory Simon-in-the-loop gates. Do not skip any. Each gate has a clear trigger, a specific question, and a defined consequence.

---

### Goal

Conduct significantly deeper research than the initial screening phase and produce three outputs: a 6-page Evaluation Report capturing the full research across all analytical dimensions, an Opportunity Brief distilling that research into an IC-ready document incorporating Simon's insider context, and a Sources and Further Reading document. Together, these give the ventures team a complete picture of the deal — the evidence base, the investment case, and the research trail.

---

### Process

**Step 1 — Resolve company and create output folder**

Identify the company. Check for an existing screening PDF in `Resources/Output files/` or `Projects/[company-name]/`. Load it if found and flag to Simon that you are building on prior work.

Create the output folder: `Resources/Output files/[company-name]/`. If a folder already exists, flag it and use incremented version numbers for all outputs.

**[GATE 1 — Input confirmation]**

Before any research begins, prompt Simon:

> "Before I start research, please share anything that won't be findable publicly:
> - Meeting notes, pitch deck, data room materials, or any documents from the founder
> - Your impressions of the team, product, or deal from the meeting
> - Any specific angles, concerns, or questions you want the evaluation to focus on"

Do not proceed to Step 2 until Simon responds. If Simon has nothing to add, confirm and continue.

---

**Step 2 — Deep research**

Using `references/startup-evaluation-framework.md` as the guide, research all 8 dimensions:

1. Team
2. Product and Technology
3. Traction
4. Market
5. Business Model
6. Competitive Position
7. Investor Quality and Round Dynamics
8. Insurance and Strategic Relevance

Go significantly deeper than a screen on each dimension. Label all sources. Mark inferences and unverified claims with [Inference] or [Unverified]. Produce a signal rating for each dimension: Positive, Neutral, Negative, or Insufficient data.

---

**Step 3 — Load context files**

Load:
- `Context/professional/company context.md`
- `Context/professional/IAG_Insights_Group.md`
- `Wiki/CoE-Venture-Investment/founder-evaluation.md`
- Any relevant `Projects/` thesis or `Wiki/CoE` sector pages for this company's category

---

**Step 4 — Propose analytical frameworks**

Load `references/analytical-frameworks.md`. Based on the research findings, propose 2–3 frameworks most relevant to this company's stage, category, and the key open questions. For each proposed framework, state:
- Which framework
- What specific question it will help answer for this company
- Why it is more relevant than the alternatives

Use the selection guide in the file to inform the proposal.

**[GATE 2 — Framework selection]**

Present the proposal to Simon:

> "Based on the research, I recommend applying these frameworks: [list with rationale for each]. Which would you like me to apply?"

Apply only the frameworks Simon confirms. Do not proceed to Step 5 until selection is confirmed.

---

**Step 5 — Write the Evaluation Report**

Following `references/evaluation-report-template.md` exactly, populate all sections using the research and the approved frameworks. Write Section 0 (Executive Summary) last, after all other sections are complete. The Executive Summary must include a clear directional recommendation: Proceed, Stop, or Conditional proceed.

Save draft to `Resources/Output files/[company-name]/[company-name]_evaluation-report_v1.pdf`.

**[GATE 3 — Report review]**

Present the Evaluation Report draft to Simon:

> "The Evaluation Report draft is ready. Please review before I start the Opportunity Brief. Let me know if you want to proceed as-is or if anything needs to change first."

Do not begin Step 6 until Simon confirms the report is sufficient. If Simon requests changes, revise and re-present before continuing.

---

**Step 6 — Write the Opportunity Brief**

Following `references/opportunity-brief-template.md`, distill the approved Evaluation Report into the IC-ready brief. Pre-populate all sections from the research. For Sections 4 and 6, pre-fill what can be inferred but flag explicitly:

- Section 4 (Why This Makes Sense for Us): `[Needs your input: validate BU fit and add internal context]`
- Section 6 (Critical Questions): `[Needs your input: add or swap in questions from your meeting]`

Save draft to `Resources/Output files/[company-name]/[company-name]_opportunity-brief_v1.pdf`.

**[GATE 4 — Brief review and final approval]**

Present the Opportunity Brief draft to Simon:

> "The Opportunity Brief draft is ready. Two sections need your input before this is final:
> - Section 4 (Why This Makes Sense for Us): validate BU fit and add any internal context.
> - Section 6 (Critical Questions): add or swap in questions from your meeting.
> Once you confirm, I will incorporate your edits and generate all final outputs."

Incorporate Simon's input. Once Simon approves, proceed to Steps 7 and 8 without further check-ins.

---

**Step 7 — Compile Sources and Further Reading**

Compile all sources used across the research into a single document. Flag the top 10 most valuable sources for further reading, each with a one-sentence note on why it is worth the time.

Save to `Resources/Output files/[company-name]/[company-name]_sources_v1.md`.

---

**Step 8 — Generate final outputs**

Invoke the PDF skill. Generate final versions of the Evaluation Report and Opportunity Brief. Deliver all three files with working links:

- `[company-name]_evaluation-report_v1.pdf`
- `[company-name]_opportunity-brief_v1.pdf`
- `[company-name]_sources_v1.md`

Follow with a single sentence overall take on the opportunity.

---

### Output Definition

All outputs saved to `Resources/Output files/[company-name]/`.

| Output | Format | File name | Done state |
|--------|--------|-----------|------------|
| Evaluation Report | PDF | `[company-name]_evaluation-report_v1.pdf` | All sections complete, signal ratings populated, Executive Summary with clear recommendation |
| Opportunity Brief | PDF | `[company-name]_opportunity-brief_v1.pdf` | All 7 sections complete, Sections 4 and 6 confirmed by Simon, IC-ready |
| Sources and Further Reading | Markdown | `[company-name]_sources_v1.md` | All sources listed, top 10 flagged with reading notes |

Skill is done when all three files are delivered with working links and Simon has approved at Gate 4.

---

## Failure Modes

- Company cannot be identified → ask for clarification before proceeding
- Simon provides no input at Gate 1 → confirm explicitly and proceed; do not fabricate insider context
- Research is too thin at Gate 3 → flag rather than proceeding on weak foundations; tell Simon what is missing and ask whether to do more research or proceed with caveats
- Simon provides no input for Sections 4 and 6 at Gate 4 → deliver with those sections clearly marked as incomplete; do not fabricate strategic rationale
- PDF skill unavailable → deliver formatted markdown and flag the PDF failure
- Output folder already exists → flag to Simon, use incremented version numbers, do not overwrite
