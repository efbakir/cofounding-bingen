# Shape Up — Ryan Singer (Basecamp)

**Read**: in progress
**Pillar**: build + scope discipline
**File**: `books/Shape Up Ship Work that Matters.pdf`

## TL;DR

Singer's thesis: backlogs and sprint planning meetings are killing you. Replace them with **shaped work + 6-week bets + 2-week cooldown**. No one starts building until the work is shaped; once shaped, **appetite is fixed and scope is flexible**. When 6 weeks are up: ship or kill, no extensions. The "circuit breaker" principle.

Critical for cofounding-bingen: a hypothesis = a bet. Each hypothesis has a fixed appetite (1 week? 2 weeks?), with dynamic scope. When the appetite runs out, the hypothesis is either validated (move to posting) or killed — never extended. No backlog; only the hypotheses currently being shaped, and the one we're currently betting on.

## Core frameworks (for agents)

### 1. Shaping vs Building
Two separate modes of mind:
- **Shaping** (before) — define the problem, sketch the solution roughly, mark rabbit holes, set no-gos. Senior people do this. Written output: the **pitch document**.
- **Building** (after) — take the shaped pitch, decompose it into small steps, build. Mixed senior + junior team.

If these two modes mix: either build without shape (chaos) or shape without build (over-engineering). Separate them.

In cofounding-bingen:
- **Shaping** = `idea-explorer` + filling out `notes/hypotheses.md`
- **Building** = `problem-hunter` + `pain-validator` + `community-mapper` + `build-in-public-writer` chain
- Unshaped hypotheses (missing persona / WTP signal / kill criteria) don't get built on.

### 2. Appetite (NOT estimate)
**Estimate** = "how long will this take?" — dangerous, always slips.
**Appetite** = "how much time are we willing to spend on this?" — fixed, scope fits inside.

You set the appetite first, then cut scope to fit. Not the other way around.

In cofounding-bingen:
- Each hypothesis has an appetite = 1 week (small bet) or 2 weeks (big bet)
- We can add a field to `notes/hypotheses.md`: `Appetite: 1 week / 2 weeks`
- When time's up, the call is "is this signal enough?"; if not, **scope gets pulled back** (e.g. stay in 2 subs instead of 5)

### 3. Pitch document
Every shaped piece of work has 5 sections:
1. **Problem** — a real use case or frustration, not abstract
2. **Appetite** — how much time, why
3. **Solution** — fat marker sketch (low fidelity), embedded screen drawings
4. **Rabbit holes** — known traps (risky areas we caught upfront)
5. **No-gos** — explicitly out of scope (so they don't sneak back in)

In cofounding-bingen, the pitch document = the H{N} block in `notes/hypotheses.md`. The current format already maps to Singer's pitch:

| Pitch | Our field |
|---|---|
| Problem | "one-line problem statement" + "Why it sucks" |
| Appetite | (missing — could be added) |
| Solution | "What they do today" + WTP signal |
| Rabbit holes | "Kill criteria" |
| No-gos | (missing — could be added) |

### 4. Fat marker sketches
First solution drawings are done with a fat marker — fine detail isn't possible. If you draw detail too early, you're committing too early; the shaping phase should produce a **set of options**, not a decision.

The cofounding-bingen analog: build-in-public post DRAFT = fat marker. No prototype, no code yet — just "we want to solve this problem, we're posting in this sub, here's what we expect to hear back." Test before drilling deep.

### 5. Hill chart (figuring out vs executing)
When work is climbing the hill (figuring out: unsolved, problem-solving) and when it's coming down (executing: known, just typing) are different states. The hill chart visualizes this — each scope item is a dot on either side.

In cofounding-bingen:
- A hypothesis going `fresh` → `hunting` → `validated` → `mapping` = **climbing the hill** (learning)
- A hypothesis going `posting` → `live` = **coming down the hill** (executing)
- The status field is already a text-form hill chart

### 6. Circuit breaker (deadline > scope)
When the 6 weeks are up: ship or close. No extensions. Deadline beats scope. Because once "we'll just extend a week" becomes habit, the system's discipline collapses.

In cofounding-bingen:
- When a hypothesis hits its appetite, `pain-validator` scores it; whatever the result, **the decision day arrives**.
- KILL → graveyard
- GO → community-mapper continues
- MAYBE → 1 extra week of appetite (only once), then a hard call
- There is no "three-week extension."

### 7. Bets, not backlogs
A backlog = "the 200 things we'll get to one day" = paralysis + false confidence. Instead, every cycle pick **2-3 bets** out of 5-6 shaped pitches. Everything else lives in a "good idea" archive — needs a trigger to come back.

In cofounding-bingen:
- `notes/hypotheses.md` is the active bets list (max 5-6)
- Older "interesting but not now" ideas could go to `notes/hypotheses-shelf.md` (doesn't exist yet — open it when needed)
- `graveyard.md` = killed bets (re-entry trigger: "new evidence emerged")

### 8. Scope hammering
If scope grows during the build, hammer it down. Not "must vs nice" — "in vs out." Anything not shipped at the cycle deadline = out.

In cofounding-bingen: if discovery scope creeps (10 subs instead of 20), hammer — stay in the top 3 subs.

## Quotes
_(verbatim quotes go here as you read, with page numbers)_

> "..."  — page N

## What this means for the repo

| Agent / skill | What it borrows from Shape Up |
|---|---|
| `idea-explorer` | Shaping = written discipline. Pitch document = hypothesis template |
| `problem-hunter` | Appetite-driven scope. 1 week = top 3 subs. 2 weeks = +HN +IH. |
| `pain-validator` | Circuit breaker. When appetite runs out, decide — no extensions |
| `community-mapper` | Fat marker sketch = posting calendar (low fidelity, 4-week plan) |
| `build-in-public-writer` | Solution sketch = post draft (no prototype yet) |
| `notes/hypotheses.md` | Pitch document — Appetite + No-gos fields should be added |
| `notes/graveyard.md` | Killed bets archive, not a backlog |
| `notes/decisions.md` | Hill chart snapshot — which hypothesis is on which side of the hill |

## Currently missing (closer to Singer's method if added)

1. Add an **Appetite** field to the `notes/hypotheses.md` template (1w / 2w)
2. Add a **No-gos** field to the `notes/hypotheses.md` template (explicitly out of scope)
3. A "cooldown" concept: every 2-3 cycles, take 1 week off from new hypotheses — only reflection + book notes + tooling

## Anti-patterns Singer flags

1. **Backlog grooming** — endlessly re-prioritizing "good ideas," never shaping any
2. **Estimate-driven planning** — making plans with timelines that never hold
3. **Scope creep mid-build** — doing shaping work during the build phase
4. **Extending past the circuit breaker** — "if we just give it one more week..." → discipline dies
5. **Shaping by junior team** — shaping is a senior decision; shallow shape = shallow pitch
