# 04 · Growth Product Management

Growth product management is not marketing with a Jira board, and it is not
"the team that does the signup page". It is the discipline of treating the
business as a system with measurable inputs, then systematically improving
the inputs that matter most per unit of effort.

The distinction that makes it a separate job: a core PM asks *what should we
build for this customer?* A growth PM asks *where in the system is a unit of
engineering worth the most, and how do we find out cheaply?* The two need
each other. A growth team optimising signup for a product nobody keeps using
is polishing a leaking bucket, and a core team building a beloved product
that 3% of visitors ever discover is doing charity.

This module covers the growth model, loops versus funnels, activation,
sizing an idea before you build it, and running a portfolio of bets where
most of them fail.

## Core PM vs growth PM

| | Core product | Growth product |
|---|---|---|
| **Question** | Does this solve the problem? | Does the system convert better? |
| **Unit of work** | Feature | Experiment |
| **Typical horizon** | 1–2 quarters | 1–3 weeks |
| **Success** | Retention, satisfaction, job done | Conversion rate, LTV, payback |
| **Failure is** | Expensive and slow to detect | Cheap and expected — 60–80% of tests lose or are flat |
| **Main risk** | Building the wrong thing | Local maxima; short-term wins that cost retention |

## The growth model

Write your business as one equation, then argue about the terms. Everything
downstream — roadmap, OKRs, team structure — gets easier.

For a self-serve B2B SaaS like ListUp:

```
New MRR = Visitors × (Visitor→Trial) × (Trial→Paid) × ARPA
MRR(t+1) = MRR(t) × (1 − Churn) + New MRR + Expansion MRR
```

**ListUp's current model, measured over the last 8 weeks:**

| Term | Value | Note |
|---|---|---|
| Monthly site visitors | 16,000 | Organic 61%, direct 24%, paid 15% |
| Visitor → trial | 2.80% | 448 trials/month |
| Trial → activated (2 channels connected + 1 change published, ≤7 days) | 41.1% | 184 accounts |
| Trial → paid | 22.0% | 98.6 new paying accounts/month |
| ARPA | $80.78 | Blended across tiers |
| **New MRR/month** | **$7,962** | 448 × 22.0% × $80.78 |
| Monthly logo churn | 2.66% | 47.3 accounts lost/month |
| **Net accounts/month** | **+51.2** | +2.88%/month, which compounds to **40.5%/year** |

That last line is the sanity check that makes the whole model trustworthy: a
2.88% monthly net add compounds to 40.5% annual account growth, which
matches the 41% ARR growth reported in Module 1. When your bottom-up funnel
reproduces your top-down growth rate, you can start making decisions with it.
When it doesn't, find out why before you plan anything.

## Funnels and loops

A funnel is linear: you pour in at the top and some fraction comes out. A
loop feeds its own input, so the output becomes next period's input.

| | Funnel | Loop |
|---|---|---|
| **Shape** | Visitors → trial → paid | Paid user → produces something → attracts new user |
| **Growth behaviour** | Linear in spend | Compounds, with a lag |
| **Effort to improve** | Bounded; conversion rates plateau | High up front, cheap later |
| **ListUp example** | Pricing page → trial | Agency manages 8 sellers → sellers see ListUp → some sign up direct |

| Loop type | Mechanism | Works when |
|---|---|---|
| **Viral / invitation** | Users invite collaborators | The product is multiplayer |
| **Content** | Usage produces indexable pages | Output is public and searchable |
| **Paid** | Revenue funds acquisition | Payback is shorter than your cash cycle |
| **Sales-assisted** | Customers become references | Deals are considered and social proof matters |
| **Ecosystem** | Partners bring their customers | You have a platform (Module 3) |

ListUp is single-player for the seller, so no viral loop exists. The
available loops are the **agency loop** (an agency onboards its clients) and
the **paid loop**. Naming this honestly is more useful than running an
invite experiment that has no mechanism behind it. Most products have one
real loop; pretending you have four wastes a year.

## Activation is where the leverage usually is

Activation is the moment a new user gets the value they came for. It is the
highest-leverage stage in almost every SaaS funnel because it sits between
two expensive things — acquisition you paid for and retention you need.

Finding it is an analysis, not a workshop:

| Step | Method | ListUp result |
|---|---|---|
| 1. Candidate actions | List everything a new account can do in week 1 | 14 actions |
| 2. Correlate with month-3 retention | For each action, retention of those who did it vs didn't | Connecting a **second** channel: 68% vs 24% |
| 3. Find the threshold | Where does the curve bend? | 2 channels; the 3rd adds little |
| 4. Add a time bound | When does it stop predicting? | Within 7 days |
| 5. Validate causally | Hold-out or onboarding change | Guided connect flow test, below |
| **Definition** | | **2 channels connected and 1 change published within 7 days** |

Step 5 is the one teams skip, and skipping it is why so many "aha moments"
are just descriptions of the users who were going to stick anyway. The
correlation tells you where to look. Only an experiment tells you whether
pushing people through it changes anything.

## Sizing an idea before you build it

Every growth idea should be converted to money before it is scheduled. The
arithmetic is short and it kills a lot of debate.

**Method:** re-run the growth model with one term changed, take the
difference in new MRR per month, then compound 12 monthly cohorts forward
with churn at 2.66%/month to get the MRR uplift at month 12, and multiply by
12 for ARR.

| Experiment | Term changed | ΔNew MRR/mo | ΔMRR at month 12 | ΔARR |
|---|---|---|---|---|
| Guided second-channel connect | Trial→paid 22.0% → 24.5% | $905 | $9,401 | **$112,815** |
| Pricing-page rework | Visitor→trial 2.80% → 3.20% | $1,137 | $11,819 | **$141,824** |
| Agency referral loop | Visitors 16,000 → 18,000 | $995 | $10,341 | **$124,096** |
| Onboarding upsell checklist | ARPA $80.78 → $84.98 | $414 | $4,301 | **$51,617** |
| At-risk churn playbook | Churn 2.66% → 2.40% | — | $4,539 | **$54,466** |

Then discount by your honest probability of success and divide by cost:

| Experiment | ΔARR if it works | P(success) | Eng-weeks | Expected ARR | **EV per eng-week** |
|---|---|---|---|---|---|
| Pricing-page rework | $141,824 | 30% | 3 | $42,547 | **$14,182** |
| Onboarding upsell checklist | $51,617 | 50% | 2 | $25,808 | **$12,904** |
| Guided second-channel connect | $112,815 | 45% | 4 | $50,767 | **$12,692** |
| Agency referral loop | $124,096 | 20% | 6 | $24,819 | $4,137 |
| At-risk churn playbook | $54,466 | 35% | 5 | $19,063 | $3,813 |

**Read the table carefully, because the naive reading is wrong.** By raw
ΔARR the pricing-page rework wins. By EV per engineer-week it still wins,
narrowly — but the three leaders are within 12% of each other, which is well
inside the error bars on a probability you guessed. When options are that
close, pick on a second criterion: the second-channel connect experiment
also produces information about activation that the other two don't, so it
goes first.

The referral loop ranks last on this table and may still be worth doing,
because loops compound and one-off conversion gains don't. Expected value
per week is a ranking tool for the quarter, not a philosophy.

## Worked example — ListUp's activation experiment

**Hypothesis.** New accounts that connect a second channel in week 1 retain
at 68% vs 24%. Only 41.1% get there. A guided flow that asks for the second
channel during setup — instead of leaving it to a dashboard tile — will
raise trial→paid from 22.0% to 24.5%.

**Design.** 50/50 split at trial signup. Primary metric: trial→paid within
14 days of trial start. Secondary: activation rate, time to second channel.
Guardrails: day-30 retention of paying accounts, support tickets per new
account.

**Sample size.** Detecting 22.0% → 24.5% (a 2.5-point absolute lift, 11.4%
relative) at 80% power and 95% confidence needs roughly 4,500 trials per
arm. A 50/50 split gives 224 trials per arm per month, so that is
**20 months** — the experiment is not runnable as designed.

This is the single most common growth-team collision with reality, and there
are only four honest responses:

| Option | Effect | Chosen? |
|---|---|---|
| Accept a bigger MDE | Test for +5pts instead; ~1,160/arm, ~5.2 months | No — a 5pt lift is implausible |
| Move up the funnel | Use **activation** as the primary metric: 41.1% → 50%, ~490/arm, ~2.2 months | **Yes** |
| Lower confidence to 90%, power to 80% | Cuts sample ~20%; raises false-positive risk | Partially |
| Ship it on judgement, monitor | No causal read, fast | No |

**Decision:** run on activation as the primary metric with trial→paid as a
directional secondary, and pre-register that a positive activation result
plus a non-negative trial→paid trend ships. Write that rule down *before*
the data arrives, because the temptation to reinterpret a borderline
secondary metric is enormous.

**Result after 10 weeks** (515 and 508 trials per arm):

| Metric | Control | Variant | Read |
|---|---|---|---|
| Activation (2 channels + 1 publish ≤7 days) | 41.2% | 49.6% | +8.4pts, significant |
| Median time to 2nd channel | 4d 6h | 1d 2h | Strong supporting signal |
| Trial→paid (14 days) | 21.9% | 23.8% | +1.9pts, **not** significant — directionally right |
| Day-30 retention of new payers | 91.4% | 92.0% | Guardrail held |
| Support tickets per new account | 0.31 | 0.29 | Guardrail held |

**Shipped**, per the pre-registered rule. The important discipline is what
came next: trial→paid was tracked as a monitored metric for two further
quarters. It settled at 23.4%, below the 24.5% assumption, so the modelled
$112,815 was revised down to about **$86,000**. Going back and correcting
your own forecast — out loud — is what makes the next forecast believed.

## Traps

| Trap | Symptom | Fix |
|---|---|---|
| Optimising a leaky bucket | Conversion up, retention flat, revenue flat | Fix retention before acquisition; churn compounds against you |
| Local maxima | Twelve wins, no change in the growth curve | Reserve 20% of capacity for structurally different bets |
| Dark patterns | Signup up, day-30 retention down | Make a retention guardrail mandatory on every growth test |
| Vanity loops | An invite feature with no multiplayer use case | Name your one real loop and invest there |
| Underpowered tests everywhere | Everything is "trending positive" | Compute sample size first; if it's not runnable, change the metric |
| Growth team owns growth | Core team feels unaccountable for retention | Growth owns the system; every team owns its own retention |

## Exercise

Build the growth model for a product you know, then plan a quarter from it.

1. **Write the growth equation** with your product's actual terms, and fill
   in every number from data — not estimates. Include churn and expansion.
2. **Reconcile it.** Compound your monthly net add over 12 months and check
   it matches your reported annual growth. If it doesn't, find the
   discrepancy before going further; that is the most valuable hour in this
   exercise.
3. **Identify your activation moment** with the five-step method. Report the
   retention split for your top candidate action, the threshold, and the
   time bound — and state honestly whether it has ever been validated
   causally.
4. **Name your one real loop**, and one loop people talk about that your
   product does not actually have.
5. **Size five ideas.** For each, change one term, compute ΔNew MRR/month,
   compound 12 cohorts with your churn rate, and report ΔARR.
6. **Rank by expected value per engineer-week**, with your honest
   probability of success. Then say which ranking you would override, and
   why.
7. **Sample-size your top experiment.** If it is not runnable in under a
   quarter, pick one of the four responses and justify it in writing.
8. **Write the pre-registered ship rule** before you run anything: which
   metric, which threshold, which guardrails, and what happens on a
   borderline result.
9. **Schedule the forecast correction.** Put a date 6 months out to compare
   your modelled ΔARR against what actually happened, and commit to sharing
   the difference.
