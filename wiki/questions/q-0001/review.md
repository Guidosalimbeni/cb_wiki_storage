# Review — q-0001

Reviewer agent, independent of the interview conversation. Recorded 2026-09-07.
Transcribed here by the orchestrator because the agent's own write did not land; the
verdict and requirements below are the reviewer's words.

## Verdict (verbatim)

**IDENTIFIED UNDER STATED ASSUMPTIONS — and the assumption doing all the work is not one
this graph can support.**

Adjustment cannot identify this effect: the only backdoor path runs through
`departure_year_within_2026`, which *is* the assignment rule, so conditioning on it
destroys all treatment variation — positivity fails exactly where the confounding lives.
`booking_departure_lead_time` must be excluded from every adjustment set for the same
reason. DiD is therefore the right family, but parallel trends is a restriction on trends,
not on edges, so this DAG can neither bless nor refuse it; it must be earned empirically,
and one month of pre-period does not earn it. The design becomes defensible on a
log/Poisson scale, with departure-month cohorts and synthetic-control weights instead of a
lumped 2027+ group, ≥18 months of pre-period, a placebo battery reported before the
headline, and a difference-in-discontinuity at 31 Dec 2026 as the comparability check. A
stated MDE comes first and may kill it: one treated cluster over 14 days plausibly cannot
detect less than a 10–20% lift. `data_mode: simulated`, so **no number from this question
says anything about IAGL** — it can only show the code runs, that the estimator recovers a
planted effect, and what the design could detect. `avios_balance` is UNVERIFIED against
live systems; the triple-difference control is conditional on confirming it at booking
grain before any live run.

## Power is the first question, not the last

If the flip produced a 5% lift, this design cannot see it, and a null from it must never be
reported as "no effect". The record does not state an MDE. That is a finding, and it
belongs in the first cell of the notebook, not the last. It is also the one place where a
single company input transforms the exercise: daily or weekly member booking counts and
their volatility, by departure-year group, for calibration. Everything else can stay
simulated.

## `avios_balance`: UNVERIFIED, and the triple difference is conditional on it

Because `data_mode` is `simulated`, the `observed:` flags in `wiki/concepts/` are **design
choices for the simulation, not facts about IAGL's systems**. `avios_balance` is therefore
**UNVERIFIED against live systems**. The triple-difference design (members who *can*
respond, because they hold enough Avios, versus members who *cannot*) may be built and
exercised in simulation, but it **must not be run on live data until `avios_balance`
availability at booking grain is confirmed**, including whether it is available as-of-booking
rather than as a current snapshot. A current-snapshot balance is post-treatment and would
put a post-treatment variable into the design. If confirmation fails, drop the triple
difference rather than substitute a snapshot.

## Requirements before this is a design rather than a sketch

1. **MDE stated**, computed from calibrated counts, with permutation inference specified.
2. **Pre-period extended to ≥18 months**; the July-only pre-period abandoned.
3. **Log/Poisson scale declared**; the level DiD dropped.
4. **Departure-month cohorts as the panel**, with synthetic-control weights over the donor
   pool and pre-fit quality reported.
5. **Diff-in-discontinuity at 31 Dec 2026** as the comparability check, with the July and
   prior-year jump differenced out.
6. **Placebo battery run and reported before the headline estimate**: placebo windows,
   placebo outcome if one exists, lead coefficients, leave-one-cohort-out.
7. **`booking_departure_lead_time` explicitly excluded** from every adjustment set, with
   the reason recorded on the node page.
8. **A banner on every artefact** stating `data_mode: simulated` and that no number bears
   on IAGL; `dag_tested: no` stays on the record until the DAG notebook has actually run.
9. **`avios_balance` verified before any live run**, or the triple difference dropped.

Requirements 3, 7 and 8 are free. Requirement 1 is the one that decides whether the rest is
worth doing.

## Strongest argument against my own verdict (verbatim)

I may be too strict on parallel trends and too impressed by my own placebo list. The
treated group here is almost certainly the large majority of member bookings, and the flip
was a genuine, sizeable change in terms — if it created bookings at all it plausibly created
them by a lot, not by 5%, in which case a 15% MDE is adequate and the whole power objection
dissolves. The analyst's "different kind of trip with almost no overlap" also cuts in my
disfavour: two nearly independent markets are *less* likely to share a common shock that
must then be assumed away, and a proportional-trends DiD on log counts absorbs most of what
seasonality does to a thin, flat 2027 series. And it is possible I am over-engineering a
simulated exercise whose stated purpose is only to check that the estimator recovers a
planted effect — a plain two-group log DiD with an event study does that perfectly well. The
answer to that is narrow but decisive: a design built in simulation is the design that gets
run on live data the moment an extract appears, and pre-period length, scale, the cohort
panel and the MDE are all far cheaper to fix now than after someone has quoted a number.
