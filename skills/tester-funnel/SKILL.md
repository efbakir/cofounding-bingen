---
name: tester-funnel
description: Manage the list of people interested in testing what we're building. Add new contacts (from Reddit comments, X DMs, IH replies, LinkedIn), update funnel stage (interested → contacted → onboarded → using → churned/converted), and surface who needs follow-up. Single source of truth lives in notes/testers.md.
---

# tester-funnel

## Trigger
- User runs `/tester-funnel add` (or `update`, `list`, `followup`)
- After a build-in-public post is published and replies start coming in
- Daily during active validation: `/tester-funnel followup` to surface who's overdue

## Subcommands

### `add` — register a new interested tester
Inputs: name/username, platform, source (which post/thread), what they said, contact (DM handle / email)

Append to `notes/testers.md`:
```markdown
- **{name or @handle}** — {platform} — {source: H{N} {platform} post link or DM thread}
  - Said: "{verbatim or 1-line summary}"
  - Contact: {DM / email / form fill}
  - Stage: interested
  - Last touch: {YYYY-MM-DD}
  - Next action: {send prototype link / book 15-min / wait for prototype}
```

### `update` — move someone through the funnel
Inputs: name/handle + new stage

Stages (left to right):
- `interested` — said yes to testing, not contacted yet
- `contacted` — DM sent, awaiting response
- `onboarded` — has access to prototype/early version
- `using` — actively using, gave at least one piece of feedback
- `converted` — paid (even $1, signal matters)
- `churned` — went silent for 14+ days OR explicitly opted out

Edit the entry in-place, update Stage + Last touch + Next action.

### `list` — show current funnel
Read `notes/testers.md`, group by stage, count per stage, output a table:

```
Stage         Count   Names
interested    7       @ana, u/bob, ...
contacted     3       ...
onboarded     2       ...
using         1       ...
converted     0       —
churned       2       ...
```

### `followup` — surface overdue contacts
Read all entries, return anyone where:
- Stage = `interested` AND last touch > 3 days ago
- Stage = `contacted` AND last touch > 5 days ago
- Stage = `onboarded` AND last touch > 7 days ago
- Stage = `using` AND last touch > 10 days ago

For each, suggest a specific follow-up action.

## File format

`notes/testers.md`:

```markdown
# Testers funnel

## interested ({count})
- ...

## contacted ({count})
- ...

## onboarded ({count})
- ...

## using ({count})
- ...

## converted ({count})
- ...

## churned ({count})
- ...
```

## Rules
- **Verbatim quotes** when adding — what they actually said, not "they expressed interest"
- **Always log source** — which post/DM/thread brought them in
- **No fabrication** — if you don't have a contact method, set Contact to "no DM yet, follow up via comment thread"
- **Move backward is OK** — if someone goes silent then re-engages, move them forward again with a new "Last touch"
- **Churn is data** — don't delete churned entries; we want to see ratio over time
- **Privacy** — if someone shared via DM, don't post their full name in a public repo. Use handle / first name only.
