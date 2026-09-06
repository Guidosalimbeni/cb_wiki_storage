---
id: pwa_discount_tier_chosen
label: Discount tier a member selects (1 of 9) at booking
observed: true
measured_at: post_treatment
graphs: [pwa-avios]
tags: [dag]
source: interview/q-0001 on 2026-09-06
confirmed_by: analyst
confirmed_on: 2026-09-06
---

## Caused by
- [[pwa_discount_tier_conversion_rate]] — which schedule is in effect changes which tier
  looks attractive to the member. {by:analyst on:2026-09-06}
- [[member_price_sensitivity]] — an unobserved member trait: how much a given member
  values cash discount vs Avios spend shapes which tier they'd pick under either schedule.
  {by:analyst on:2026-09-06}

## Causes
- [[pwa_avios_redeemed]] {by:analyst on:2026-09-06}
- [[pwa_cash]] {by:analyst on:2026-09-06}

## What this is
A **post-treatment mediator**, not a confounder, for the bookings question. It sits
downstream of the treatment (schedule) and upstream of Avios/cash metrics. It must **not**
be conditioned on when estimating the effect of the schedule on `pwa_bookings`: because
`member_price_sensitivity` is unobserved and causes both tier choice and (plausibly)
booking propensity, controlling for chosen tier risks opening a collider path and biasing
the treatment effect on bookings. Flagged here so nobody builds a model that stratifies on
tier chosen. {by:analyst on:2026-09-06}

`data_mode: simulated` for q-0001: `observed: true` here is a design choice — generated so
the DAG notebook can demonstrate the collider risk, not yet a confirmed fact about system
observability.
