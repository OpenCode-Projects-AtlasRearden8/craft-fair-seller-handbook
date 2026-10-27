# STATUS.md

## What was built

**"The Craft-Fair Seller Handbook"** — a beginner manual for selling in
person at fairs, markets, and conventions, in plain English and
LLC-flavored small-business style (never legal or tax advice), published
as Markdown docs plus a static HTML site generated from them. By Dylan
Asdale / Asdale Dynamics, LLC.

The handbook covers the full arc of a calm seller season: picking the
right events (free scouting included), what applications and sales-tax
permits actually ask in plain English, a budget booth that reads at ten
feet, whole-dollar pricing and the two-hop cash dance with an $85
starting float, card readers rehearsed at the kitchen table, one honest
seven-column tally sheet reconciled to the penny, restock math (the
bring-formula and the hero/filler/experiment split), slow-day and
weather survival with a written go/no-go rule, and — intentionally — a
30-minute same-night after-event review ritual with printable scorecards
that decide next season's bookings.

### Contents (`docs/`, 13 pages)

1. `index.md` — Start Here: the promise, reading shortcuts, ground
   rules, the complement-relationship with the Side-Hustle Reseller
   Handbook, and "what this handbook is not" (the disclaimer)
2. `01-finding-events.md` — four event types in round numbers, the
   five-question event test, the free vendor-scout method (bag-carrier
   watching, vendor three-question interviews), organizer questions,
   event red-flag scams, "start small on purpose," the seasonal
   calendar, and the recurring-market vs excursion split
3. `02-applications-and-permits.md` — every application question
   decoded, the two rules of applying (early; waitlist ≠ rejection),
   business names/DBA/LLC-flavor naming discipline, the W-9 in one
   paragraph (SSN vs EIN, no advice attached), the insurance/COI
   question, sales-tax permits in genuinely plain English, the
   one-phone-call rule to the state's department of revenue, the
   paperwork bring-list, and organizer-collected "fees for taxes"
4. `03-booth-setup-on-a-budget.md` — the $150 starter-kit table with
   free alternatives, the ten-foot rule, the ASCII booth layout, the
   two-tote load-in system, cheap high-value extras, canopy weights as
   the only non-optional extra, photos for applications, and an
   earned-first upgrade order
5. `04-pricing-and-making-change.md` — the three-layer floor formula
   (materials + labor + show share + margin), round-price rounding
   ladder, the three-price raft, bundles and multiples, sales tax at
   the booth (bake-in vs add-on), the $85 starting float breakdown,
   the two-hop cash dance with switch-scam defense, counterfeit
   caution, and the end-of-day take-count
6. `05-card-readers.md` — the reader landscape in one rounded table
   (~2.7% + 10¢ shape), the three choosing questions, the
   kitchen-table dry-run checklist (real $1 test charge + refund), the
   tap flow, tips on/off, refunds, the five-rung offline plan with its
   honest risk notes, battery-bank trio, and the card-side close
7. `06-honest-sales-tracking.md` — hopeful vs honest tracking, the
   seven-column tally sheet with a worked sample, the 10 p.m. footer
   totals (cash + card = gross − refunds − costs = margin-of-the-day),
   tax as a set-aside, the weekly roll-up with the 1-5 rating column,
   backups, and the five rows that pay for the whole system
8. `07-restock-math.md` — sell-through per hour (and per busy-hour),
   the bring-formula (`rate/hour × hours × crowd factor × 1.3`) with
   a worked candle example, the on-shelf vs committed vs truly-
   available table, hero/filler/experiment 70/25/5 stock split,
   deliberate sell-out and the one-third rule, count-before-you-pack,
   and what restock math can't fix
9. `08-slow-days-and-weather.md` — ten slow-hour moves in working
   order, canopy-as-weather-machine (weights, sidewalls, the gutter
   tilt), the wet-weather kit, the go/no-go call, rain-day economics
   in round numbers, and feed-the-seller basics
10. `09-after-event-review.md` — why tonight matters, the 7-step
    30-minute ritual, the five review questions, the season roll-up
    table, rebooking verdicts (return / return with one change /
    pass / never out of guilt), the annual review (cost per $100 of
    sales), photo + receipts archive, and the two-minute fallback
11. `event-scorecards.md` — printable scout card (Scorecard A), the
    ten-row post-event verdict (Scorecard B) with its return/pass
    reading, the event decision matrix, the pre-written wet go/no-go
    rule form, and the season roll-up card (Scorecard C)
12. `packing-checklist.md` — two totes + money kit + paperwork sleeve +
    weather kit + person kit, load-in morning order, load-out night
    order, and the two-rule summary
13. `glossary.md` — plain-English A-to-Z definitions, each cross-linked
    to the chapter that earned it (LLC, W-9, COI, float, bring-formula,
    over/short, switch scam, sell-through rate, wet go/no-go rule, and
    more)

### Site generator (`scripts/`)

- `build.py` — stdlib-only static site generator: small Markdown
  renderer (headings with anchors, paragraphs, fenced code, tables,
  ordered/unordered/checkbox lists with wrapped-line continuation —
  including links that wrap across list-item lines, a bug common to
  sibling generators that this one fixes — blockquotes, rules, inline
  styles, links with automatic `.md` → `.html` conversion), sidebar
  navigation with sections, prev/next paging, accessibility basics
  (skip link, aria labels, semantic HTML, viewport meta). CLI:
  `--out DIR`, `--check` (verify into a temp dir), `--serve`
  (localhost preview). Every build self-checks all pages and links.
- `assets/style.css` — warm readable typography with a market-day
  copper accent, responsive layout, print-friendly checkboxes.
- `test_build.py` — 30 tests: inline rendering, block-level Markdown
  structures (incl. cross-line-link and consecutive-item regression
  tests), and site-level checks (every doc listed in reading order,
  all 9 chapters link the glossary, full build contains all pages,
  internal links resolve, brand/footer/shaded sections render, the
  not-legal-or-tax-advice disclaimer is present on Start Here).

## How to run it

```bash
python3 scripts/build.py            # build site into site/
python3 scripts/build.py --check    # verify into a temp dir, leave site/ alone
python3 scripts/build.py --serve    # build + preview at http://localhost:8000
python3 scripts/test_build.py       # run the 30-test suite
```

Requirements: Python 3.10+ (stdlib only, no installs, fully offline
except the `--serve` localhost listener). Open `site/index.html` after
building.

## Verification results (all passing, 2026-10-27)

- `python3 scripts/build.py` → "Built 13 pages … All checks passed:
  pages built, links resolve, structure valid."
- `python3 scripts/build.py --check` → clean verification into a temp
  directory without touching `site/`.
- `python3 scripts/build.py --out /tmp/…` → clean build to an arbitrary
  directory, all 13 HTML pages + `styles.css` produced.
- `python3 scripts/test_build.py` → **30/30 tests OK** (also verified
  with `python3 -m unittest discover -s scripts`).
- `build.py --serve` → HTTP 200 on `index.html`, `glossary.html`,
  `styles.css`, `event-scorecards.html`, `09-after-event-review.html`.
- Spot-checked rendered HTML: checkbox lists, permit-question tables,
  tally-sheet table, fenced-code worksheets and scorecards, block
  quotes, and `.md` → `.html` link rewriting all render correctly;
  zero unconverted `.md` references across all 13 pages.
- Renderer-bug verification: a Markdown link wrapping across a
  list-item continuation line now converts to HTML (regression test
  added; the pre-fix build produced it unconverted).
- Content lint pass: no non-ASCII artifacts beyond intended math
  symbols (− × ÷ → ≈ — ·), no secrets/API keys/personal data, no TODOs,
  no dead internal links (build passes its link check on every run).

## Known gaps / future ideas

- Sales-tax specifics are deliberately state-agnostic and round; the
  book routs every real question to the state's department of revenue
  ("one-phone-call rule"). A state-by-state appendix is out of scope
  on purpose (it would age fast).
- Card-reader rates are rounded figures that drift; a periodic re-check
  of the reader-landscape table against major providers' published
  pricing is worthwhile.
- No PDF/e-book or print-CSS export yet — the build targets HTML only
  (checkboxes and scorecards are print-friendly by CSS, but a
  dedicated print sheet could go further).
- Possible future extras: a CSV export template for the weekly
  roll-up, a tally-sheet generator page, and a per-event restock
  calculator that fills the bring-formula from last event's numbers.
