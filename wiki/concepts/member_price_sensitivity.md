---
id: member_price_sensitivity
label: Member's underlying sensitivity to cash discount vs Avios cost (unobserved trait)
observed: false
measured_at: pre_treatment
graphs: [pwa-avios]
tags: [dag]
source: interview/q-0001 on 2026-09-06 — reasoned, not measured; no proxy identified yet
confirmed_by: analyst
confirmed_on: 2026-09-06
---

## Causes
- [[pwa_discount_tier_chosen]] {by:analyst on:2026-09-06}
- [[pwa_bookings]] — plausible: a member who is more price-sensitive may also be more
  likely to book at all when better terms are on offer, independent of which tier they end
  up choosing. Not confirmed with a number, flagged as a reasoned edge only. {by:analyst on:2026-09-06}

## What this is
Not a confounder on the schedule→bookings path we care about (schedule assignment is
deterministic on lead time, not on this trait). It matters because it is the reason
`pwa_discount_tier_chosen` is a collider/mediator that should not be conditioned on — see
[[pwa_discount_tier_chosen]]. Under `data_mode: simulated` for this question, `observed:
false` here is a **design choice for the simulation** (we deliberately withhold it from
the estimator to test whether the design still recovers the planted effect), not yet an
established fact about whether this company could ever measure it.
