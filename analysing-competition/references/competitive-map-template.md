# Competitive Map Template

Use this template for the Competitive Map section (Section 1) of every competitive analysis report.
The table must include all three competitor tiers. Do not collapse tiers.

---

## Table format

| Name | Type | Founded | HQ | Funding (USD) | Key Differentiator | Est. Scale | Strategic Backer |
|------|------|---------|----|--------------|--------------------|------------|-----------------|
| [Company A] | Direct | [Year] | [City, Country] | $[X]M Series [X] | [1-sentence claim] | [Employees / ARR signal if available] | [Lead investor or parent — ⚠️ if IAG conflict] |
| [Company B] | Indirect | [Year] | [City, Country] | Undisclosed | [1-sentence claim] | [Signal] | [Investor] |
| [Manual process / Excel / Internal build] | Substitute | — | — | — | Status quo; no switching cost | Widespread | — |

---

## Column definitions

**Name**
Company name and website URL inline (e.g. [Acme](https://acme.com)).

**Type**
One of: Direct | Indirect | Substitute
- Direct: same product, same buyer, same problem
- Indirect: different solution approach, same problem, same buyer
- Substitute: manual process, Excel, legacy tool, or internal build that solves the same problem without dedicated software

**Founded**
Year founded. Mark as [Unverified] if sourced from secondary sources only.

**HQ**
City and country. Relevant for geographic expansion risk and regulatory jurisdiction.

**Funding (USD)**
Total publicly announced funding. Use "Undisclosed" if no public data. Never estimate. Cite source.
For public companies: note market cap tier instead (e.g. "Public, ~$2B market cap").

**Key Differentiator**
One sentence maximum. This is their claimed edge — stress-test it in Section 2 (Differentiation Analysis), not here.
If their claimed differentiator is vague or unsubstantiated, note that in Section 2.

**Est. Scale**
Any publicly available traction signal: employee count (LinkedIn), named customer logos, ARR if disclosed in press,
app download figures, geographic footprint. Mark as [Unverified] if from secondary sources.
Do not estimate ARR or revenue without a source.

**Strategic Backer**
Lead investor(s) or corporate parent if relevant. Flag with ⚠️ CVC conflict risk if a backer is an insurer,
reinsurer, or financial services firm that could conflict with IAG's participation in this round.
Load `Context/professional/company context.md` to check IAG's known investor relationships before assigning flags.

---

## Archetype clustering (for fragmented markets)

If the competitor set exceeds 10 players, do not list all individually.
Cluster into archetypes and add a summary row per archetype:

| Archetype | # Players | Representative Examples | Common Positioning | Shared Weakness |
|-----------|-----------|------------------------|--------------------|----------------|
| [e.g. AI-native point solutions] | 8 | [A], [B], [C] | Narrow workflow automation | No enterprise integrations; point solution risk |
| [e.g. Legacy incumbents] | 3 | [X], [Y], [Z] | Broad coverage, established trust | Slow product velocity; weak AI capability |

Then list only the 3–4 most relevant individual players in the full table above.

---

## Formatting notes

- Sort rows within each tier by funding (largest to smallest) — higher funding signals greater competitive threat
- If a competitor has raised a round in the past 12 months, bold the funding figure to flag recency
- Always include at least one Substitute row — "we have no substitutes" is almost never true in enterprise software
