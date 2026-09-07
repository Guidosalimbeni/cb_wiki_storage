---
id: 2026-08-conversion-rate-flip-experiment
date_start: 2026-08-01
date_end: 2026-08-14        # "first 2 weeks of August 2026"
announced_on: null          # not stated in source — unknown, flagged below
touches: [pwa_discount_tier_conversion_rate, avios_redeemed, cash, bookings]
visible_in_data: partial    # policy is visible; a clean control group is not
source: raw/pwa_exp   # same text previously ingested under the path raw/iagl_pwa
recorded_by: analyst
recorded_on: 2026-09-06
reingested_on: 2026-09-07
---

## What changed
The mapping between discount tier and conversion rate was flipped for the two-week
window. Normally the **maximum discount** tier carries the **least favourable**
conversion rate for the member (down to 0.004) and the **minimum discount** tier the
**most favourable** (up to 0.01). During the experiment window this was inverted: the
max discount became the *most* favourable conversion rate, and the min discount the
*least* favourable.

Rationale given: this was expected to be costly to IAGL/BA Holidays in the short run —
treated as an investment intended to drive more bookings and, via the combined IAGL + BA
Holidays margin (BA Holidays keeps ~10% of ticket price on top of IAGL's Avios margin),
keep overall margin high despite the richer redemption terms.

## Who it applied to
All members, all routes — but **only for bookings with a future departure date within
2026**.

## Who it did NOT apply to
Bookings with departure dates in 2027 or later kept the standard (non-flipped)
conversion rate schedule. This is the only segmentation boundary recorded — there was no
member-level or route-level split.

## Why it matters causally
This was **not a randomised A/B test** — there is no A/B split of members or bookings;
the policy applied uniformly to everyone booking a 2026 departure. The only exploitable
boundary is the departure-date cutoff (within-2026 vs 2027+), which is a plausible
regression-discontinuity/DiD-style comparison group, not a randomised control.

Announcement timing is not stated in the source — unknown whether members anticipated
the change. Flagged as unclassified/unknown, see ingest summary.

## Known threat to naive analysis
A same-period-last-year (Aug 2025) DiD counterfactual was attempted and found to be
**biased**: that period was contaminated by a separate, different change made last year.
The 2025 change is not named or dated in the source.

See [[2026-08-conversion-rate-flip]] in `wiki/experiments/` for the design and the
(currently absent) readout, [[pay-with-avios-ba-holidays]] for how the product works, and
[[iagl-pwa-metrics]] for the margin and cost-per-Avios formulas.
