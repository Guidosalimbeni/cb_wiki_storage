---
id: avios_balance
label: Member's Avios balance at time of booking
observed: true
measured_at: pre_treatment
graphs: [pwa-pricing]
tags: [dag]
source: interview/2026-09-07
confirmed_by: null
confirmed_on: null
---

How many Avios the member holds when booking. A member cannot redeem what they do not
hold, so this gates whether the flip could affect them at all — and it is a natural
subgroup for a heterogeneous-effect check.

`observed: true` is assumed from the fact that IAGL runs the currency; **not yet confirmed
by the analyst**, and under q-0001 the data is simulated in any case.

## Causes
- [[avios_redeeming_bookings]] — proposed.

## Caused by
- [[booking_departure_lead_time]] — proposed, weak.

## Questions that turned on this
- [[q-0001]]
