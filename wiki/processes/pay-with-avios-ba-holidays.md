# Pay with Avios — BA Holidays

How the product works, as described by the analyst. Facts only; causal claims found in
the source are quarantined at the bottom of this page as attributed prose.

Source: `raw/pwa_exp` (same text previously ingested as `raw/iagl_pwa`),
recorded_by: analyst, recorded_on: 2026-09-07.

## The company and the product

IAG Loyalty (IAGL) is the company behind the **Avios** loyalty currency. One of its
products is **Pay with Avios (PWA) for BA Holidays**: when a member is booking a holiday
they can redeem some of their Avios for a discount on the holiday ticket.

BA Holidays is now part of IAGL. BA Holidays' own margin on a booking is **10% of the
ticket price**. {source: raw/pwa_exp}

## The discount ladder

At booking the member is presented with **up to 9 discount options**. Each option is:

- a **percentage of the ticket price** taken as discount, and
- an **Avios-to-cash conversion rate** attached to that discount tier.

The conversion rate ranges from **0.01** (most favourable to the member — each Avios buys
more discount) down to **0.004** (least favourable).

Under normal policy the ladder is **penalising**: the higher the discount tier, the worse
the conversion rate. That mapping was inverted for two weeks in August 2026 — see
[[2026-08-conversion-rate-flip-experiment]].

## Key business metrics

Defined on the source's own words; see [[iagl-pwa-metrics]] for the formulas.

- Number of bookings made using the product
- Avios redeemed
- Cash (cash paid on the booking)
- Cost per Avios = sum of cash in the window ÷ sum of Avios in the window

## What is and is not observable

**This is the central data limitation of the product.**

- Visible: all *logged-in member* activity — searches and **all member bookings, whether
  or not Avios were redeemed**. Avios-redeeming bookings are a strict subset of visible
  member bookings. Confirmed by the analyst in interview. {q:q-0001 on:2026-09-07}
- **Not visible: non-member BA Holidays bookings.** These are hidden from IAGL.
  {source: raw/pwa_exp}

Correction: an earlier reading of `raw/pwa_exp` implied that only Avios-redeeming
bookings were countable. That was wrong. The invisible group is **non-members**, not
non-redeemers. {q:q-0001 on:2026-09-07}

Consequences:

- The denominator "all BA Holidays bookings" still does not exist in our data, so any
  metric phrased as a share of *total* BA Holidays bookings is not computable as stated,
  and non-member bookings are unavailable as a control group.
- But **member booking volume is an observable outcome**, and it can be decomposed into
  redeeming and non-redeeming bookings. This is what lets a genuine increase in bookings
  be told apart from members merely switching into redeeming on bookings they would have
  made anyway. That distinction is the crux of q-0001.

## Causal claims made in the source (attributed, not edges)

These are the business's model of the product. They are **not** drawn in
`wiki/concepts/` — edges are only drawn in an interview where the analyst confirms them.

- The August 2026 experiment rationale argued that a **more attractive conversion rate on
  the high-discount tiers would drive more bookings**, and that the extra volume — counted
  against the *combined* IAGL + BA Holidays margin — would keep overall margin high
  despite a higher short-run redemption cost. {source: raw/pwa_exp}
- The source describes marginal margin as "usually very small", because cost per Avios
  typically sits around **0.005** against an Avios value of 0.00659. {source: raw/pwa_exp}
