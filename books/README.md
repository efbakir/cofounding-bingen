# books/

Startup-shaping books. PDFs/EPUBs are not pushed (in `.gitignore`); only notes go under `books/notes/`, and agents read those.

## Suggested reading order (for problem-discovery + build-in-public flow)

| # | Book | Author | Why |
|---|---|---|---|
| 1 | **The Mom Test** | Rob Fitzpatrick | How to ask validation questions without contaminating the answer. Direct extension of the `pain-validator` agent. |
| 2 | **Demand-Side Sales 101** | Bob Moesta | Cleanest take on "Jobs to be Done." Sharpens what `idea-explorer` produces. |
| 3 | **The Lean Startup** | Eric Ries | Build-Measure-Learn loop and MVP definition. The whole repo's mental model is built on top of it. |
| 4 | **Hooked** | Nir Eyal | Habit-forming product loop. Reference for `tester-funnel`'s "using → converted" transition. |
| 5 | **Traction** | Gabriel Weinberg | 19 traction channels. Bedside checklist for `community-mapper` output. |
| 6 | **The Cold Start Problem** | Andrew Chen | Network effects and atomic networks. Useful if a hypothesis pivots toward marketplace/community shape. |
| 7 | **Working Backwards** | Bryar & Carr | Amazon's PR-FAQ technique. Forces `idea-explorer` to write hypotheses as press releases. |
| 8 | **Crossing the Chasm** | Geoffrey Moore | Early adopter → mainstream transition. After validation, before scale. |
| 9 | **Blue Ocean Strategy** | Kim & Mauborgne | Differentiation framework. Reads alongside the `competitor-analysis` skill. |
| 10 | **Zero to One** | Peter Thiel | "What truth do you know that no one else does?" — the headline question for `idea-explorer`. |
| 11 | **Shape Up** | Ryan Singer (Basecamp) | Six-week cycles, appetite-driven scope, no backlogs. Already has notes — see `books/notes/shape-up.md`. |
| 12 | **UX for Lean Startups** | Laura Klein | Behavioral > stated preference, listening tour, concierge MVP. Already has notes. |

## Folder structure

```
books/
├── README.md         (this file)
├── notes/            (markdown notes — versioned)
│   ├── lean-startup.md
│   ├── shape-up.md
│   └── ...
└── *.pdf / *.epub    (gitignored, local only)
```

## Note format

For each book, `books/notes/{slug}.md`:

```markdown
# {Title} — {Author}

**Read**: YYYY-MM-DD
**Pillar**: {discovery / build / sell / scale / mindset}

## TL;DR
{3-5 sentences. Tells someone who hasn't read the book what it does for this repo.}

## Frameworks (for agents)
{Named, transferable frameworks. Example: "Mom Test's 3 anti-patterns: compliment fishing, pitching the hypothesis, asking about future commitments."}

## Quotes
> "{verbatim, with page number}"

## What this means for the repo
- For `idea-explorer`: ...
- For `pain-validator`: ...
```

## How agents use this

When `idea-explorer` runs, it does a `Read` + `Glob` over `books/notes/*.md` and prioritizes the "Frameworks" sections. Add a new note and the next run picks it up automatically.
