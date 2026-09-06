---
id: pwa_discount_tier_conversion_rate
label: PWA discount-tier -> conversion-rate schedule (flipped vs normal)
observed: true
measured_at: pre_treatment
graphs: [pwa-avios]
tags: [dag]
source: interview/q-0001 on 2026-09-06, wiki/events/2026-08-conversion-rate-flip-experiment.md
confirmed_by: analyst
confirmed_on: 2026-09-06
---

## Caused by
- [[booking_lead_time]] — for bookings made 2026-08-01 to 2026-08-14, the flipped schedule
  applies iff departure date falls within 2026 (lead time short of the 2027-01-01
  threshold); the normal schedule applies otherwise. Deterministic policy rule, not a
  member choice, not randomised. {by:analyst on:2026-09-06}

## Causes
- [[pwa_bookings]] — the richer terms at the top discount tier under the flipped schedule
  are the hypothesised direct driver of any change in booking volume. {by:analyst on:2026-09-06}
- [[pwa_discount_tier_chosen]] — flipping which tier carries the best conversion rate
  changes which tier is attractive to a member choosing among the 9, so schedule shapes the
  choice a member then makes. {by:analyst on:2026-09-06}

## What this is
The treatment for q-0001. Binary/categorical: `flipped` (max discount tier gets best
conversion rate) vs `normal` (max discount tier gets worst conversion rate), in effect for
a fixed two-week calendar window and gated only by whether the booking's departure date is
in 2026 or 2027+. See [[2026-08-conversion-rate-flip-experiment]] for the full policy
description. Population for q-0001 is restricted to this window — no before/after or
other-window comparison is in scope, per analyst.

`data_mode: simulated` for q-0001: `observed: true` here is a design choice for the DAG
notebook, generated as a deterministic function of `booking_lead_time` — not yet a
confirmed fact about system observability.
