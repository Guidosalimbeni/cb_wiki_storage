---
id: booking_in_flip_window
label: Booking made during 1–14 August 2026
observed: true
measured_at: pre_treatment
graphs: [pwa-pricing]
tags: [dag]
source: raw/pwa_exp
confirmed_by: analyst
confirmed_on: 2026-09-07
---

Whether the booking date falls inside the two-week flip window. Together with
[[departure_year_within_2026]] it fully determines [[pwa_conversion_rate_flip]].

Open point: the source does not say whether the flip was **announced** to members. If it
was, bookings could have been delayed into the window or rushed before it ended, which
would show as a dip immediately before 1 August and a spike immediately after 14 August.
That is testable in the notebook without asking anyone.

## Causes
- [[pwa_conversion_rate_flip]] {by:analyst on:2026-09-07}

## Questions that turned on this
- [[q-0001]]
