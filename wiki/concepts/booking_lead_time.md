---
id: booking_lead_time
label: Booking lead time (days between booking and departure)
observed: true
measured_at: pre_treatment
graphs: [pwa-avios]
tags: [dag]
source: interview/q-0001 on 2026-09-06
confirmed_by: analyst
confirmed_on: 2026-09-06
---

## Causes
- [[pwa_discount_tier_conversion_rate]] — during the Aug 2026 window, whether a booking's
  departure falls in 2026 or 2027+ is a deterministic threshold function of lead time
  (departure date minus booking date, booking date fixed within the window). This is the
  assignment mechanism for the treatment, not a free choice. {by:analyst on:2026-09-06}
- [[pwa_bookings]] — a direct (non-treatment) path: bookings with far-out (2027+) departure
  dates and bookings with near-term (2026) departure dates may differ systematically in
  urgency, trip type or seasonality, independent of which conversion-rate schedule applied.
  This is the confound an RDD-style design at the cutoff is meant to neutralise, not one we
  can assume away. {by:analyst on:2026-09-06}

## What this is
Continuous running variable: departure_date − booking_date, for bookings made in the
Aug 2026 flip window. The departure-year cutoff (2026 vs 2027+) used in the experiment
record is the coarse, binary version of this; here it is kept continuous because that is
what makes a regression-discontinuity design possible around 2027-01-01.

Analyst confirmed a member's departure date is fixed before booking and is not
manipulated in response to the treatment — i.e. this variable is exogenous *to the
treatment assignment*. It is not thereby assumed exogenous to the *outcome*: whether
booking propensity is continuous across the year-boundary is the RDD's continuity
assumption, and needs checking against data, not asserted from an interview.
{by:analyst on:2026-09-06}
</content>
