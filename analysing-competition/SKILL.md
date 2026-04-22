---
name: analysing-competition
description: "Use this skill to map the competitive landscape for a specific startup under active evaluation. Trigger when Simon says 'competitive analysis for [company]', 'map competitors for this deal', 'who does [company] compete with', 'run competitive research on [company]', 'moat analysis', 'how differentiated is [company]', 'competitive section for IC', or when a pitch deck, company URL, or DD notes are shared with questions about defensibility, market position, or competitive risk. Distinct from competitive-research (sector-level thesis work) — this skill is startup-specific, designed for active DD, and produces IC-ready output importable into deal memo drafting without rework."
---

<!-- version: 1.0 | tested-on: claude-sonnet-4-6 -->

# Analysing Competition

## Triggers

Use this skill when the user asks about a specific startup's competitive position during active evaluation. Specific phrases:
"competitive analysis for [company]", "map competitors for this deal", "who does [company] compete with",
"run competitive research on [company]", "moat analysis", "how differentiated is [company]",
"competitive section for IC", "is there a real moat here?", "what could kill this deal competitively?"

Also trigger when a pitch deck, company URL, DD notes, or prior screening PDF is shared and the user asks
about market position, defensibility, differentiation, or competitive risk — even without an explicit trigger phrase.

Do not trigger for sector-level landscape mapping or thesis development — that is the `competitive-research` skill.

---

## Dependencies

- Web search and web fetch tools (required)
- PDF skill (required)
- `Context/professional/company context.md` — IAGFV lens and CVC participation risk flags
- `Context/professional/IAG_Insights_Group.md` — IAG divisions (for strategic backer conflict checks)
- `references/moat-framework.md` — canonical moat taxonomy, scoring guide, red flags (load before Moat Assessment)
- `references/competitive-map-template.md` — Competitive Map table format and column definitions (load before Step 4)
- `references/ic-competitive-checklist.md` — IC questions for pre-flight self-review (load before Gate 2)
- Optional: pitch deck, DD notes, prior screening PDF if available in context or `Resources/Output files/`

---

## Instructions

This skill has two mandatory human gates. Do not skip either.

### Step 1 — Resolve the startup

Confirm the company name and canonical URL. If a pitch deck or prior screening PDF exists for this company
in `Resources/Output files/` or context, load it now — it will anchor the competitive framing and save
redundant research.

---

### [GATE 1] — Input confirmation

Before starting any research, present a brief scope summary and ask:

> "I'll map the competitive landscape for [Company]. Confirm:
> 1. URL / deck / DD notes to load: [list what you've found, or 'none identified']
> 2. Any specific competitive question to anchor the analysis? (e.g. 'is there a real moat?', 'how does this compare to [named competitor]?')
> 3. Any sector or thesis frame I should apply? (e.g. 'insurtech claims automation')"

Wait for confirmation before proceeding. If the user says "go" with no additions, proceed with defaults.

---

### Step 2 — Research

Run layered searches. The goal is an honest picture of the competitive field, not validation of the founder's framing.

**Company research:**
- Fetch the startup's website (homepage, product pages, blog). Note what they say about competitors — treat it as a research prompt, not a fact.
- Search: `[company name] competitors`, `[company name] vs [category]`, `[company name] alternative`

**Direct competitor identification:**
- `[category] startups [year]`, `[category] venture backed`, `[category] series A B funded`
- `[category] software vendors`, `best [category] tools`, Y Combinator batch searches if relevant
- Search for recent funding announcements, pivots, and customer wins among competitors

**Indirect competitors and substitutes:**
- Explicitly search for manual process alternatives, Excel-based workflows, and internal build options
- `[problem] without software`, `how do [buyer type] currently handle [problem]`

**Strategic backers:**
- For each significant competitor, note investor names. Cross-reference against IAG business units.
  Flag any backer that could create a participation conflict (load `Context/professional/company context.md`).

Label every data point with its source URL. Mark inferences with [Inference] and unverified claims with [Unverified].
Do not fabricate funding figures — use only publicly announced rounds; mark unknown as "undisclosed".

If the founder claims zero competition: treat this as a research prompt. Look harder. Surface alternatives.
"We have no competitors" is a yellow flag, not a finding.

### Step 3 — Structure the competitive set

Load `references/competitive-map-template.md`. Organise findings into three tiers:
1. **Direct competitors** — same product, same buyer, same problem
2. **Indirect competitors** — different approach, same problem, same buyer
3. **Substitutes** — manual processes, Excel, internal builds, status quo

If the competitor set exceeds 10 players, cluster by archetype rather than listing individually.
Prioritise recency: a competitor that raised 12 months ago is more dangerous than one that raised 3 years ago.

---

### Step 4 — Write the report

Produce the report in the following fixed structure. Do not reorder or rename sections.

---

**COMPETITIVE ANALYSIS — [COMPANY NAME]**
*Date: [today's date] | Prepared by: IAGFV*

**Executive Verdict** (2–3 sentences)
Is the startup's competitive position a reason to invest, a risk to manage, or a deal-breaker?
Be direct. This sets the frame for the IC reader before they read anything else.

**1. Competitive Map**
Use the table format from `references/competitive-map-template.md`.
Columns: Name | Type | Founded | HQ | Funding | Key Differentiator | Est. Scale | Strategic Backer
Flag any backer with a potential IAG conflict as ⚠️ CVC conflict risk.

**2. Differentiation Analysis**
Where does the startup genuinely differ — and where are founder claims unsubstantiated or temporary?
Distinguish: "we are better" (execution advantage, temporary) vs. "we are different" (structural, durable).
Stress-test differentiation against what customers actually pay for, not what the deck asserts.
If three or more well-funded players are at similar stages targeting the same buyer, name the margin compression risk explicitly.

**3. Moat Assessment**
Load `references/moat-framework.md`. Score and narrate each of the six moat types:
Network effects | Proprietary data | Switching costs | Brand | Regulatory | Distribution
For each: score (Strong / Moderate / Weak / None), 1–2 sentence rationale, and red flags if present.
A switching cost that doesn't demonstrably lock in customers is not a moat — say so.

**4. Competitive Risks**
At minimum, cover:
- What happens if a well-funded incumbent enters or accelerates in this category?
- What happens if the best-capitalised peer raises a large round and compresses pricing?
- "What could kill this?" — one specific, credible scenario written in plain language
- If competing against manual processes or Excel: frame the risk differently — the enemy is inertia and
  IT procurement cycles, not a $500M SaaS incumbent

**5. IC Verdict**
One opinionated paragraph. Competitive position as an investment signal: green light, yellow flag, or red flag?
Do not hedge into meaninglessness. If the position is weak, say so with the specific evidence.
If the anchor question from Gate 1 was provided, answer it directly here.

**Sources**
List the top 15 sources consulted, prioritising analysis articles, research reports, and industry commentary
over company websites or press releases. Format: [Title](URL) — [1-sentence note on why it's worth reading].
Aim for sources Simon can read to go deeper, not sources that simply confirm the report's findings.

---

### [GATE 2] — Draft review

Present the full report draft (not as a PDF yet). Ask:

> "Here's the draft. Before I generate the PDF:
> - Anything factually wrong or missing?
> - Want me to go deeper on any section, competitor, or moat type?
> - Any insider context (meeting notes, founder claims, BU conversations) to incorporate?
>
> Say 'go' to generate the PDF, or give me changes and I'll revise first."

Wait for input. If the user requests further research, run it and revise the affected sections before looping
back. Do not generate the PDF until the user explicitly says to proceed.

### Step 5 — Generate PDF and save

Invoke the PDF skill. Save to `Resources/Output files/[company-name]_competitive-analysis_v1.pdf`.

Present the PDF link followed by one sentence restating the Executive Verdict.

---

## Failure Modes

- **Company cannot be identified** — ask for clarification before any research begins
- **Insufficient public data for early-stage startup** — run category-level analysis, flag data thinness
  explicitly in the Executive Verdict, and do not speculate on individual players
- **Competitor set is fragmented (10+ small players)** — cluster by archetype; do not list all individually
- **Founder claims zero competition** — treat as a research prompt, look harder, surface alternatives;
  explain in Section 2 what was found and what the "no competitors" claim signals
- **Anchor question not answerable from public data** — flag in IC Verdict and recommend a specific
  due diligence action (reference call, demo, data room request) to resolve it
- **CVC conflict identified** — flag in the Competitive Map with ⚠️ and call it out in IC Verdict;
  do not bury it in a footnote
- **PDF skill unavailable** — deliver formatted markdown, flag PDF failure to the user
