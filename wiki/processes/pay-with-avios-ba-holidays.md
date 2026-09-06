---
id: pay-with-avios-ba-holidays
system: IAGL / BA Holidays
source: raw/iagl_pwa
recorded_by: analyst
recorded_on: 2026-09-06
---

## What this is
IAG Loyalty (IAGL) is the company behind the Avios loyalty currency. "Pay with Avios"
(PWA) for BA Holidays is one redemption product: a member booking a BA Holidays package
can redeem some of their Avios for a discount on the holiday ticket.

## How it works
At booking, a member is presented with **up to 9 discount options**. Each option is:
- a **discount**, expressed as a percentage off the ticket price, and
- a **conversion rate** between cash and Avios specific to that discount tier.

The tiers trade off against each other: a higher discount tier usually comes with a more
penalised (worse) conversion rate. Conversion rate ranges from **0.01** (most favourable
to the member) down to **0.004** (least favourable). Source: raw/iagl_pwa {q:ingest
on:2026-09-06}.

## Key metrics
- **Bookings** — number of bookings made using the PWA product.
- **Avios redeemed** — total Avios spent through the product in a window.
- **Cash** — total cash paid alongside the redeemed Avios in a window.
- **Cost per Avios (CPA)** — `sum(cash in window) / sum(avios redeemed in window)`.
  Usually around **0.005**. This is a ratio of two aggregates, not a per-booking figure.

## Margin (arithmetic, not causal)
Stated formula, as given: for IAGL alone,
`margin = sum(avios redeemed in period) × 0.00659 − sum(cash in period)`.

The `0.00659` figure is described as a backing/liability rate for Avios distinct from the
CPA the member actually gets (0.004–0.01) — the spread between what a member "pays" in
Avios-to-cash terms and what IAGL books as the redemption cost is where margin comes
from. **This is an accounting identity, not a causal claim** — it belongs in a
`## Computed from` block if/when `pwa_margin` becomes a concept, never in `## Caused by`.

BA Holidays is now part of IAGL, and BA Holidays separately earns ~10% of ticket price as
its own margin on the same booking. A combined "IAGL + BA Holidays" margin view was used
to justify the August 2026 experiment (see below) — this combined formula is asserted in
the source material but not spelled out arithmetically; flagged as **not fully
classified**, see summary.

## What is NOT observed
Booking volume for BA Holidays **independent of Avios usage** is not visible to IAGL —
i.e. non-member bookings are hidden. IAGL can see all logged-in member activity (search
and booking, whether or not they used PWA) but not bookings made by non-members. This is
an important observability boundary for any question comparing PWA vs non-PWA or member
vs non-member booking behaviour: **total market/booking volume is unobserved**, only the
member-visible slice is. Source: raw/iagl_pwa {q:ingest on:2026-09-06}.

## Dateable changes affecting this process
- [[2026-08-conversion-rate-flip-experiment]] — a policy change flipping which discount
  tier got the favourable conversion rate, run for two weeks in August 2026.

## Related experiment material
- [[2026-08-avios-conversion-flip]] — the experiment record and its assessment
  challenges (no control group, contaminated DiD counterfactual).
