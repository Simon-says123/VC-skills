---
name: screening-startups
description: Produces a structured 1-2 page IAGFV initial screening PDF for a named startup or URL using only public sources. Researches the company across seven evaluation dimensions (Team, Traction, TAM, Timing, Tech and Product, Investors, Insurance Relevance), applies the IAGFV screening framework, and generates a formatted PDF with no human check-ins. Use when triaging inbound deals, preparing for a first meeting, or assessing sourced companies. Trigger when the user says 'screen this company', 'screen [name or URL]', 'initial screen on X', 'quick screen', 'triage this one', or whenever a company name is shared with evaluation intent — even without an explicit request phrase.
---

<!-- version: 1.0 | tested-on: claude-sonnet-4-6 -->

# Screening Startups

## Triggers

Use when the user shares a company name or URL with evaluation intent. Specific phrases:
"screen this company", "screen [URL or name]", "do an initial screen", "quick screen on X",
"run a screen on this", "triage this one for me", "give me a screen on [company]".

Also trigger when a company name appears in context with no explicit request phrase but
evaluation is clearly the intent (e.g., "what do you think of Acme AI?" in an IAGFV
deal flow context).

---

## Dependencies

- Web search and web fetch tools (required)
- PDF skill (required)
- `Resources/Templates/initial-screening-framework.md` — seven evaluation dimensions, signal standards, and research guidance (required)
- `Resources/Templates/initial-screening-output.md` — nine-section output structure and formatting rules (required)
- `Context/professional/company context.md` — IAGFV lens, focus areas, evaluation criteria
- `Context/professional/IAG_Insights_Group.md` — IAG divisions and KPIs
- `Resources/insurtech-startups-pitchbook.xlsx`, `Agnostic_VC_Insurtech.xlsx`, `Insurance_CVCs_Global.xlsx` — cross-reference for known companies (load if accessible)
- Relevant `Projects/` or `Wiki/CoE` pages if the sector has prior IAGFV coverage

---

## Instructions

**Mode: Autonomous.** Run the full workflow and deliver a finished PDF with no check-ins. Pause only if a blocking issue arises (company cannot be identified, or a critical data gap changes the assessment materially).

### Goal

Produce a structured, evidence-based initial screening PDF that gives an IAGFV analyst a calibrated lean on a company — interesting or not — based entirely on public sources. The screen must cover all seven evaluation dimensions and surface the questions that only a founder conversation can answer.

### Process

**Step 1 — Load framework and output structure**

Read `Resources/Templates/initial-screening-framework.md` in full. This defines the seven evaluation dimensions, signal standards, and research guidance. Read `Resources/Templates/initial-screening-output.md` for the nine-section output format and formatting rules. Also load `Context/professional/company context.md` and `Context/professional/IAG_Insights_Group.md`. Check for prior sector coverage in `Projects/` or relevant `Wiki/CoE` pages.

**Step 2 — Resolve the company**

If given a name only, find the correct website URL before proceeding. If the company cannot be identified unambiguously, ask for clarification.

**Step 3 — Research**

Conduct structured research across all seven dimensions defined in the framework. For each dimension, apply the signal standards (strong/weak) as the evaluation lens — do not summarise; assess.

Fetch the company website (homepage, About, Team, Blog where accessible). Run targeted web searches covering:

- Funding history and round details (Crunchbase, TechCrunch, press releases)
- Founder backgrounds and prior roles (LinkedIn)
- Known customers, partners, and integration announcements
- Competitive landscape: 2-3 closest alternatives or substitutes
- Recent news, product launches, hiring signals

Cross-reference the pitchbook xlsx files if available. Label every data point with its source. Mark inferences and unverified claims explicitly with [Inference] or [Unverified].

**Step 4 — Populate and generate**

Populate all nine sections from `Resources/Templates/initial-screening-output.md` in order. Apply all formatting rules defined in that file. Then invoke the PDF skill to produce a clean 1-2 page PDF.

Save to `Resources/Output files/[company-name]_initial-screen_v1.pdf`.

Present the PDF link followed by a 2-sentence summary of Section 9 (Initial Take).

---

## Failure Modes

- Company cannot be identified → ask for clarification before proceeding
- `initial-screening-framework.md` or `initial-screening-output.md` not found → notify the user and ask them to confirm the file location before proceeding
- Insufficient public information to populate 3 or more sections meaningfully → do not invent. Flag the gaps explicitly within the PDF and deliver a partial screen with a note at the top explaining what could not be sourced
- PDF skill unavailable → deliver formatted markdown and flag the PDF failure to the user
