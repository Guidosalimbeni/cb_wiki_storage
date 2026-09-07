---
id: avios_redeeming_bookings
label: Member bookings that redeemed Avios
observed: true
measured_at: post_treatment
graphs: [pwa-pricing]
tags: [dag]
source: raw/pwa_exp; interview/2026-09-07
confirmed_by: analyst
confirmed_on: 2026-09-07
---

Count of member bookings on which Avios were redeemed. A **strict subset** of
[[member_booking_volume]].

This is the metric the business calls "bookings made using the product". It is the one
most likely to move under the flip, and the one most likely to make the experiment look
successful without any incremental holiday being sold — because a better rate gives
members who were booking anyway a reason to pay with Avios.

## Caused by
- [[pwa_conversion_rate_flip]] — a better rate at the top of the ladder makes redeeming
  more attractive. Proposed, not yet confirmed.
- [[member_booking_volume]] — more bookings mechanically give more opportunities to
  redeem. Proposed.
- [[avios_balance]] — a member cannot redeem what they do not hold. Proposed.

## Questions that turned on this
- [[q-0001]]
