# screening-startups

## What it does
Produces a structured 1–2 page initial screening PDF for a named startup or URL using only public sources. Best used when triaging inbound deals, preparing for a first meeting, or assessing sourced companies.

## Reference files
- `references/initial-screening-framework.md` — seven evaluation dimensions, signal standards, and research guidance
- `references/initial-screening-output.md` — nine-section output structure and formatting rules
- `[company context file]` — investment lens, focus areas, and evaluation criteria
- `[company divisions file]` — business units and KPIs used to assess strategic relevance
- `[deal pipeline files]` (.xlsx) — optional cross-reference for known companies

## Install
Copy this folder into your skills directory, then toggle the skill on in **Customize > Skills**.

## What to change
- `references/initial-screening-framework.md` — replace with your own evaluation framework and signal standards
- `references/initial-screening-output.md` — replace with your preferred output template and section structure
- `[company context file]` — supply your own company or fund context so screens are assessed through the right lens
- `[company divisions file]` — supply relevant business unit context if strategic relevance scoring is needed
- `[deal pipeline files]` — optional: point to your own deal pipeline spreadsheets for cross-referencing known companies

## Usage
**Trigger:** "screen [company name or URL]"
**Output:** PDF report (1–2 pages), saved to [your output folder]

## Model tested on
claude-sonnet-4-6
