---
id: member_booking_volume
label: Member booking volume (all logged-in member BA Holidays bookings)
observed: true
measured_at: post_treatment
graphs: [pwa-pricing]
tags: [dag]
source: interview/2026-09-07
confirmed_by: analyst
confirmed_on: 2026-09-07
---

Count of BA Holidays bookings made by logged-in members, **whether or not Avios were
redeemed**, at the grain of booking-date × departure-year-group.

The analyst confirmed in interview that all member bookings are visible, redeeming or not.
An earlier reading of `raw/pwa_exp` had this wrong. {by:analyst on:2026-09-07}

**This is the outcome q-0001 actually wants.** [[avios_redeeming_bookings]] is a subset of
it, and using the subset alone cannot tell an increase in bookings apart from members
switching into redeeming on bookings they would have made anyway.

Not observed, and deliberately not a node here: *non-member* BA Holidays bookings. Total
BA Holidays booking volume is therefore not an available outcome, and non-members are not
available as a control group. See [[pay-with-avios-ba-holidays]].

## Caused by
- [[pwa_conversion_rate_flip]] — the investment case. Proposed, not yet confirmed.
- [[seasonal_holiday_demand]] — August demand patterns move bookings regardless of policy.
  Proposed.
- [[booking_departure_lead_time]] — long-lead and near-term trips are booked at different
  rates through the year. Proposed.

## Computed from
- [[avios_redeeming_bookings]] plus non-redeeming member bookings. **Arithmetic, not
  cause.** A shift in the split between the two is a mix change and is not by itself
  evidence of incremental volume.

## Questions that turned on this
- [[q-0001]]
