# 08 · Advanced Experimentation

Level 2 covered the two-arm A/B test: hypothesis, primary metric, sample
size, guardrails, ship or don't. That machinery is correct and it will carry
you a long way. It also breaks in five specific situations that you will hit
within a year of running experiments seriously:

| Situation | What breaks | Covered here |
|---|---|---|
| You check results daily | The false-positive rate, badly | Peeking |
| You read 12 metrics per test | The false-positive rate, again | Multiple comparisons |
| The population is too small | Nothing is ever significant | Variance reduction, alternative designs |
| Treatment leaks between arms | Randomisation | Switchbacks, cluster assignment |
| A year of wins produces no visible movement | Your belief in the whole programme | Holdouts and meta-analysis |

The mark of an advanced practitioner is not knowing more tests. It is
knowing when the standard test is lying to you, and having a defensible
alternative ready.

## Peeking: the most common way to be confidently wrong

A fixed-horizon test assumes you look once, at the end. Every additional
look is another chance for random noise to cross the threshold. Simulating
an A/A test — two identical arms, no real effect — at 4,000 samples per arm
with a 5% significance level:

| Looks during the test | Actual false-positive rate |
|---|---|
| 1 (at the end) | 5.0% |
| 2 | 7.6% |
| 5 | 13.9% |
| 10 | 19.3% |

Check your dashboard daily for two weeks and roughly one in five *null*
experiments will show you a significant result at some point. Since the
result disappears if you keep waiting, and teams tend to stop when they see
what they wanted, the practical false-positive rate is worse than the table
suggests.

| Fix | How it works | Cost |
|---|---|---|
| **Don't look** | Pre-commit to a sample size and a date; lock the dashboard | Discipline; slow bad news |
| **Sequential testing** (mSPRT, always-valid p-values) | Continuously valid confidence bounds; stop any time legitimately | ~10–25% more samples for the same power |
| **Group sequential** (O'Brien-Fleming) | 3–4 pre-planned looks with adjusted thresholds | Requires planning the looks up front |
| **Bayesian with a decision rule** | Report P(variant better) and a loss function, stop at a threshold | Needs an agreed prior and a real decision rule, not vibes |

Any of these is fine. What is not fine is a fixed-horizon test read like a
sequential one, which is the default state of most experimentation
programmes.

## Multiple comparisons

Every metric you test is another lottery ticket:

| Metrics read at α = 0.05 | P(at least one false positive) |
|---|---|
| 1 | 5.0% |
| 3 | 14.3% |
| 5 | 22.6% |
| 12 | 46.0% |
| 20 | 64.2% |

Read a dozen metrics and it is a coin flip whether *something* looks
significant. The same applies to slicing by segment — six segments is six
comparisons.

| Approach | Use for |
|---|---|
| **One primary metric, declared before the test** | The ship decision. Everything else is secondary |
| **Bonferroni** (α / m; 0.0042 for 12 metrics) | Small numbers of genuinely co-primary metrics; conservative |
| **Benjamini-Hochberg (FDR)** | Exploratory scans across many metrics, where some false discoveries are tolerable |
| **Pre-registered segments only** | Segment analysis. Post-hoc segments generate hypotheses, never conclusions |

Say this out loud in the readout: "the effect in the agency segment was
found post-hoc and is a hypothesis for the next test, not a result." It
costs you nothing and it is the difference between an experimentation
programme and a story-generating machine.

## Variance reduction — the cheapest way to buy power

If you cannot get more users, get less noise. **CUPED** (controlled
experiment using pre-experiment data) adjusts each user's outcome by their
pre-period behaviour, removing variance that has nothing to do with the
treatment. It is unbiased and it is essentially free once implemented.

For ListUp's trial→paid test from Module 4, which needed **4,476 trials per
arm**:

| Variance reduction | Sample needed per arm | Months at 224 trials/arm/month |
|---|---|---|
| 0% (no CUPED) | 4,476 | 20.0 |
| 20% | 3,581 | 16.0 |
| 30% | 3,133 | 14.0 |
| 40% | 2,686 | 12.0 |
| 50% | 2,238 | 10.0 |

Even a 50% reduction leaves a 10-month test. That is the real lesson: **CUPED
turns an impossible test into a slow one, not into a fast one.** It works
best where the pre-period metric correlates strongly with the outcome —
which for brand-new trial users, who have no pre-period, it does not.

| Technique | Mechanism | Best for |
|---|---|---|
| CUPED | Regress out pre-period covariate | Existing users with history |
| Stratified assignment | Balance arms on tier, tenure, channel count | Small samples with known heterogeneity |
| Winsorising / capping | Trim extreme values | Revenue and usage metrics with heavy tails |
| Moving up the funnel | Test a nearer, higher-rate metric | When the ultimate metric is rare |

That last row is not a statistical trick, but it is the one that most often
rescues a test — and it comes with an obligation to verify later that the
proxy actually moved the thing you cared about.

## When randomisation itself doesn't work

| Design | Use when | How it works | Weakness |
|---|---|---|---|
| **Cluster randomisation** | Users interact within a group | Randomise the account or agency, not the user | Effective sample is the number of clusters, not users |
| **Switchback** | Treatment affects shared state (pricing, marketplace, queues) | Alternate treatment on/off across time slices for everyone | Needs many switch periods; sensitive to time-of-day effects |
| **Difference-in-differences** | Rollout is geographic or sequential | Compare change over time in treated vs untreated groups | Requires parallel pre-trends — plot them and show it |
| **Regression discontinuity** | A threshold decides who gets it | Compare just above vs just below the cut-off | Only measures the effect *at* the threshold |
| **Interrupted time series** | Everyone got it at once | Model the counterfactual from history | Weak against anything else that changed that week |
| **Matched-cohort rollout** | Small B2B populations (Module 5) | Roll out to 40 matched accounts, compare to matched non-recipients | Not causal; be explicit about that |

ListUp's repricing recommendations need cluster randomisation at the
**account** level, not the listing level, because rules apply across a
seller's whole catalogue. Randomising individual listings would leak
treatment through the seller's own behaviour and quietly overstate the
effect.

## Long-term holdouts

Short tests measure the novelty response. A **holdout** — a small population
kept on the old experience for months — measures whether any of it lasted.

| Parameter | Typical | ListUp |
|---|---|---|
| Holdout size | 1–5% of users | 3% of accounts (53 accounts) |
| Duration | 3–12 months | 6 months, refreshed annually |
| Measures | Cumulative effect of everything shipped | Trial→paid, activation, retention, ARPA |
| Cost | Those users get a worse product | Accepted; excluded from beta programmes to avoid confusion |

Holdouts are the only honest answer to "did the last year of work matter?"
They are also politically hard, because occasionally they say no.

## Worked example — ListUp's experiment programme meta-analysis

**Setup.** Over four quarters ListUp ran **34 experiments** on the
self-serve funnel. The experiment registry (built by product ops in Module
7) recorded the pre-registered hypothesis, primary metric, sample size, and
result for each.

| Outcome | Count | Share |
|---|---|---|
| Shipped — significant positive on primary metric | 11 | 32% |
| Flat / inconclusive | 16 | 47% |
| Significant negative — not shipped | 4 | 12% |
| Abandoned mid-flight (bug, traffic, scope) | 3 | 9% |

A 32% win rate is healthy. Programmes reporting 70% win rates are almost
always peeking, reading too many metrics, or only testing changes they were
going to ship anyway.

**The uncomfortable arithmetic.** The 11 shipped experiments claimed
relative lifts on trial→paid of 3.1%, 2.4%, 1.8%, 4.0%, 2.2%, 1.5%, 2.9%,
1.9%, 3.3%, 2.0% and 1.4%. Compounded, that is a **29.9%** relative
improvement, which would have taken trial→paid from 22.0% to **28.6%**.

Measured trial→paid at the end of the year: **23.4%** — a realised lift of
**6.4%**, or **21% of what was claimed**.

This gap is normal and it has four identifiable causes, each with a fix:

| Cause | Mechanism | Fix |
|---|---|---|
| **Winner's curse** | Effects that cross the significance line are, on average, overestimates — especially in underpowered tests | Shrink reported effects toward zero; power tests properly |
| **Novelty decay** | Users respond to change, then stop | Read effects at 4+ weeks, not at day 7 |
| **Non-additivity** | Two fixes to the same drop-off do not stack | Group experiments by funnel step; assume overlap within a step |
| **Population drift** | Traffic mix changed over the year | Segment the year-end number by acquisition channel before comparing |

**What ListUp changed as a result:**

1. **Report a shrunken effect.** Every shipped result is now published with
   the raw effect and a discounted expected effect, with the discount set by
   the programme's own historical realisation ratio (**0.21**, rounded to a
   0.25 planning factor). Forecasts built on experiment results use the
   discounted number.
2. **A 3% holdout**, refreshed annually, as the ground truth for cumulative
   impact — no compounding of individual claims into a portfolio number.
3. **Sequential testing by default**, so daily dashboard checks stopped
   being a statistical crime.
4. **One primary metric enforced by the registry.** A test cannot be started
   without it, and it cannot be changed after launch.
5. **A negative-results log**, circulated monthly. The four significant
   negatives were the most valuable output of the year — one of them stopped
   a redesign that would have cost a quarter.

## Governance: what an experiment must have before it starts

| Field | Rule |
|---|---|
| Hypothesis | "If we X, then Y will change by Z, because M" — mechanism required |
| Primary metric | Exactly one, from the metric dictionary |
| Secondary metrics | Listed in advance, labelled non-decisional |
| Guardrails | At least one retention and one quality metric, with breach thresholds |
| Sample size and duration | Computed, recorded, including minimum runtime of one full week |
| Segments | Pre-registered, or explicitly labelled exploratory |
| Analysis method | Fixed-horizon or sequential, decided in advance |
| Ship rule | Written before data exists, including the borderline case |
| Owner and readout date | Named person, dated |

## Exercise

1. **Audit your last ten experiments** against the governance table. Count
   how many had exactly one pre-declared primary metric and a written ship
   rule. Report the number honestly.
2. **Compute your peeking exposure.** How many times was the dashboard
   checked during your last test? Map it to the false-positive table and
   state the effective error rate you were running at.
3. **Count the metrics** read in your last readout, and compute the
   family-wise error rate. Then rewrite that readout with one primary metric
   and everything else explicitly labelled non-decisional.
4. **Estimate your CUPED headroom**: correlate your primary metric with a
   pre-period covariate, square the correlation to approximate the variance
   reduction, and recompute the sample size. Say whether it changes any
   decision.
5. **Pick one experiment that cannot be randomised at the user level** and
   design it properly — cluster, switchback or diff-in-diff — including what
   you would show to prove the design is valid (parallel pre-trends, balance
   check, number of clusters).
6. **Run the meta-analysis.** Compound the claimed lifts from everything you
   shipped in the last year, compare against the actual movement in the
   metric, and compute your realisation ratio.
7. **Propose a holdout**: size, duration, what it measures, what it costs,
   and the sentence you would use to defend it to an executive who wants
   100% of users on the new experience.
8. **Write the negative-results log** for the last year — every test that
   lost or was flat, and what each one saved you from building.
