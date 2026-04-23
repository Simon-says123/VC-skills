---
name: synthesising-research
description: >
  Condenses batches of research reading — reports, articles, expert call transcripts,
  clippings, DD notes — into a structured internal insight memo. Output: a single
  markdown memo with executive 'so what', key signals, contrarian angles, thesis
  implications, and action items. Trigger when Simon says 'synthesise this reading',
  'pull insights from these docs', 'weekly research digest', 'summarise what I've been
  reading', 'turn this into a memo', or 'what's the so-what'. Also use when Simon shares
  a folder of research, multiple PDFs, or a batch of clippings and asks for synthesis or
  insight extraction — even without an explicit trigger phrase. Sits between wiki-ingest
  (filing action) and vc-output-packaging (stakeholder delivery): raw reading in,
  insight memo out.
---

<!-- version: 1.0 | tested-on: claude-sonnet-4-6 -->

# Synthesising Research

## Triggers
Use this skill when Simon says: "synthesise this reading", "pull insights from these docs",
"weekly research digest", "summarise what I've been reading", "turn this into a memo",
"what's the so-what". Also trigger when Simon shares a folder of research, multiple PDFs,
or a batch of clippings and asks for synthesis — even if "synthesis" is not the word used.

Do not trigger for:
- Filing clippings into the wiki → use wiki-ingest
- Packaging a memo for stakeholders → use vc-output-packaging

---

## Dependencies
- Read access to input folder or sources
- `references/synthesis-structure.md` — always read before writing the memo
- `references/source-citation-format.md` — always read before writing the memo
- `references/signal-vs-noise-heuristics.md` — read if present; use built-in heuristics if missing (see Failure Modes)

---

## Instructions

Freedom level: **Medium** — the memo structure is fixed; judgement calls on signal vs. noise have room.

### Step 0 — Load references

Before doing anything else, read:
1. `references/synthesis-structure.md`
2. `references/source-citation-format.md`
3. `references/signal-vs-noise-heuristics.md` (if present)

### Step 1 — Gate 1: Thesis frame

Check whether Simon has provided a sector or thesis frame.

If not, ask before proceeding:
> "What sector or thesis frame should anchor this synthesis? (e.g. 'insurtech distribution', 'climate risk modelling', or 'general scan — no frame')"

Do not proceed until you have a frame or Simon explicitly declines to provide one.

### Step 2 — Gate 2: Input confirmation

Scan the specified folder or source list. Present to Simon:
- List of sources found (file names, types, approximate date range if detectable)
- Any sources that look unreadable or out of scope
- If a time window was specified, which sources fall within it

Ask Simon to confirm the source set. Simon can add, remove, or adjust scope before synthesis begins. Only proceed once confirmed.

### Step 3 — Read all sources

Read every confirmed source in full before writing a single sentence of the memo. Do not start drafting mid-read — partial synthesis produces false confidence.

Apply the signal vs. noise heuristics from `references/signal-vs-noise-heuristics.md` (or the defaults in that file). Keep a running mental tally: what cleared the bar and why.

### Step 4 — Apply VC synthesis principles

These are non-negotiable filters on what enters the memo:

1. **So-what for the fund** — every insight must answer "what does this mean for our deal work or thesis?" Observations without investment implication do not go in.
2. **Novel over consensus** — if content merely confirms what is already known, note it as confirmation, do not present it as signal.
3. **Surface disconfirming evidence** — do not bury it. If sources conflict with the current thesis, that belongs in the memo even if inconvenient.
4. **Flag pattern breaks** — anomalies and reversals often mark the start of deal flow. They deserve explicit treatment.
5. **First vs. second order** — distinguish what is happening (first order) from what it implies for pricing, competition, founders, or LPs (second order). Second-order is where the memo earns its keep.

### Step 5 — Write the memo

Follow the template in `references/synthesis-structure.md` exactly. All sections mandatory except Insight Tweets.

- Write the 'So What' section last, even though it appears first
- Every signal in the Key Signals section must carry an inline citation
- Label uncertainty throughout: `[Inference]`, `[Speculation]`, `[Unverified]`
- Use inline citations per `references/source-citation-format.md`
- Ruthless signal-to-noise: nothing enters unless it clears the heuristics bar

### Step 6 — Gate 3: Insight tweets (optional)

After drafting the memo, ask:
> "Do you want a short 'Insight Tweets' block added — 1–3 tweetable insights for internal sharing? Each under 140 characters, no jargon, no context assumed."

Add the block only if Simon confirms. Do not add it speculatively.

### Step 7 — Save and Gate 4: Review

Save the memo to `Resources/Output files/` following the global naming convention:
`synthesis-[topic]_memo_v1.md`

Present the file link, then ask:
> "Does this land? Anything to sharpen or cut?"

Iterate until Simon signs off. A memo is not finished until Simon explicitly confirms it is.

---

## Human-in-the-Loop Gates Summary

| Gate | Trigger | What Simon decides |
|------|---------|-------------------|
| Gate 1 | No thesis frame provided | Provide frame or proceed as general scan |
| Gate 2 | Before synthesis begins | Confirm/adjust source set and time window |
| Gate 3 | After memo draft | Add optional Insight Tweets block |
| Gate 4 | After file saved | Review and iterate until sign-off |

---

## Failure Modes

- **Single source input** — proceed but open the memo with: "⚠️ Thin input: this synthesis is based on a single source. Conclusions should be treated as preliminary." 
- **No thesis frame after prompting** — proceed as general scan; note at top of memo that no thesis frame was applied.
- **signal-vs-noise-heuristics.md missing** — use the built-in defaults in the template file. Flag to Simon: "References/signal-vs-noise-heuristics.md not found — using default heuristics. Customise that file to tune signal filtering to your criteria."
- **Conflicting sources** — surface the conflict explicitly in the relevant section. Do not silently pick the higher-authority source. Format: "Source A states X [citation]; Source B contradicts this, stating Y [citation]. This has not been resolved."
- **No sources found in specified folder** — stop immediately. Tell Simon the folder appears empty or the path is incorrect. Do not attempt to synthesise from memory.
- **Sources unreadable (corrupt, wrong format)** — flag at Gate 2. Do not skip silently.
