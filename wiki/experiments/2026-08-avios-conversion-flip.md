---
id: 2026-08-avios-conversion-flip
ran: [2026-08-01, 2026-08-14]
design: none                # not randomised — attempted DiD, found contaminated. see below
unit: booking
graph: pwa-avios              # tentative — no graph drawn yet, no interview has happened
methods: []
source: raw/iagl_pwa

# No usable prior yet — the identification attempt failed. Filled in honestly rather
# than fabricated; see "What it found" and "Do not reuse this if".
priors: []
---

## What was tested
See [[2026-08-conversion-rate-flip-experiment]] for the policy change itself: for the
first two weeks of August 2026, the conversion-rate schedule across the up-to-9 discount
tiers was flipped (max discount tier got the best conversion rate instead of the worst),
applied to all members and routes, but only for bookings with a 2026 departure date.

## Design
**Not an A/B test.** There was no treatment/control split — the policy applied
uniformly to all members and routes booking a 2026 departure in the window. The only
candidate comparison groups are:
- a temporal comparison (before/after, or same period last year), or
- a departure-date boundary comparison (2026 departures, treated, vs 2027+ departures,
  untreated) within the same booking window.

## What was tried, and why it failed
A difference-in-differences was attempted using a temporal split: the same two-week
period one year earlier (Aug 2026 vs 2025) as treatment/post vs control/pre, with a
month-earlier window in each year as an additional pre-period check.

**This DiD is reported as biased**: the same period last year (Aug 2025) was itself
"heavily contaminated by another change that happened last year" (unspecified in the
source — not yet identified what that change was). This breaks the parallel-trends
assumption the DiD needs, so the resulting estimate should not be trusted or reused.

## What it found
No trustworthy effect estimate is available from this material. The naive DiD is known
to be biased; no other identification strategy has been executed yet against this
window.

## Heterogeneity / CATE
Not assessed — no valid design has been run yet.

## Priors this gives you
**None usable.** Do not centre any model on a number computed from the contaminated
DiD above. The 2026-vs-2027-departure-date boundary within the experiment window is
untried and may be a cleaner design (RDD-style on departure date) — worth pursuing in a
future question rather than reusing the DiD number.

## What it constrains in the graph
No graph has been drawn for this yet — no interview has taken place. This page exists to
record the raw material and the known threat (contaminated same-year-ago comparison)
before anyone tries the DiD again.

## Do not reuse this if
Do not reuse the same-period-last-year comparison for anything until the "other change
that happened last year" mentioned in the source is identified and dated. Until then,
treat 2025-08 as a known-bad control period for this product.

## Questions that used it
(none yet)
