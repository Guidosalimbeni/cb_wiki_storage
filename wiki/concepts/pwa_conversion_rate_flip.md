---
id: pwa_conversion_rate_flip
label: PWA conversion-rate flip (treatment)
observed: true
measured_at: treatment
graphs: [pwa-pricing]
tags: [dag]
source: raw/pwa_exp; interview/2026-09-07
confirmed_by: analyst
confirmed_on: 2026-09-07
---

Binary policy exposure at the level of a **booking**. During 1–14 August 2026 the mapping
between discount tier and Avios-to-cash conversion rate was inverted: the maximum discount
tier carried the *most* favourable rate (0.01) instead of the least (0.004). Event page:
[[2026-08-conversion-rate-flip-experiment]].

A booking is exposed if and only if it was made in the window **and** has a departure date
within 2026. There was no member-level or route-level split.

**Data mode is `simulated` for q-0001.** `observed: true` here is a design choice for the
simulation, not a verified fact about the warehouse. {q:q-0001 on:2026-09-07}

## Caused by
- [[departure_year_within_2026]] — the departure-date boundary is the entire assignment
  rule; nothing else determined exposure. {by:analyst on:2026-09-07}
- [[booking_in_flip_window]] — exposure also requires the booking to fall in 1–14 Aug 2026.
  {by:analyst on:2026-09-07}

## Causes
- [[avios_redeeming_bookings]] — a richer rate at the top of the ladder makes redeeming
  more attractive, so more member bookings are expected to involve a redemption. This is
  the business's stated rationale; proposed, not yet confirmed.
- [[member_booking_volume]] — the investment case was that better redemption terms would
  *create* bookings, not just change how existing ones are paid for. This edge is the
  whole question. Proposed, not yet confirmed.

## Questions that turned on this
- [[q-0001]] — how to estimate the effect of the flip on booking volume.
