# 07 · Product Ops Basics

Somewhere between three product managers and fifteen, a company stops being
limited by how good its PMs are and starts being limited by how much of
their week reaches the work. Nobody notices the transition. Each individual
addition is reasonable — one more dashboard, one more weekly sync, one more
spreadsheet that three teams depend on and one person maintains — and then
one day the PMs are excellent, the roadmap is sensible, and everything takes
twice as long as it should.

Product ops is the function that gives that time back. It is not a PM
assistant, and it is not a project management office. Its customer is the
product organisation, and its job is to make the *system* of doing product
work reliable, so PMs can spend their hours on judgement rather than
plumbing.

This module covers what product ops actually owns, how to know when you need
it, the operating calendar, the two artefacts that pay for the whole
function, and how to measure whether it is working.

## The three pillars

| Pillar | Owns | Symptom when missing |
|---|---|---|
| **Data & insights** | Metric definitions, event taxonomy, self-serve dashboards, research repository, feedback taxonomy | Three decks with three different numbers for "active accounts" |
| **Process & cadence** | Planning rhythm, launch tiering, intake, release notes, roadmap format, review templates | Every quarter's planning is redesigned from scratch |
| **Tooling & knowledge** | The product stack, permissions, templates, onboarding for new PMs | New PM takes 10 weeks to be useful; nobody can find last year's decision |

A useful boundary test: **if two teams do the same thing differently and
nobody benefits from the difference, it belongs to product ops.** If the
difference is a real product judgement, it belongs to the PM.

## When do you need it?

| Signal | Threshold | What it means |
|---|---|---|
| Number of PMs | 5–8 | The point at which inconsistency costs more than a headcount |
| Time to answer "how many accounts use X?" | Over 1 day | You have a data-access problem, not an analyst shortage |
| Recurring metric disputes | More than 1 per month | No metric dictionary |
| New PM ramp time | Over 8 weeks | No documented operating system |
| Share of PM time on coordination and reporting | Over 30% | Do the audit below |
| Quarterly planning duration | Over 3 weeks | The process is the bottleneck |

Two or more signals firing is a stronger case than any headcount ratio. The
common ratio quoted is one product ops person per 6–10 PMs, but ratios are
descriptions, not diagnoses.

## Do the time audit before you argue for the hire

Two weeks of self-reported time, six categories, 30 seconds a day per PM.
The result is the business case.

**ListUp, 4 PMs at 42 hours/week = 168 PM-hours/week:**

| Category | Before | Hours/wk | After 2 quarters of product ops | Hours/wk | Δ |
|---|---|---|---|---|---|
| Discovery & customer contact | 14% | 23.5 | 26% | 43.7 | **+20.2** |
| Decisions & writing | 19% | 31.9 | 29% | 48.7 | **+16.8** |
| Coordination & status | 34% | 57.1 | 24% | 40.3 | −16.8 |
| Reporting & decks | 13% | 21.8 | 5% | 8.4 | −13.4 |
| Ad-hoc data pulls | 11% | 18.5 | 3% | 5.0 | −13.4 |
| GTM & enablement support | 9% | 15.1 | 13% | 21.8 | +6.7 |

**43.7 PM-hours per week** moved out of coordination, reporting and data
pulls. Over 46 working weeks that is **2,009 hours — 1.04 PM
FTE-equivalents**, against one product ops hire. At a $165,000 fully loaded
PM cost, the reclaimed capacity is worth about **$171,600 a year**.

Two honesties that make this argument credible rather than promotional:

- **Self-reported time is soft.** Present it as directional and re-run the
  audit after two quarters — which is exactly what produced the "after"
  column here.
- **Hours reclaimed are not automatically hours well spent.** Discovery
  contact rose from 23.5 to 43.7 hours a week; the follow-up question is
  whether the decisions got better, which is a separate measurement.

## The two artefacts that pay for the function

### 1. The metric dictionary

One row per metric, owned by product ops, disputed nowhere else.

| Field | Example entry |
|---|---|
| **Name** | Active account |
| **Definition** | An account that published at least one listing change in the trailing 28 days |
| **Excludes** | Internal accounts, trials, accounts in dunning past day 14 |
| **Source** | `fact_publish_events`, joined to `dim_account` |
| **Grain** | Account × day |
| **Owner** | Growth PM |
| **Refresh** | Daily, 06:00 UTC |
| **Known caveats** | Bulk imports count as one change, not N |
| **Approved uses** | Board deck, weekly review |
| **Do not use for** | Billing or entitlement decisions |

The last two rows prevent the most expensive class of error: a number that
was correct for one purpose being reused for another where it is wrong.

### 2. The feedback taxonomy

Feedback arrives from six places in five formats. Without one taxonomy you
cannot count anything.

| Field | Values |
|---|---|
| **Source** | Sales intake, CS ticket, churn interview, in-app, review site, user research |
| **Account** | ID, tier, ARR, tenure |
| **Problem theme** | From a controlled list, ~30 entries, owned by product ops |
| **Job affected** | Connect, decide, publish, verify, report |
| **Severity** | Blocker / friction / annoyance / wish |
| **Evidence type** | Observed / reported / inferred |

Two rules keep this honest: **only product ops adds a theme to the
controlled list** (otherwise you get 400 free-text themes and no counts),
and **every theme carries a revenue roll-up** so a monthly report can say
"theme 14 touches 212 accounts and $38,400 of MRR" instead of "we hear this
a lot".

## The operating calendar

Product ops owns the rhythm so no PM has to reinvent it.

| Cadence | Ritual | Owner | Product ops provides |
|---|---|---|---|
| Weekly | Metrics review, 30 min | Head of Product | Dashboard refreshed and annotated before the meeting |
| Weekly | OKR confidence update | PMs | The template and the nag |
| Bi-weekly | Release notes and changelog | PMs | Format, publishing, distribution |
| Monthly | Feedback theme report | Product ops | The whole thing |
| Monthly | Roadmap outlook refresh for GTM | PMs | Format, assembly, distribution |
| Quarterly | Planning (3 weeks: inputs → drafts → commit) | Head of Product | Timeline, templates, pre-read pack, data |
| Quarterly | OKR grading and retro | PMs | Scoring sheet, historical comparison |
| Quarterly | Win/loss synthesis | Product ops | Analysis and report |
| Annually | Strategy refresh | Head of Product | Market data, cohort analysis, competitive pack |
| Continuous | Launch tiering and checklist | PMs | Tier definitions, checklist, gate tracking |

The most under-appreciated line is the quarterly planning timeline. Turning
planning from "three chaotic weeks" into "a dated sequence with a pre-read
pack" is usually the single largest time saving the function delivers.

## Worked example — ListUp's first two product ops quarters

**Hire made after** four signals fired: PMs at 4 (approaching the 5–8 band),
34% of time on coordination and reporting, a metric dispute in three
consecutive board decks, and a 10-week new-PM ramp.

**Quarter 1 — stop the bleeding.**

| Week | Deliverable | Result |
|---|---|---|
| 1–2 | Time audit and metric-dispute inventory | 11 metrics with more than one definition in use |
| 3–5 | Metric dictionary v1, 26 metrics | Board deck and weekly review reconciled; two dashboards deleted |
| 6–8 | Self-serve dashboard: adoption by tier, funnel, churn | Ad-hoc data requests fell from 31/month to 9/month |
| 9–11 | Feedback taxonomy and one intake pipeline | First monthly theme report with revenue roll-ups |
| 12 | Quarterly planning timeline and pre-read pack | Planning ran 3 weeks instead of 5 |

**Quarter 2 — build the system.**

| Deliverable | Result |
|---|---|
| Launch tiering (T1/T2/T3) with checklists | Two T3 launches skipped work that used to be done reflexively |
| PM onboarding pack: dictionary, calendar, templates, 12 recorded customer calls | New PM ramp 10 weeks → 5 weeks |
| Win/loss synthesis, quarterly | Produced the P(true blocker) estimates used in Module 6's triage |
| Experiment registry with pre-registration | Stopped two duplicate tests; made Module 8's meta-analysis possible |
| Roadmap outlook format, refreshed monthly | Sales stopped asking individual PMs for dates |

**What product ops explicitly did not take on**, agreed in writing on day
one, because a function without a boundary becomes a dumping ground:

| Not owned | Stays with |
|---|---|
| Prioritisation decisions | PMs |
| Writing PRDs or specs | PMs |
| Being the roadmap's spokesperson | PMs and Head of Product |
| Running standups for delivery teams | Engineering managers |
| Customer discovery interviews | PMs (ops provides the recruiting pipeline) |

## Measuring product ops

The function must be held to outcomes, not activity, or it degrades into a
template factory.

| Metric | Baseline | After 2 quarters |
|---|---|---|
| PM time on discovery + decisions | 33% | 55% |
| Ad-hoc data requests per month | 31 | 9 |
| Metric disputes per month | 3 | 0 |
| New PM ramp to first owned decision | 10 weeks | 5 weeks |
| Quarterly planning elapsed time | 5 weeks | 3 weeks |
| Launches with a completed checklist | 45% | 100% |
| Experiments pre-registered | 20% | 92% |

## Anti-patterns

| Anti-pattern | Looks like | Fix |
|---|---|---|
| **Ops as PM assistant** | Ops writes the PM's deck | Ops builds the template; the PM writes the content |
| **Process police** | Compliance reviews, mandatory forms nobody uses | Every process must save more time than it costs; measure it |
| **Shadow analytics team** | Ops becomes a data-pull queue | Ops builds self-serve; a persistent queue means the dashboard is wrong |
| **Owning the roadmap** | Ops arbitrates priorities | Ops owns the process, PMs own the calls |
| **Hiring too early** | Two PMs and a product ops manager | Under 5 PMs, the Head of Product does this; write the docs yourself |
| **Never sunsetting** | 40 dashboards, 9 used | Audit annually; delete anything unopened in 90 days |

## Exercise

1. **Run the time audit.** Two weeks, six categories, every PM including
   yourself. Publish the percentages and the hours per week.
2. **Check the signals.** Score your organisation against the six thresholds
   and state how many fire. If it is fewer than two, write the case for *not*
   hiring yet, and what you would do instead.
3. **Inventory metric disputes.** List every metric that has more than one
   definition in active use. For the three most-cited, write full dictionary
   entries including "do not use for".
4. **Build the feedback taxonomy**: a controlled list of no more than 30
   problem themes, plus the fields above. Recode the last 60 pieces of
   feedback into it and produce the first theme report with revenue
   roll-ups.
5. **Draw the operating calendar** for your team — every recurring ritual,
   its owner, and what would have to exist for it to run without a PM
   preparing it by hand.
6. **Write the boundary list**: five things product ops will own and five it
   will not. Get the head of product to sign it.
7. **Set the outcome metrics** with baselines measured today and targets at
   two quarters, and put the re-measurement date in the calendar now.
8. **Find one thing to delete.** Identify a recurring meeting, dashboard or
   report that nobody has used in 90 days, and remove it this week. The
   first product ops act should subtract, not add.
