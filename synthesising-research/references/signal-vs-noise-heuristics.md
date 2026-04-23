# Signal vs. Noise Heuristics

**Status:** Template — customise this file with your own rules.

On first run of synthesising-research, Claude will flag that this file has not been
customised and prompt Simon to supply his own heuristics. Until then, Claude uses
the defaults below.

---

## Default Signal Heuristics

A piece of content clears the signal bar if it meets at least one of the following:

1. **Changes a number** — updates a market size, growth rate, loss ratio, deal count,
   burn multiple, or other quantitative anchor that is currently in use in the thesis.

2. **Names a specific company move** — funding round with terms, strategic pivot,
   shutdown, material partnership, or executive hire that signals directional change
   in a relevant player.

3. **Contradicts consensus** — explicitly disputes or materially qualifies a widely
   held view in the space, with evidence (not just opinion).

4. **Reveals a new buyer or seller behaviour** — evidence of how the actual purchase,
   renewal, or usage decision is changing in ways that affect economics or distribution.

5. **Surfaces a regulatory or structural shift** — a new rule, policy decision, or
   market structure change with direct pricing or competitive implications.

6. **Identifies a meaningful new entrant or exit** — a player arrives, pivots out, or
   shuts down in a way that changes the competitive map.

7. **Provides a primary data point** — direct quotation or finding from an expert call,
   proprietary survey, or DD session that is not publicly available.

---

## Default Noise Heuristics

Exclude by default, regardless of source quality:

- **Restatements of known market size** — "the global [X] market is worth $Y billion"
  without new data, a new source, or a meaningful update to prior figures.

- **Pundit predictions without mechanism** — "AI will transform X within 5 years" with
  no named mechanism, timeline evidence, or named actor driving the change.

- **Company PR framed as news** — press releases and blog posts, especially funding
  announcements without disclosed terms or strategic specifics.

- **Conference consensus** — themes repeated across multiple panels with no new
  evidence introduced. If everyone is saying it, the market has already priced it.

- **Anecdote presented as trend** — a single data point or customer story extrapolated
  to a market-level claim without corroborating sources.

- **Recycled analyst framing** — a repackaging of figures or narratives from widely
  read reports (McKinsey, CB Insights, etc.) with no new interpretation or update.

---

## How to Customise This File

Replace or extend the lists above with rules tuned to the fund's specific thesis areas.
Useful additions:

- **Deal-specific triggers**: "Flag any mention of [Company Name] regardless of context."
- **Thesis-specific signal bars**: "Anything touching parametric catastrophe bond pricing models."
- **Threshold adjustment**: "Require at least 2 signal heuristics met before including."
- **Source-specific rules**: "Treat expert call output as automatically passing the bar."
- **Exclusion overrides**: "Do not exclude McKinsey data if it covers a topic with no
  alternative sources."

Keep every entry concrete and testable. Avoid vague criteria like "interesting" or
"relevant" — they produce inconsistent outputs across synthesis runs.

---

## Customisation Prompt (Claude: use this on first run if file is uncustomised)

> "I'm using the default signal heuristics for this synthesis. These are a reasonable
> starting point but are not tuned to your specific thesis areas. To get sharper,
> more consistent filtering: open references/signal-vs-noise-heuristics.md and replace
> or extend the defaults with your own criteria. The file has instructions on how to do this."
