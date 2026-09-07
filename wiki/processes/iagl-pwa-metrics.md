# IAGL Pay-with-Avios metric definitions

Definitions exactly as given by the analyst. Source: `raw/pwa_exp`, recorded_by: analyst,
recorded_on: 2026-09-07.

These are **arithmetic identities**, not causal statements. If any of these quantities
becomes a node in a graph, the relationship between it and its inputs belongs under
`## Computed from`, never `## Caused by`.

## Cost per Avios (CPA)

    cost_per_avios = sum(cash in window) / sum(avios in window)

Typical observed level: **around 0.005**. {source: raw/pwa_exp}

Note the window dependence: CPA is a ratio of two sums over a chosen period, not a
per-booking average. Changing the window changes the number.

## IAGL margin

    iagl_margin = sum(avios redeemed in period) * 0.00659 - sum(cash in period)

0.00659 is the internal value placed on one Avios. Because CPA is usually ~0.005 against
a 0.00659 valuation, the marginal margin per redemption is small.

## Combined IAGL + BA Holidays margin

BA Holidays is part of IAGL and takes **10% of the ticket price** as its own margin. The
August 2026 experiment was justified on a *combined* margin basis:

    combined_margin = iagl_margin + 0.10 * sum(ticket price in period)

This combined formula is the one the experiment's business case rested on. It is recorded
here as the definition used; whether it was the right basis is a question, not a fact.

## Volume metrics

- **Bookings made using the product** — bookings where Avios were redeemed. Bookings made
  without Avios, and all non-member bookings, are not visible; see
  [[pay-with-avios-ba-holidays]].
- **Avios redeemed** and **cash** — the two components of every metric above.
