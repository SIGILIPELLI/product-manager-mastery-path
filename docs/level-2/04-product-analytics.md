# 04 · Product Analytics

Level 1 metrics answer "how are we doing." Product analytics answers "where
exactly is the product losing people, and what would fixing it be worth."
The difference is structural: a KPI dashboard reports totals, while
analytics decomposes those totals into **funnels** (where users drop),
**cohorts** (whether the product is getting better over time), and
**retention curves** (whether it holds anyone at all). A PM who can't do
this is dependent on someone else to convert a number into a decision.

This module covers the event model everything rests on, the four analyses
you will use weekly, and how to turn a funnel step into a revenue estimate
so your roadmap arguments carry a number.

## The event model comes first

Every analysis below is only as good as the events underneath it. Analytics
debt is unrecoverable — you cannot backfill an event you never fired.

| Element | Rule | Good | Bad |
|---|---|---|---|
| Event name | `object_action`, past tense, snake_case | `listing_published` | `Publish!`, `user did publish` |
| Granularity | One event per meaningful user action, not per click | `marketplace_connected` | `button_clicked` (with 40 meanings) |
| Properties | Everything you'd want to segment by, on the event itself | `marketplace: "B"`, `listing_count: 47`, `plan: "growth"` | Properties looked up later from a different table |
| Identity | Same user ID pre- and post-signup; alias anonymous IDs | `user_id` stitched at signup | Anonymous sessions orphaned |
| Ownership | A tracking plan in version control, reviewed like an API | One spreadsheet/repo, one owner | Ad-hoc events added per feature |

**PM habit:** every PRD gets a tracking section listing the events and
properties needed to evaluate the feature. If it's not in the PRD, it does
not exist at launch, and you will spend the following month arguing from
anecdotes.

## Funnel analysis

A funnel is an ordered sequence of events within a time window. Two rules
save you from most bad funnel readings: **specify the window** (a 7-day
funnel and a 30-day funnel tell different stories), and always read the
**step conversion**, not just the overall rate — the overall rate hides
which step is the problem.

| Step | Users | Step conv. | Overall |
|---|---|---|---|
| Signed up | 1,000 | — | 100% |
| Connected 1st marketplace | 620 | 62.0% | 62.0% |
| Imported ≥1 listing | 430 | 69.4% | 43.0% |
| Published to 2nd marketplace | 180 | **41.9%** | 18.0% |
| Still active in week 2 | 126 | 70.0% | 12.6% |

Read this the right way round: the biggest *absolute* loss is step 1 (380
users), but the worst *step conversion* is step 3 at 41.9% — and step 3 is
where the product's core promise lives. Prioritize by "worst step
conversion on a step that matters," then check whether the loss is large
enough to be worth the work.

**Sizing the prize.** If step 3 goes from 41.9% to 55%, then 430 × 0.55 =
237 users reach the second marketplace and 237 × 0.70 = **166** stay active
in week 2, versus 126 today. That's **+40 activated users per 1,000
signups**, a 31.7% relative improvement in activation. At ~22% of activated
users converting to paid and $69 ARPU, one month's cohort is worth roughly
**$607 in new MRR** — recurring, and repeating every month. That sentence is
what wins a prioritization argument; "step 3 looks bad" is not.

## Cohort analysis

A cohort is a group defined by when they started (or by a shared property).
Cohorts answer the question totals cannot: *is the product improving, or is
the total just growing?*

| Signup cohort | Size | W1 | W2 | W4 | W8 | W12 |
|---|---|---|---|---|---|---|
| January | 1,000 | 42% | 31% | 25% | 23% | 22% |
| February | 1,180 | 44% | 33% | 26% | 24% | — |
| March | 1,240 | 51% | 40% | 33% | — | — |
| April (post-onboarding fix) | 1,310 | 58% | 46% | — | — | — |

Reading a cohort table: **down a column** tells you whether the product got
better for successive cohorts; **across a row** tells you the shape of the
retention curve. Here the W1 column climbing 42 → 58% across four months is
the strongest evidence the onboarding work paid off — a total-users chart
would have shown the same upward line whether or not the fix worked.

## Retention curves

Plot the % of a cohort active in each period since signup. The only thing
that matters is the shape:

| Curve shape | Meaning | Action |
|---|---|---|
| **Flattens** at a positive floor | Product-market fit for that segment; a stable base accumulates | Grow the top of the funnel — you can now afford to |
| **Decays to zero** | No habitual use case; growth leaks out as fast as it comes in | Stop acquiring; fix the core value |
| **Smiles** (dips then rises) | A subset finds deep value after a delay | Find that subset; make their path the default |

Then split the curve by whether users hit your activation event:

| Segment | Share of cohort | W4 retention |
|---|---|---|
| Activated (published to a 2nd marketplace in week 1) | 18% | **62%** |
| Not activated | 82% | **17%** |
| Blended | 100% | 25.1% |

The gap between 62% and 17% is the entire product argument. Raising
activation from 18% to 28% — with no change to retention within either
group — lifts blended W4 retention from 25.1% to **29.6%**, +4.5 points.
That is what "define an activation metric" is actually for.

## Engagement depth

| Metric | Definition | Use it for | Caution |
|---|---|---|---|
| DAU/MAU | Daily actives ÷ monthly actives | Daily-use products | Meaningless for weekly or monthly workflows |
| **Ln/28** (e.g. L7/28) | Days active in the last 28 | Any cadence; far better than DAU/MAU | Needs a defined "active" event |
| Power-user curve | Histogram of users by days active in 28 | Spotting bimodality | Averages hide this entirely |
| Feature adoption | % of *active* users using feature X | Cutting dead features | Denominator must be actives, not all accounts |

ListUp's DAU/MAU is 2,400 ÷ 9,000 = **26.7%**, which sounds mediocre until
you remember sellers publish on a weekly cadence. The right metric for this
product is L4/28 (four or more active days in 28), where the power-user
histogram is bimodal: one cluster at 1–2 days and one at 8+, with almost
nobody between. Averages would report "4.1 days" — a value no actual user
experiences.

## The North Star and its inputs

One North Star metric, decomposed into 3–5 inputs a team can actually own:

| Level | ListUp example | Owner |
|---|---|---|
| **North Star** | Weekly cross-listed publishes (listings pushed to 2+ channels) | Whole product org |
| Input: breadth | % of accounts with 2+ marketplaces connected | Onboarding team |
| Input: frequency | Publishes per active account per week | Core product team |
| Input: reliability | % of publishes that succeed first try | Platform team |
| Input: retention | W4 retention of activated accounts | Whole product org |

A good North Star has three properties: it moves *before* revenue, it
represents delivered customer value (not clicks), and every input is
plausibly ownable by one team. If an input can't be assigned, it isn't an
input — it's a wish.

## Worked example — ListUp's quarterly analytics review

**Question:** the quarter's outcome is raising weekly cross-listed publishes.
Where's the leverage?

1. **Funnel:** step 3 (publish to 2nd marketplace) converts at 41.9%, the
   worst step on the critical path — 250 users lost per 1,000 signups.
2. **Cohorts:** W1 retention has climbed 42 → 58% since the onboarding fix,
   so top-of-funnel is *not* the constraint any more; the constraint moved
   downstream.
3. **Retention split:** activated users retain at 62% vs 17%. Activation is
   the lever, and activation *is* step 3.
4. **Segmentation:** among users stuck at step 3, 71% never opened the
   marketplace-connection settings a second time — consistent with the
   API-key friction found in interviews (Module 1) and the 41% drop-off in
   that step's own micro-funnel.
5. **Sizing:** step 3 at 55% yields +40 activated users per 1,000 signups
   (+31.7%), ≈ $607 new MRR per monthly cohort, and +4.5 points of blended
   W4 retention if activation reaches 28%.

**Conclusion presented to the team:** one number (41.9%), one cause
(second-marketplace connection friction), one prize ($607/month recurring
per cohort, compounding). Three data sources — funnel, cohort, interviews —
pointing at the same step. That triangulation is what makes an analytics
finding safe to bet a quarter on.

## Exercise

Using your own product's analytics (or ListUp's numbers):

1. **A tracking plan** for one feature: 5+ events in `object_action` form,
   each with its properties and a one-line definition of when it fires.
2. **A funnel table** for your primary conversion path — 4+ steps, with the
   time window stated, showing user counts, step conversion, and overall
   conversion. Circle the worst *step* conversion, not the biggest drop.
3. **A cohort retention table**: 4+ cohorts × 4+ periods. State in one
   sentence whether the product is getting better for new users, and what
   in the table proves it.
4. **A retention curve split by your activation event.** Report retention
   for activated vs not-activated, and compute the blended retention if
   activation rose by 10 percentage points.
5. **A sized recommendation**: pick the one funnel step you'd fix, estimate
   the improved step conversion, and carry the arithmetic all the way to
   users and revenue per month. Show the calculation, not just the result.
