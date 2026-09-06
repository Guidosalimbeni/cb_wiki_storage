---
id: pwa_avios_redeemed
label: Avios redeemed through PWA (per booking / window total)
observed: true
measured_at: post_treatment
graphs: [pwa-avios]
tags: [dag]
source: interview/q-0001 on 2026-09-06
confirmed_by: analyst
confirmed_on: 2026-09-06
---

## Caused by
- [[pwa_discount_tier_chosen]] — the chosen tier's discount % and conversion rate largely
  determine Avios redeemed on a booking; mostly mechanical given the tier, but the tier
  choice itself is a causal outcome of the schedule. {by:analyst on:2026-09-06}

## What this is
Not the outcome for q-0001 (that is [[pwa_bookings]]). Recorded because
[[2026-08-conversion-rate-flip-experiment]] lists it as touched by the treatment, and
because a future margin question will need it. Out of scope for this question's estimate.

`data_mode: simulated` for q-0001: `observed: true` is a design choice, unused by this
question's estimator; kept for graph completeness only.
