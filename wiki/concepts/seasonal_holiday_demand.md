---
id: seasonal_holiday_demand
label: Seasonal holiday demand
observed: false
measured_at: concurrent
graphs: [pwa-pricing]
tags: [dag]
source: interview/2026-09-07
confirmed_by: null
confirmed_on: null
---

Underlying demand for holidays in the calendar period — school terms, pay cycles, weather,
competitor pricing, macro conditions. Not measured directly anywhere in our data.

Marked `observed: false` as a **proposal**, not yet an established claim: no source has
confirmed that IAGL holds no demand index. If one exists it should be recorded here,
because an unobserved common driver that hits 2026 and 2027 departures *differently* is
what breaks the parallel-trends assumption behind the departure-date comparison.

It only threatens the design if it moves the two departure-year groups differently during
1–14 Aug 2026. If it moves them together, the difference-in-differences absorbs it.

The analyst confirmed that, as far as they know, **nothing else changed** between July and
September 2026 that could move BA Holidays member bookings — no campaign, no BA Holidays
pricing or product change. This is an absence-of-evidence statement from one person, not a
verified audit, so it is recorded as a stated belief and the notebook should still test for
unexplained level shifts outside the window. {by:analyst on:2026-09-07}

## Causes
- [[member_booking_volume]] — proposed.
- [[avios_redeeming_bookings]] — proposed, via booking volume.

## Questions that turned on this
- [[q-0001]]
