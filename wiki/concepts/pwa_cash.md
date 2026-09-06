---
id: pwa_cash
label: Cash paid alongside redeemed Avios through PWA (per booking / window total)
observed: true
measured_at: post_treatment
graphs: [pwa-avios]
tags: [dag]
source: interview/q-0001 on 2026-09-06
confirmed_by: analyst
confirmed_on: 2026-09-06
---

## Caused by
- [[pwa_discount_tier_chosen]] — mechanical consequence of the chosen tier's discount %,
  same reasoning as [[pwa_avios_redeemed]]. {by:analyst on:2026-09-06}

## What this is
Not the outcome for q-0001. Recorded because the treatment touches it (see
[[2026-08-conversion-rate-flip-experiment]]); out of scope for this question's estimate.
CPA and margin computed from this and `pwa_avios_redeemed` are accounting identities, not
causal claims — see [[pay-with-avios-ba-holidays]].

`data_mode: simulated` for q-0001: `observed: true` is a design choice, unused by this
question's estimator; kept for graph completeness only.
</content>
