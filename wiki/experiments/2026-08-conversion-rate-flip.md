---
id: 2026-08-conversion-rate-flip
ran: [2026-08-01, 2026-08-14]
design: none — uncontrolled policy change to the whole population
unit: booking (segmented only by departure date within/after 2026)
graph: null            # no graph drawn yet — no question has needed one
methods: []
source: raw/pwa_exp
priors: []             # DELIBERATELY EMPTY — no readout exists, see below
---

## What was tested

For the first two weeks of August 2026, the mapping between discount tier and Avios
conversion rate on [[pay-with-avios-ba-holidays]] was **flipped**: the maximum discount
tier carried the *most* favourable conversion rate (up to 0.01) and the minimum discount
tier the *least* favourable (0.004). Normally the ladder runs the other way.

The change itself is recorded as an event:
[[2026-08-conversion-rate-flip-experiment]].

## Design

**There was no A/B split.** The policy applied to all members and all routes. The only
boundary is the booking's **departure date**: it applied to bookings with a departure
within 2026, and not to bookings departing 2027 or later. {source: raw/pwa_exp}

## What it found

**Nothing yet is recorded.** No readout is in the source material.

## Why the obvious readout does not work

A DiD against the same period last year (August 2025), with the month before as the
pre-period, was attempted and is **biased**: August 2025 was heavily contaminated by a
separate change made in 2025. {source: raw/pwa_exp} That change is not named or dated in
the source — see the ingest summary.

## Priors this gives you

**None.** This page exists so that nobody treats "we ran the flip in August 2026" as
evidence about the effect of the flip. The experiment ran; it has not been read out with
a defensible counterfactual.

What is *available* rather than measured: the departure-date boundary (within-2026 vs
2027+) is the only untreated comparison group that exists in the data, and it is not
randomised — bookings with far-future departures differ from near-term ones in ways that
are plausibly related to both redemption behaviour and booking volume.

## Do not reuse this if

Do not quote any number from this window as an effect of the flip until a design has been
reviewed. Also note the visibility limit on the outcome: **non-member** BA Holidays
bookings are invisible, so *total* BA Holidays booking volume is not observable.
Corrected in interview: **all member bookings are visible**, redeeming or not — the
invisible group is non-members, not non-redeemers. {q:q-0001 on:2026-09-07}

## Questions that used it

- (none yet)
