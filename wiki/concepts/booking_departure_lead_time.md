---
id: booking_departure_lead_time
label: Lead time between booking date and departure date
observed: true
measured_at: pre_treatment
graphs: [pwa-pricing]
tags: [dag]
source: interview/2026-09-07
confirmed_by: analyst
confirmed_on: 2026-09-07
---

Days between when the booking was made and when the trip departs.

This node exists because of one thing the analyst said: bookings departing in 2027+ are
"a different kind of trip — long-haul, planned, school holidays". Lead time is the
variable that difference runs through, and it sits **upstream of both the assignment
variable and the outcome**, which makes it the main threat to the departure-date
comparison.

It is not a confounder in the classic sense — nothing about lead time caused the *policy*
to be flipped. But it makes the treated and untreated groups structurally different, so
their booking volumes need not trend together. That is the parallel-trends assumption, and
it is the assumption the design will live or die on.

## Caused by
- [[departure_year_within_2026]] — a 2027 departure booked in Aug 2026 is by construction
  a long-lead booking. {by:analyst on:2026-09-07}

## Causes
- [[member_booking_volume]] — long-lead and near-term trips fill up on different seasonal
  rhythms. Proposed.
- [[avios_balance]] — plausibly, members planning far ahead have accumulated differently.
  Proposed, weak.

## Questions that turned on this
- [[q-0001]]
