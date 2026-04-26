# The Lean Startup — Eric Ries

**Read**: in progress
**Pillar**: discovery + build
**File**: `books/Lean Startup Eric Ries.pdf`

## TL;DR

A startup is "a human institution designed to create a new product or service under conditions of extreme uncertainty." That sentence is the whole book. Building under uncertainty means thinking like a scientist: state a hypothesis, run the smallest possible test, learn, accelerate the loop. The **speed** of the Build–Measure–Learn cycle matters more than your craftsmanship or intelligence — because every cycle teaches you what you got wrong.

This book is the core mental model of cofounding-bingen. The "kill fast" discipline of `pain-validator`, the "specific persona required" rule of `idea-explorer`, the existence of `notes/graveyard.md` — they're all the operational form of Lean.

## Core frameworks (for agents)

### 1. Build–Measure–Learn loop
Each hypothesis runs through:
- **Build** — the smallest possible thing (the "what we're building" line in the hypothesis, the one-sentence MVP)
- **Measure** — who did what, in **behavior** not words ("I'd pay" → real money, not stated intent)
- **Learn** — was the hypothesis confirmed, falsified, or pivot-worthy?

In cofounding-bingen the loop maps to:
- Build = `notes/posts/H{N}-*.md` (post drafts or small prototypes)
- Measure = `notes/testers.md` funnel transitions (interested → contacted → onboarded → using → converted)
- Learn = `notes/discoveries/H{N}-*.md` "Validation" section + verdict

### 2. MVP (Minimum Viable Product)
"The smallest thing that lets you start the learning loop." Smallest ≠ worst. Smallest = focused only on the hypothesis being tested, no feature drift. A single post can be an MVP.

In cofounding-bingen, the MVP is the output of `build-in-public-post` skill. The post is the smallest thing that gathers "I would pay for this" responses. No code yet.

### 3. Validated learning vs vanity metrics
- **Vanity** — total users, total followers, numbers that can't falsify your hypothesis
- **Validated** — cohort-based, behavior-based, numbers that prove or disprove

In cofounding-bingen:
- Vanity ❌ — "the post got 500 upvotes"
- Validated ✓ — "the post drove 23 DMs, 11 of those took the 15-min call, 4 asked for prototype access"
- The `tester-funnel` skill tracks validated metrics by definition — every stage transition is a behavior.

### 4. Pivot vs Persevere
At the end of every loop, two options: **persevere** (continue with the same hypothesis) or **pivot** (change one part of it).

Ries's pivot types:
- **Zoom-in** — a sub-feature becomes the main product
- **Zoom-out** — the product becomes a feature of a larger product
- **Customer segment** — same problem, different persona
- **Customer need** — same persona, different problem
- **Platform / technology / business model**

In cofounding-bingen, a pivot decision goes to `notes/decisions.md`. When `pain-validator` returns MAYBE with "weak axis" notes, that's already a hint at which pivot is needed (e.g. low WTP but high intensity → "customer segment" pivot, look for the same pain in a higher-paying segment).

### 5. Innovation Accounting
Three steps:
1. Establish baseline (first real data from MVP)
2. Tune the engine (hypothesis test cycles)
3. Pivot or persevere (decide after 3 cycles)

For each hypothesis, baseline = first discovery + first post response rate.

### 6. Five Whys (root cause)
When something breaks, ask "why" five times. Each answer becomes the ground for the next "why." Drags the underlying systemic weakness out from beneath the surface technical problem.

In cofounding-bingen: when a hypothesis is killed, the `notes/graveyard.md` postmortem has "Cause of death" + "Lesson" — the minimal form of Five Whys.

### 7. Small batch sizes
Big batch (3 months of silent work → big launch) = high risk, late learning. Small batch (one post, one test per week) = constant learning.

In cofounding-bingen: each hypothesis runs the discover → validate → map → post chain end-to-end in 4 weeks. Then the next one starts. Not a backlog, a batch.

## Quotes
_(verbatim quotes go here as you read, with page numbers — empty for now)_

> "..."  — page N

## What this means for the repo

| Agent / skill | What it borrows from Lean Startup |
|---|---|
| `idea-explorer` | MVP definition discipline — the hypothesis must be sharp enough to define the "smallest thing to test" |
| `problem-hunter` | Get out of the building — Reddit/HN/IH is our "outside" |
| `pain-validator` | Validated learning > vanity. Behavior signal (currently paying) > stated signal (would pay) |
| `community-mapper` | Engine of growth: paid vs viral vs sticky. Which one fits this hypothesis? |
| `build-in-public-writer` | Build = post. Smallest build = fastest learn. |
| `tester-funnel` | Cohort metrics. Which post brought which testers, who churned. |
| `notes/graveyard.md` | Pivot history. Killed hypotheses are Five-Why raw material for future hypotheses. |

## Anti-patterns Ries flags (and we shouldn't fall into)

1. **"Just ship it" without learning** — output theater, no hypothesis
2. **Achievement of delivery vs achievement of learning** — feature shipped ≠ progress
3. **Premature scaling** — scaling before the engine of growth is proven
4. **Vanity metric celebration** — "we got 1000 upvotes this week"
5. **Pivot too late** — not hearing what the data says for 3 months
6. **Pivot too early** — panic decision after one cycle
