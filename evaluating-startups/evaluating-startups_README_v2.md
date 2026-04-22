# evaluating-startups

## What it does
Takes a startup that has cleared initial screening and produces three IC-ready outputs: a 6-page Evaluation Report covering 8 analytical dimensions, a distilled Opportunity Brief, and a Sources document. The skill runs in Co-Worker mode with four mandatory human-in-the-loop gates — pausing to gather insider context before research begins, confirm analytical frameworks after research, approve the Evaluation Report draft before writing the Brief, and incorporate the investor's strategic input before final outputs are generated. This structure ensures the final deliverables reflect both deep public research and the investor's first-hand judgment.

## Reference files
- `references/startup-evaluation-framework.md` — 8-dimension research guide (Team, Product, Traction, Market, Business Model, Competitive Position, Investor Quality, Strategic Relevance)
- `references/analytical-frameworks.md` — 5 analytical frameworks with a selection guide
- `references/evaluation-report-template.md` — 6-page report structure
- `references/opportunity-brief-template.md` — IC-ready brief structure
- `[company context file]` — fund parameters and investment lens
- `[company context file]` — firm divisions and strategic KPIs
- `Wiki/CoE-Venture-Investment/founder-evaluation.md` — team assessment criteria

## Install
Copy this folder into your skills directory, then toggle the skill on in **Customize > Skills**.

## What to change
- `references/startup-evaluation-framework.md` — adjust evaluation dimensions to match your fund's criteria
- `[company context file]` — replace with your own firm's fund parameters and investment thesis
- Opportunity Brief Sections 4 and 6 — pre-fill with your own internal context prompts if desired

## Usage
**Trigger:** "write an opportunity brief for [company]"
**Output:** Three files — Evaluation Report (PDF), Opportunity Brief (PDF), Sources (Markdown)

**The four human-in-the-loop gates:**
- **Gate 1 (before research):** [user] shares meeting notes, pitch deck, and any angles or concerns to prioritise
- **Gate 2 (after research):** [user] confirms which analytical frameworks to apply before the report is written
- **Gate 3 (after Evaluation Report draft):** [user] reviews and approves the report before the Opportunity Brief begins
- **Gate 4 (after Opportunity Brief draft):** [user] adds internal strategic context to two flagged sections before final PDFs are generated

## Model tested on
claude-sonnet-4-6
