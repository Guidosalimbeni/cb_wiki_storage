---
id: departure_year_within_2026
label: Departure date falls within 2026
observed: true
measured_at: pre_treatment
graphs: [pwa-pricing]
tags: [dag]
source: raw/pwa_exp; interview/2026-09-07
confirmed_by: analyst
confirmed_on: 2026-09-07
---

Whether the booking's **departure date** is inside 2026 (treated) or 2027 or later
(untreated). Fixed at the moment of booking, so it is measured before treatment applies.

This is the **assignment mechanism**. It is not randomised, and it is the only boundary
that exists in the data.

The analyst confirmed there is no meaningful **pull-forward**: members did not move
departure dates into 2026 to chase the better rate, because by August a 2027 departure is
a different kind of trip (long-haul, planned, school holidays) with almost no overlap with
near-term 2026 bookings. {by:analyst on:2026-09-07}

That confirmation does two opposite things, and both matter:

- **Good:** no edge runs from [[pwa_conversion_rate_flip]] back into this node, so the
  2027+ group is genuinely untreated and is not depleted by the treatment.
- **Bad:** "a different kind of trip" is the parallel-trends threat. The two groups differ
  systematically, so their booking volumes need not move together in the absence of the
  flip. See [[booking_departure_lead_time]].

## Causes
- [[pwa_conversion_rate_flip]] — determines exposure. {by:analyst on:2026-09-07}
- [[booking_departure_lead_time]] — arithmetically and behaviourally, a 2027 departure
  booked in August 2026 is a long-lead trip. {by:analyst on:2026-09-07}

## Questions that turned on this
- [[q-0001]]
