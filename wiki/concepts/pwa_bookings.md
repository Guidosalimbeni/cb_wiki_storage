---
id: pwa_bookings
label: PWA-redemption bookings (count, BA Holidays)
observed: true
measured_at: post_treatment
graphs: [pwa-avios]
tags: [dag]
source: interview/q-0001 on 2026-09-06
confirmed_by: analyst
confirmed_on: 2026-09-06
---

## Caused by
- [[pwa_discount_tier_conversion_rate]] — the effect of interest for q-0001: does the
  flipped schedule change how many members complete a PWA-redemption booking, for bookings
  made in the Aug 2026 window. {by:analyst on:2026-09-06}
- [[booking_lead_time]] — a direct, non-treatment path: near-term (2026 departure) vs
  far-out (2027+ departure) bookings may differ in urgency/seasonality independent of the
  schedule in effect. This is the confound the RDD design has to neutralise by working
  locally around the 2027-01-01 cutoff, not something assumed away. {by:analyst on:2026-09-06}
- [[member_price_sensitivity]] — reasoned, unconfirmed-by-number edge; see
  [[member_price_sensitivity]]. {by:analyst on:2026-09-06}

## What this is
Outcome for q-0001. **PWA-redemption bookings specifically** — not all BA Holidays
bookings among members — per analyst, scoped to bookings made 2026-08-01 to 2026-08-14.
No broader population or window is in scope for this question.

Note: `pwa_discount_tier_chosen` and downstream Avios/cash metrics are **not** on this
outcome's identifying path and must not be conditioned on — see
[[pwa_discount_tier_chosen]] for the collider/mediator warning.

`data_mode: simulated` for q-0001: `observed: true` here is a design choice — this node
carries the planted effect the estimator has to recover, not yet a confirmed fact about
what IAGL measures.
</content>
