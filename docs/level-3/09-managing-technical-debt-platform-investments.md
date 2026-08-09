# 09 · Managing Technical Debt & Platform Investments

Technical debt is the one roadmap item that has no customer, no revenue
attached, no launch, and no demo — and it will still determine whether you
can ship anything in eighteen months. Because it has no advocate outside
engineering, it gets funded the way charity gets funded: sporadically, on
goodwill, and first to be cut.

The PM's job here is not to decide how the code should be structured. It is
to make the cost of *not* fixing it legible in the same units as everything
else on the roadmap, so the trade-off is a real decision rather than a
losing argument between "customer value" and "engineering wants to
refactor". A PM who can say "this is costing us 28 engineer-weeks a year,
here is the working" has changed the conversation permanently.

This module covers a taxonomy of debt, how to measure the interest, how to
build the business case for a platform investment, and how to decide what
to leave broken on purpose.

## Not all debt is the same

The classic quadrant (Fowler) is worth internalising because it tells you
who to talk to and what to change:

| | **Prudent** | **Reckless** |
|---|---|---|
| **Deliberate** | "We ship the simple version now, and we know the cost" — legitimate, needs a written trigger for repayment | "We don't have time for design" — a management failure, not an engineering one |
| **Inadvertent** | "Now we know how it should have been built" — unavoidable and healthy | "What's layering?" — a capability gap; hiring and mentoring problem |

Only the top-left is really *debt*, in the sense of a deliberate loan with a
repayment plan. And debt is not only code:

| Type | Example at ListUp | Interest shows up as |
|---|---|---|
| **Code** | 11 marketplace adapters, each written bespoke | Every change made 11 times |
| **Architecture** | Sync pipeline assumes batch, retrofitted for real-time | New channel work takes 5 weeks not 2 |
| **Data** | Three definitions of "active account" | Wrong decisions; ops time (Module 7) |
| **Infrastructure** | Manual deploys, no staging parity | Deploy fear, weekend incidents |
| **Test** | 41% coverage on the publish path | Regressions reach production |
| **Product debt** | Four ways to set a price rule, all still supported | Support load, onboarding confusion, every new feature × 4 |
| **Process debt** | Every launch checklist reinvented | PM time (Module 7) |

**Product debt is yours outright.** Nobody else will propose removing the
second-best way of doing something, and it is often the cheapest debt in the
building to repay.

## Measuring the interest

Debt is only fundable when its cost is a number. Four measurements, all
available from data you already have:

| Measurement | How to get it | ListUp |
|---|---|---|
| **Unplanned work ratio** | Share of sprint capacity spent on incidents, hotfixes and rework | 27% |
| **Change failure rate** | Deploys causing an incident or rollback | 18% |
| **Lead time in affected areas** | Cycle time for stories touching the debt vs elsewhere | 1.8× longer |
| **Incident hours** | On-call and follow-up hours, tagged by cause | 14 incidents/quarter × 6.5h |

**Convert to money once, and reuse it forever.** ListUp's engineering team
is 9 engineers. At 46 productive weeks a year that is **414 engineer-weeks
annually**, or 103.5 per quarter. At a $175,000 fully loaded cost, one
engineer-week is **$3,804**.

| Line | Calculation | Value |
|---|---|---|
| Unplanned work | 414 × 27% | **111.8 eng-weeks/year** |
| Cost of that | 111.8 × $3,804 | **$425,250/year** |
| Sanity check | 27% × 9 × $175,000 | $425,250 ✓ |

Nobody in the company can look at $425,250 a year of unplanned work and call
debt repayment a hobby. That single number is the point of the exercise —
and the cross-check in the last row is what stops a finance director from
dismantling it in the meeting.

## Budgeting models

| Model | How it works | Best for | Fails when |
|---|---|---|---|
| **Fixed allocation** | 15–25% of every sprint, permanently | Steady-state teams | Becomes untracked slack with no visible output |
| **Debt sprints** | One full sprint per quarter | Debt needing coordinated change | Stop-the-world sprints get cancelled under pressure |
| **Boy-scout rule** | Improve whatever you touch | Small, local, code-level debt | Never addresses architecture |
| **Funded initiative** | Debt work has its own business case and roadmap slot | Large platform investments | Requires the arithmetic below |
| **Dedicated platform team** | A team whose customers are other teams | 25+ engineers | Below that scale it starves feature work |

Most organisations need two at once: a standing allocation for the small
stuff, plus funded initiatives for anything over about three engineer-weeks.
ListUp runs 20% standing plus funded initiatives above 3 weeks.

**Make the standing allocation visible.** Debt work that is invisible gets
cut first. ListUp reports it in the same weekly review as feature work, with
the interest metrics above as its outcome measures.

## Worked example — the channel adapter framework, funded properly

Module 3 computed the breakeven on ListUp's adapter framework using new
adapters only: 14 weeks fixed, 5 weeks bespoke versus 2 weeks on the
platform, breaking even on the **fifth** adapter. With only three more
channels planned this year, that calculation says **don't build it** — the
three planned adapters save 3 × (5 − 2) = 9 weeks against a 14-week
investment, a 5-week loss.

That calculation is incomplete, and it is incomplete in the direction that
kills most platform investments: it counts only the principal on future
work and ignores the **interest being paid on the 11 adapters that already
exist**.

| Cost line | Before | After | Annual saving |
|---|---|---|---|
| Adapter maintenance (11 channels) | 0.60 eng-wk/channel/quarter = 6.6/qtr | 0.25 = 2.75/qtr | **15.4 eng-weeks** |
| Adapter-caused incidents | 9/quarter × 6.5h = 1.46 eng-wk/qtr | 3/quarter = 0.49 | **3.9 eng-weeks** |
| Three new adapters | 3 × 5 = 15 weeks | 3 × 2 = 6 weeks | **9.0 eng-weeks** |
| **Total** | | | **28.3 eng-weeks/year** |

| | Value |
|---|---|
| Investment | 14 eng-weeks = **$53,261** |
| Annual return | 28.3 eng-weeks = **$107,663** |
| **Payback** | **5.9 months** |
| Year-2 return | $107,663 against zero further investment |

The proposal that gets funded is not "we should refactor the adapters". It
is: *14 engineer-weeks, paying back in 5.9 months, returning 28 weeks a year
thereafter, and here are the four measurements we will re-check at month
six.*

**Written into the proposal before approval:**

| Element | Commitment |
|---|---|
| Scope boundary | Adapter interface and shared retry/rate-limit layer only. No changes to the sync pipeline |
| Slice plan | 3 slices of ~5 weeks; 2 existing adapters migrated per slice, value from slice 1 |
| Kill criterion | If migrating the first 2 adapters takes over 7 weeks, stop and re-plan |
| Verification date | Month 6: re-measure maintenance hours, incident count, adapter build time |
| What we give up | One quarter of Growth-tier feature work, named specifically so nobody is surprised |

The kill criterion matters most. Platform projects fail by becoming
open-ended, and the only reliable defence is a pre-agreed number at which
the team stops and re-plans in public.

**At month 6, the actual:** maintenance 3.1 eng-weeks/quarter against a 2.75
target (missed slightly), incidents 4/quarter against 3, new adapter build
2.5 weeks against 2. Roughly 24 eng-weeks/year of realised saving against
28.3 forecast — **85% realisation**, payback 7.0 months. Report this. A
platform team that reports 85% is trusted with the next proposal; one that
reports 100% every time is not measuring.

## Deciding what to leave broken

Not all debt should be repaid. Route every item through this table:

| Question | If yes | If no |
|---|---|---|
| Is the code in an area we will change in the next 12 months? | Candidate | Leave it; debt in frozen code costs nothing |
| Is it causing measurable interest (incidents, unplanned work, slowdown)? | Candidate | Document it and move on |
| Is the component likely to be replaced or sunset within 18 months? | **Don't fix — plan the replacement** | Candidate |
| Can it be fixed incrementally with value at each step? | Fund it | Break it down first, or don't start |
| Would a customer notice within 6 months? | Fund it now | It can wait a quarter |

**"We're going to rewrite it anyway" is a legitimate answer** — but only if
the rewrite is on a dated roadmap. Otherwise it is how debt becomes
permanent.

## Sunsetting: the cheapest debt repayment

Removing a feature repays code debt, product debt, test debt and support
debt at the same time, and it is the intervention PMs are most uniquely able
to authorise.

| Step | Action | ListUp example: legacy CSV rule import |
|---|---|---|
| 1. Measure | Accounts using it in 90 days | 34 accounts (1.9%) |
| 2. Value | Revenue and strategic weight of those accounts | $2,700 MRR; 3 are Pro |
| 3. Cost | Maintenance, support, blocking effect | 1.2 eng-wk/quarter; blocks the new rule schema |
| 4. Migration path | What replaces it | Rule templates plus a one-time import tool |
| 5. Notice | Length and channel | 90 days, in-app + email + direct CSM outreach to the 3 Pro accounts |
| 6. Assist | Concierge migration for the top accounts | PM personally migrated 3 accounts |
| 7. Remove | Delete code, tests, docs, dashboards | 1.2 eng-wk/quarter recovered, permanently |

Removal is the only debt repayment with a negative ongoing cost. Budget for
one sunset per quarter and the code base gets smaller while the product gets
better — which almost never happens any other way.

## Talking about it with executives

| Don't say | Say |
|---|---|
| "We need to pay down tech debt" | "27% of engineering time — $425,250 a year — goes to unplanned work; here is the largest cause" |
| "The code is a mess" | "Stories in the adapter layer take 1.8× longer than elsewhere" |
| "It'll take about a quarter" | "14 engineer-weeks in three slices, value from slice one, kill criterion at 7 weeks" |
| "We'll be faster afterwards" | "28 engineer-weeks a year back, payback in 5.9 months, re-measured at month 6" |
| "Engineering is asking for this" | "This is on the roadmap because it is the cheapest capacity we can buy this year" |

## Exercise

1. **Classify your debt.** List your team's ten largest known items into the
   prudent/reckless × deliberate/inadvertent quadrant, and label the type
   (code, architecture, data, infra, test, product, process).
2. **Measure the interest.** Get four numbers: unplanned work ratio, change
   failure rate, lead-time multiplier in the affected area, and incident
   hours by cause. If any is unavailable, say what instrumentation is
   missing.
3. **Convert to money.** Compute your team's annual engineer-weeks, cost per
   engineer-week, and the annual cost of unplanned work. Cross-check it a
   second way, as above.
4. **Find your product debt.** List every feature with more than one way to
   do the same job. Count the accounts using each variant.
5. **Build one full business case**: investment in engineer-weeks and
   dollars, annual return broken into maintenance, incidents and future
   work, payback in months, slice plan, kill criterion, verification date,
   and what gets given up.
6. **Include the existing interest.** Compute your case twice — once on
   future work only, once including the interest on what already exists —
   and note whether the decision changes.
7. **Route ten items through the leave-broken table** and produce two lists:
   fund now, and deliberately not fixing (with the reason).
8. **Plan one sunset** through all seven steps, including the exact notice
   wording and who personally migrates your largest affected account.
9. **Rewrite one debt request** using the executive language table, and take
   it to the next roadmap review.
