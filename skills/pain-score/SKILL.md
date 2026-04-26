---
name: pain-score
description: Score raw findings in a discovery file on three axes — intensity (rage/frustration), frequency (one-off vs recurring), and WTP (willingness to pay). Multiplies into a single 0-27 score per finding. Returns median + verdict KILL/MAYBE/GO. Used by pain-validator agent and callable directly via /pain-score H{N}.
---

# pain-score

## Trigger
- User runs `/pain-score H{N}`
- pain-validator agent invokes this skill
- After problem-discover skill writes findings to `notes/discoveries/H{N}-*.md`

## Inputs
- Hypothesis ID (H{N}) — required
- Discovery file `notes/discoveries/H{N}-*.md` must exist with raw findings (F1, F2, ...)

## Process

### 1. Read findings
Open the latest `notes/discoveries/H{N}-*.md`, parse each F# block.

### 2. Read original hypothesis
Open `notes/hypotheses.md`, find H{N}. Note the WTP signal we were looking for — if findings don't contain that signal at all, that's a kill regardless of intensity/frequency.

### 3. Score each finding on three axes

#### Intensity (0-3)
Read the verbatim quote. Apply:

| Score | Signal |
|---|---|
| 0 | Neutral mention. "Does anyone use X?" "Just curious about Y." |
| 1 | Mild annoyance. "Kind of clunky." "Wish it had X." |
| 2 | Clear frustration. "Wasted hours." "Broken." Emotional language. Names the pain explicitly. |
| 3 | Rage / quit / public callout. Curse words. "I'm done." "Switching." "Garbage." "Scam." Public takedown. |

#### Frequency (0-3)
Cross-check across ALL findings in the file (not just this F):

| Score | Signal |
|---|---|
| 0 | Single isolated post. No similar finding elsewhere. |
| 1 | 2-3 similar posts in last 6 months across the discovery set. |
| 2 | Recurring monthly across multiple users / multiple subs. |
| 3 | Same complaint weekly+, multiple sources, dates span >6 months. |

NOTE: frequency is per-pattern, not per-finding. If 8 findings all describe the same pain, every one of them gets the same frequency score.

#### WTP — Willingness to Pay (0-3)

| Score | Signal |
|---|---|
| 0 | No money signal at all. |
| 1 | Using a free tool that sucks. Could pay, but no proof. |
| 2 | Currently paying for a worse solution OR explicit "I'd pay for X." |
| 3 | Paying real money already AND complaining about price/quality. ("$200/mo for Y and it doesn't even Z.") |

### 4. Compute total per finding
`total = intensity × frequency × WTP` (max 27)

NOTE: multiplicative, not additive — a 0 on any axis nukes the total. Intentional. We need all three.

### 5. Verdict thresholds (median across findings)

| Median | Verdict |
|---|---|
| 0-5 | **KILL** — not enough signal across the set |
| 6-12 | **MAYBE** — one axis is weak, need targeted next experiment |
| 13-27 | **GO** — real signal, hand to community-mapper |

### 6. (Optional) Competitor check
If `competitor-analysis` skill is installed and verdict is GO/MAYBE, invoke it to verify the problem isn't already well-served. Note any direct competitors found.

### 7. Write verdict
Append to the same `notes/discoveries/H{N}-*.md`:

```markdown
---

## Validation — {YYYY-MM-DD}

| Finding | I | F | WTP | Total | Quote anchor |
|---|---|---|---|---|---|
| F1 | 2 | 3 | 2 | 12 | "wasted 4 hours on..." |
| F2 | 3 | 3 | 1 | 9 | "I rage-quit..." |
| ... |

**Median total**: X
**Verdict**: KILL / MAYBE / GO

**Why**:
- Strongest axis: {intensity / frequency / WTP} — evidence: F#, "{quote snippet}"
- Weakest axis: {axis} — gap: {what's missing}
- {existing competitors found?}: {Y / N — list}

**Next step**: {kill + graveyard entry / re-hunt with focus on {axis} / hand to community-mapper}
```

If KILL: also append 2-line postmortem to `notes/graveyard.md` and update H{N} status in `notes/hypotheses.md` to `killed`.

## Output to caller
- Median score, verdict, one-line "what I'd do next"

## Rules
- **Default to lower scores.** False negatives are cheap, false positives waste months.
- **Quote evidence for every score >= 2.** No anchor quote = score 1.
- **Multiplicative, not additive.** A 0 on any axis = total 0. This is by design.
- **No vibes-based scoring.** "Feels strong" isn't a justification.
- **Don't move the goalposts.** If the hypothesis defined a specific WTP signal and we didn't find it, kill — even if intensity/frequency are high.
