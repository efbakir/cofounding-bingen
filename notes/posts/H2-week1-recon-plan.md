# H2 Week 1 — Recon Plan (NOT a post — operational doc for Efe + Bingen)

**Status**: live
**Window**: 2026-04-27 → 2026-05-03 (5 working days)
**Time budget**: ~30 min/day × 5 days = 2.5 hours total. Anything more is procrastination.
**Decision gate**: ≥3 verbatim WTP quotes → proceed to Week 2 (r/nosurf post). <3 → KILL H2, redirect attention to H6 (Eclipta-platform call with Bingen).

---

## Why this week is recon, not posting

H2's pain-validator returned **MAYBE not GO** (median 0/27 across 14 scored HN findings). The reason is structural, not absence of pain — Reddit was blocked at hunt time, and r/nosurf is the highest-priority hunting ground per the hypothesis. WTP signal on HN is anemic because HN is builder-tier, not rage-tier. Reddit fixes that — or kills H2 cleanly.

**No drafts go live this week.** Posting against an unvalidated WTP wedge is how indie hackers ship dead products in crowded lanes. (See: EvoCat — same thesis, alive but commercially flat 12+ months in. F3.)

---

## Lurk-only targets (priority order)

| # | Target | What | Time |
|---|---|---|---|
| 1 | **r/nosurf** | Top + new posts past 30 days. Search: `Opal`, `blocker`, `bypass`, `disable`, `pay`, `would buy`, `tried` | 60 min total over 5 days |
| 2 | **r/digitalminimalism** | Same searches. Cal Newport audience overflow. | 30 min |
| 3 | **r/ADHD focus threads** | Search: "phone blocker doesn't work", "Opal", "ScreenZen". DO NOT POST — anti-self-promo enforced. | 20 min |
| 4 | **Opal community forum** (`community.opalapp.com`) | Top-voted feature requests. What do paying $20/mo Opal users wish existed? | 20 min |
| 5 | **ScreenZen Discord** (`https://discord.com/invite/qwDJm4pZZa`) | Pinned messages, recent #feedback. **Lurk only — competitor's house.** | 10 min |
| 6 | **Brick community board** (Canny) | Feature requests on `getbrick.com/pages/community-board`. | 10 min |

**Total**: ~150 min / 2.5 hrs across 5 days. Stop at 2.5 hrs even if you want to keep going.

---

## What to capture (verbatim, no paraphrase)

For every comment that hits, write to `notes/discoveries/H2-phone-rage-reset.md` under a new section "Reddit Recon — Week 1":

**Required fields per finding**:
- Source URL (full link)
- Date of comment
- Username (anonymize only if user is throwaway-style)
- **Verbatim quote** — copy-paste, no edits
- WTP type: which of the three buckets does it hit?
  - **(a) $ signal**: explicit "I pay $X for [tool]", "I'd pay $Y for [shape]", "I bought [hardware]", "wasted $Z on [coach/app]"
  - **(b) integration request**: "wish [blocker] also did [grounding/breath/reset]", "I stack [block app] + [meditation app] manually"
  - **(c) bypass-rage with paid tool**: "I pay for Opal and still disable it", "ScreenZen costs me $X and I bypass it daily"
- Tags: `rage` / `bypass` / `meditation-adjacent` / `WTP-stated` / `competitor-churn`

---

## Decision gate — Friday 2026-05-01 EOD

Count verbatim quotes that hit ANY of (a), (b), (c) above.

| Count | Action |
|---|---|
| ≥ 3 | **GO** → escalate H2 status in `notes/hypotheses.md` to `posting`. Activate `notes/posts/H2-reddit-nosurf.md` for Tuesday 2026-05-04. Log decision in `notes/decisions.md`. |
| 1-2 | **HOLD** → extend recon by 3 days, hit r/getdisciplined + r/iphone uninstall threads. If no improvement by 2026-05-06, kill. |
| 0 | **KILL** → move H2 to `notes/graveyard.md` with verbatim "WTP wedge unconfirmed on Reddit after 5 days lurking" reason. Pivot Efe + Bingen attention to H6 (Eclipta-as-platform). |

---

## Owner split

- **Efe**: r/nosurf, r/digitalminimalism, Opal forum, ScreenZen Discord (lurk).
- **Bingen**: r/ADHD focus threads (his domain — meditation/regulation context), Brick Canny.
- **Both**: dump every quote into `notes/discoveries/H2-phone-rage-reset.md` "Reddit Recon — Week 1" section as you find it. Async OK; one file, two writers.

---

## What NOT to do this week

- **No posts.** Not on r/nosurf, not on IH, not on X. Drafts stay parked until Friday's gate.
- **No DMs to HN users.** u/nosduhz, u/lekker-kapsalon etc. stay untouched. We earn that DM by having a v0 — not before.
- **No tweets about "validating H2".** Build-in-public posts come Week 3, not Week 1. Week 1 is private.
- **No EvoCat install / sign-up.** That's a separate task (`competitor-analysis`-skill territory) and not this week's job. If you do it, log it separately and don't let it eat the recon budget.
- **No new hypothesis hunting.** H1, H3, H4 are dead. H5/H7 validators run async. Week 1 is laser on H2-or-die.

---

## If Reddit is still blocked from your environment

1. Try `https://old.reddit.com/r/nosurf/search?q=Opal&restrict_sr=1`
2. Try a mobile browser (sometimes bypasses scraper-block)
3. Worst case: Bingen lurks on his phone, screen-recordings the threads, you transcribe verbatim into the discoveries file
4. Do NOT use Bing/DuckDuckGo cache — those were already verified blocked at hunt time

If Reddit is unreachable for the entire week, that's its own data point: **kill H2 on infrastructure grounds**, because we can't validate it AND can't distribute on it. Move to H6.

---

## Success looks like

By Friday 2026-05-01:
- 3-10 new verbatim findings in `notes/discoveries/H2-phone-rage-reset.md` "Reddit Recon — Week 1"
- One decision logged in `notes/decisions.md`: GO, HOLD, or KILL
- `notes/hypotheses.md` H2 status updated
- If GO: r/nosurf draft scheduled for Tuesday morning EST

That's the whole week. No more, no less.
