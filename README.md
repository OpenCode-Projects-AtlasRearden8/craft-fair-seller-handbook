# The Craft-Fair Seller Handbook

A beginner manual for selling in person at fairs, markets, and
conventions — written the way a friend would explain it: clearly, kindly,
and never condescending. It ships as Markdown docs plus a small static
HTML site you can build and read entirely on your own computer.

Written by [Dylan Asdale](https://dylanasdale.github.io) and published by
**Asdale Dynamics, LLC** — beginner-friendly AI education, books, and tools.

## Who it's for

- Makers, authors, and small-shop owners taking their first tables into
  the real world: what events to book, what paperwork actually asks of
  you (in plain English), what a booth costs, how change gets made, and
  how the numbers stay honest.
- People who learn best from step-by-step instructions with round
  numbers, printable checklists, and zero status symbols.
- People who want the *after-event* question answered too: what to
  review, how to decide next season, and how to pass on an event
  without guilt.

## What's inside

| Page | What you'll learn |
| --- | --- |
| [Start here](docs/index.md) | How to use the handbook — and what it is not |
| [Finding events](docs/01-finding-events.md) | Four event types, the five-question test, free scouting, red flags |
| [Applications & permits](docs/02-applications-and-permits.md) | What forms really ask, W-9 in one paragraph, sales-tax permits in plain English |
| [Booth on a budget](docs/03-booth-setup-on-a-budget.md) | The $150 starter kit, the ten-foot rule, the two-tote load-in |
| [Pricing & change](docs/04-pricing-and-making-change.md) | The three-layer floor, round prices, the $85 float, the two-hop cash dance |
| [Card readers](docs/05-card-readers.md) | Reader landscape in round numbers, the kitchen-table dry run, offline plans |
| [Honest sales tracking](docs/06-honest-sales-tracking.md) | One seven-column tally sheet, the 10 p.m. totals, tax as a set-aside |
| [Restock math](docs/07-restock-math.md) | Sell-through rate, the bring-formula, hero/filler/experiment stock |
| [Slow days & weather](docs/08-slow-days-and-weather.md) | Ten slow-hour moves, canopy-as-tent, the go/no-go call |
| [After-event review](docs/09-after-event-review.md) | The 30-minute same-night ritual, rebooking verdicts, the annual review |
| [Event scorecards](docs/event-scorecards.md) | Printable scout card, post-event verdict, decision matrix, wet-weather rule |
| [Packing checklist](docs/packing-checklist.md) | Two totes, one money kit, the paperwork sleeve, load-in/load-out orders |
| [Glossary](docs/glossary.md) | Every word, defined without the jargon fog |

## Built to complement the reseller handbook, not repeat it

This handbook pairs with **The Side-Hustle Reseller Handbook** (selling
online on eBay/Amazon) the way two halves of one small business pair:

- The reseller book covers **online**: listings, photos, shipping,
  marketplace fees, and quitting politely.
- This book covers **in person**: the room you can't retake, the change
  you must make, and the weather you can't reschedule.

They share the same bones — one simple records table, scam radar, calm
exits — and hand work to each other: leftover stock from an event goes
online (their book), and online ideas come to life at a booth (this
one). Neither requires the other. Nothing here duplicates their jobs.

## Build the website

Everything runs on the Python standard library — no installs, no keys,
no accounts, nothing leaves your machine.

```bash
python3 scripts/build.py
```

That writes the finished site into `site/`. Open `site/index.html` in
any browser. The build also self-checks every internal link:

```bash
python3 scripts/build.py --check   # verify into a temp dir (build + checks)
python3 scripts/build.py --out DIR # build somewhere else
python3 scripts/build.py --serve   # build, then preview at http://localhost:8000
```

## Run the tests

The generator ships with a stdlib-only test suite (unit tests for the
Markdown renderer plus site-level checks that every page builds and
every internal link resolves):

```bash
python3 scripts/test_build.py
```

## Repository layout

```
docs/           The handbook, one Markdown file per chapter
scripts/        build.py — markdown-to-HTML static site generator (stdlib only)
scripts/        test_build.py — tests for the generator
scripts/assets/ The stylesheet the build embeds and ships as styles.css
site/           Generated output (safe to delete; rebuild any time)
LICENSE         MIT, © 2026 Asdale Dynamics, LLC
```

## Requirements

Python 3.10 or newer. Nothing to install — the generator and its tests
use only the standard library, work fully offline, and never touch a
network except when `--serve` listens on your own localhost.

## A note on money and law

Booth fees, card-reader rates, and permit details here are **round
numbers on purpose**, for thinking, not filing. This handbook is
education, not tax, legal, or financial advice; when a decision gets
real (money, legal, health), a real professional — and for permits,
your state's own department of revenue — belongs in the conversation.
Event norms and payment-app policies also change; this book is
versioned, and the numbers you rely on are the ones you verify.

## License

MIT — see [LICENSE](LICENSE). © 2026 Asdale Dynamics, LLC. Corrections
and pull requests welcome; be kind, be honest, be plain-spoken.
