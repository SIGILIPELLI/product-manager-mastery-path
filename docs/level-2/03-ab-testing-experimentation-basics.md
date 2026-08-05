# 03 · A/B Testing & Experimentation Basics

Most product decisions are made from a mix of judgement and after-the-fact
dashboards, which means you rarely learn whether the change caused the
result. An A/B test is the one tool that gives you causality: two groups
identical in every respect except the change, so any difference between them
is the change. As a PM you don't need to derive the statistics, but you do
need to size a test before it runs, refuse to read it early, and tell the
difference between "we won" and "we can't tell" — because most of the damage
done by experimentation programs comes from PMs shipping noise.

This module covers hypothesis writing, metric selection, sample sizing,
reading a result honestly, and the specific situations where you should not
A/B test at all.

## Writing a testable hypothesis

An untestable hypothesis is the single most common reason an experiment
produces an unusable result. Use this shape:

> **Because** [evidence], **we believe that** [change] **for** [audience]
> **will cause** [metric] **to move from X to Y**. **We'll know we're right
> when** [primary metric moves ≥ MDE] **and** [guardrails hold].

| Weak | Rewritten |
|---|---|
| "New pricing page will convert better" | Because 61% of pricing-page sessions end without scrolling past the fold (analytics, Q2), we believe adding a plan-comparison table above the fold for first-time visitors will raise visitor→trial from 4.0% to 5.0%. We'll know when the primary metric clears +25% relative and trial→paid does not fall below 20%. |
| "Users will like the new onboarding" | Because 41% of new accounts abandon at the API-key step (funnel, n=1,180), we believe replacing the key field with guided screenshots will raise step completion from 59% to 70%, without raising support tickets per new account. |

## Choosing metrics before you run

Every experiment needs exactly one primary metric, a small number of
secondary metrics, and guardrails you have committed to *in advance*.

| Metric type | How many | Purpose | Rule |
|---|---|---|---|
| **Primary** | Exactly 1 | The decision metric — ship/no-ship hangs on it | Chosen before launch; never swapped afterward |
| **Secondary** | 2–4 | Explain *why* the primary moved | Directional only; never promote one to primary post hoc |
| **Guardrail** | 2–5 | Things you refuse to break | Pre-set thresholds; a breach blocks ship even on a win |
| **Diagnostic** | Any | Sanity: sample ratio, latency, error rate | Checked day 1, not at the end |

Good guardrails for a conversion test: downstream trial→paid rate, refund
or cancellation rate, support tickets per 100 new accounts, page latency
p95. The purpose of a guardrail is to catch the win you bought by moving
harm somewhere you weren't looking.

## Sizing the test

Four inputs determine how long a test must run. Decide all four before you
start, because after the fact they become excuses.

| Input | Meaning | Typical | Effect on sample size |
|---|---|---|---|
| Baseline rate (p) | Current conversion | measured | Lower baseline → more traffic needed |
| **MDE** | Minimum detectable effect — the smallest lift worth shipping | 5–25% relative | Halving the MDE roughly **quadruples** the sample |
| Significance (α) | Tolerance for false positives | 0.05 | Tighter → larger sample |
| Power (1−β) | Chance of detecting a real effect | 0.80 | Higher → larger sample |

A usable approximation for a two-sided test at α = 0.05 and 80% power:

> **n per arm ≈ 16 × p × (1 − p) ÷ (absolute lift)²**

At a 12% baseline and a 2-point absolute lift, that's
16 × 0.12 × 0.88 ÷ 0.02² = **4,224 per arm** (the exact two-proportion
formula gives 4,437 — close enough to plan with).

The quadratic term is the thing to internalize:

| Baseline | Target | Relative lift | n per arm | Total |
|---|---|---|---|---|
| 12% | 15% | +25% | 2,036 | 4,071 |
| 12% | 14% | +16.7% | 4,437 | 8,875 |
| 12% | 13.2% | +10% | 12,004 | 24,007 |
| 12% | 12.6% | +5% | 47,036 | 94,072 |

**Divide the total by weekly eligible traffic to get the runtime, and round
up to whole weeks** so every day of the week is represented equally.
Anything past 4–6 weeks is a planning problem, not a statistics problem:
cookie churn, seasonality, and competing releases will contaminate it.

## Reading the result

| You see | It means | Do |
|---|---|---|
| p < 0.05, CI excludes 0, guardrails fine | Real effect at your chosen tolerance | Ship |
| p > 0.05, CI is *narrow* around 0 | Confidently no meaningful difference | Don't ship; ship the cheaper variant |
| p > 0.05, CI is *wide* | Underpowered — you learned nothing | Extend or abandon; do not call it "flat" |
| Primary wins, guardrail breached | You moved the harm, not removed it | Do not ship. Investigate |
| Primary flat, a secondary "wins" | Almost certainly multiple comparisons | Treat as a hypothesis for the next test |

Always report the **confidence interval**, not just the p-value. "+23.5%
relative, 95% CI [+6%, +41%]" tells a stakeholder both that it worked and
how much you actually know. "p = 0.0085" tells them neither.

## Five ways experiments go wrong

| Trap | What happens | Fix |
|---|---|---|
| **Peeking** | Checking daily and stopping at the first significant reading. With 5 looks the false-positive rate is 22.6%; with 20 looks it's 64.2% | Fix the end date up front, or use a sequential-testing tool built for peeking |
| **Sample ratio mismatch** | Split is 52/48 instead of 50/50 — the assignment or logging is broken | Check on day 1; a failed SRM check invalidates the test |
| **Novelty / primacy effects** | Existing users react to *change*, not quality; effect decays | Run ≥2 weeks; segment new vs returning users |
| **Metric swap** | Primary was flat, so a secondary becomes the headline | Write the primary in the doc before launch and never edit it |
| **Underpowered "flat" result** | An inconclusive test is reported as "no difference" and the idea is killed | Report the CI; state the MDE the test could actually detect |

## When *not* to A/B test

| Situation | Why testing fails | Do instead |
|---|---|---|
| Too little traffic for the MDE | You'd need a year | Qualitative testing, before/after with a holdout, painted-door test |
| Big strategic bets | No variant exists; it's a direction, not a button | Assumption tests (Module 1), staged rollout, beta cohort |
| Legal, security, or accessibility fixes | Not optional regardless of result | Just ship it |
| Rare events (enterprise deals, annual renewals) | Sample accrues too slowly | Cohort comparison, qualitative win/loss |
| The change is obviously right and cheap | Test cost exceeds the information value | Ship, monitor guardrails |

## Worked example — ListUp pricing page

**Context:** ListUp's pricing page gets ~3,000 unique visitors a week.
Baseline visitor→trial-start is 4.0%. Discovery (Module 1) found anxiety —
not attraction — is the blocker: sellers can't tell which plan covers their
marketplaces without opening a second tab.

**Hypothesis:** Because 4 of 6 switch interviews cited uncertainty about
marketplace coverage, we believe a plan-comparison table above the fold with
per-marketplace coverage will raise visitor→trial from 4.0% to 5.0% (+25%
relative). Guardrails: trial→paid stays ≥ 20%; page p95 latency stays under
1.2s.

**Sizing:** at p = 0.04, MDE = +1 point absolute, α = 0.05, 80% power →
**6,745 per arm, 13,490 total**. At 3,000 visitors/week that is 4.5 weeks,
rounded up to **5 whole weeks**.

**Result after 5 weeks:**

| Arm | Visitors | Trials | Rate |
|---|---|---|---|
| Control | 6,750 | 268 | 3.97% |
| Variant | 6,750 | 331 | 4.90% |

**Analysis:** absolute lift +0.93 points, relative **+23.5%**, z = 2.63,
**p = 0.0085**. 95% CI on the absolute lift: **[+0.24, +1.63] points**, i.e.
**[+6%, +41%] relative**. Guardrails: trial→paid 22.1% (control) vs 21.4%
(variant) — inside tolerance; p95 latency unchanged.

**Decision: ship.** But read the interval before you promise anything: the
point estimate is +23.5%, and the honest forecast range is +6% to +41%.
Committing next quarter's revenue plan to the +23.5% figure is how a
successful experiment turns into a missed target. Report the low end to
finance and the point estimate to the team.

**The counterfactual worth noting:** had ListUp set the MDE at +10% relative
instead of +25%, the same test would have required 24,007 visitors — eight
weeks — and would have run into the seasonal Q4 traffic spike. The MDE
wasn't a statistical choice; it was a scheduling one.

## Exercise

Design a complete experiment for your own product:

1. **A hypothesis** in the *Because… we believe… will cause… we'll know
   when…* form, citing a real number from your analytics or research.
2. **A metrics table**: one primary, 2–4 secondary, and at least three
   guardrails with explicit numeric thresholds that would block a ship.
3. **A sizing calculation**: baseline, MDE, α, power → sample per arm →
   runtime in whole weeks at your real traffic. If the runtime exceeds six
   weeks, state which input you'd change and what you give up by changing
   it.
4. **A pre-registered decision rule**: write, before running, exactly what
   result leads to ship, iterate, or kill. Include what you'll do if the
   result is inconclusive.
5. **A "don't test this" list**: three decisions on your current roadmap
   that should *not* be A/B tested, and the alternative evidence you'd
   gather for each.
