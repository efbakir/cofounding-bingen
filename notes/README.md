# notes/

Active ideation. This is where agents write, and where you and Bingen jointly update.

## Files

| File | Contents | Who writes |
|---|---|---|
| `hypotheses.md` | Active hypotheses (H1, H2, ...) | `idea-explorer` agent + manual |
| `graveyard.md` | Killed hypotheses + cause of death | `pain-validator` agent (automatic) |
| `discoveries/H{N}-*.md` | Findings + validation per hypothesis | `problem-hunter` + `pain-validator` + `community-mapper` |
| `posts/H{N}-*.md` | Build-in-public post drafts | `build-in-public-writer` agent |
| `testers.md` | Tester funnel | `tester-funnel` skill |
| `decisions.md` | Joint Efe + Bingen decisions | manual, dated |
| `conflicts.md` | Conflicting positions, 24h cooling area | manual |
| `raw/` | Large JSON/CSV pulled by skills (gitignored) | automatic |

## Workflow

1. Add a new hypothesis to `hypotheses.md` (via idea-explorer or by hand)
2. `/problem-discover H{N}` → creates `discoveries/H{N}-{date}.md`
3. `/pain-score H{N}` → appends a verdict to the same file
4. If GO: `/community-map H{N}` → distribution playbook
5. `/build-in-public-post H{N} reddit` (or another platform) → `posts/H{N}-reddit-{date}.md`
6. Publish the post → use `/tester-funnel add` for everyone who shows interest

## Rules

- Never write paraphrase into `discoveries/` or `posts/` — verbatim quotes are mandatory
- Every entry in `decisions.md` is dated and signed by both (Efe ✓ Bingen ✓)
- Never delete from `graveyard.md` — it's a learning archive
