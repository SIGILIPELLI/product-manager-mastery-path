# 06 · Working with Data Teams

Analysts and data scientists are the most over-subscribed people in most
product orgs, and PMs are usually the reason. The typical request — "can you
pull the numbers on onboarding?" — has no question in it, no decision
attached, and no definition of "onboarding," so the analyst spends two days
guessing and produces something you then ask them to redo. Get this
relationship right and you get answers in hours; get it wrong and you get a
queue.

The core shift is simple: **bring a decision, not a data pull**. This module
covers how data functions are organised, how to write a request that gets a
fast answer, the difference between the four question types (and which ones
data alone can never settle), how to keep metric definitions from drifting,
and how to work with a data scientist on a model without pretending to be
one.

## Who does what

| Role | Optimises for | Bring them | Don't bring them |
|---|---|---|---|
| **Data/analytics engineer** | Reliable pipelines and models of the data warehouse | New event sources, broken tables, a metric that needs to exist for everyone | One-off questions |
| **Product analyst** | Answering questions that change decisions | Diagnostics, funnel/cohort deep dives, experiment readouts | Dashboard maintenance you could self-serve |
| **Data scientist** | Prediction, causal inference, modelling | Forecasting, propensity/ranking models, quasi-experimental analysis | Descriptive counts |
| **Analytics/BI tooling owner** | Self-serve access and definition governance | Instrumentation reviews, metric definitions, access | Analysis |

If your org has one person wearing all four hats, the same rule applies with
more force: their scarcest resource is context-switching, so batch requests
and state the decision.

## The four question types

Which type you're asking determines who to ask, how long it takes, and
whether data can answer it at all.

| Type | Question form | Method | Typical effort | Limit |
|---|---|---|---|---|
| **Descriptive** | What happened? | Dashboard, SQL query | Hours — often self-serve | Tells you nothing about cause |
| **Diagnostic** | Why did it happen? | Segmentation, funnel decomposition, cohort comparison | 1–3 days | Produces hypotheses, not proof |
| **Predictive** | What will happen? | Forecasting, propensity models | 1–4 weeks | Assumes the future resembles the past |
| **Causal** | What will happen *if we change X*? | Experiment; failing that, quasi-experimental methods | Weeks | Correlational data cannot answer it — this is the trap |

The trap is worth stating plainly: "users who use feature X retain 3× better"
is descriptive. It is not evidence that feature X causes retention — the
people who use X may simply be the people who were always going to stay.
Only an experiment (Module 3) or a proper causal design separates the two,
and roadmaps built on that confusion are extremely common.

## The analysis brief

Send this instead of a Slack message. It takes ten minutes to write and
routinely saves days.

| Field | What goes here | Bad | Good |
|---|---|---|---|
| **Decision** | What you will do differently depending on the answer | "Understand onboarding" | "Decide whether next sprint fixes the API-key step or the import step" |
| **Question** | One sentence, answerable | "How's onboarding doing?" | "Which onboarding step has the worst step conversion for accounts created in the last 90 days?" |
| **Hypothesis** | What you expect, so a surprise is visible | — | "The 2nd-marketplace connect step, around 40–45%" |
| **Population** | Exact filter | "Users" | "Self-serve accounts created 2026-03-01 to 2026-05-31, excluding internal and trial-abuse accounts" |
| **Metric definitions** | How each term is computed | "Active" | "Active = ≥1 `listing_published` in the trailing 7 days" |
| **Cut by** | The segments that would change the decision | — | Plan tier, channel count at signup, acquisition source |
| **Deadline & why** | Real date and the meeting it feeds | "ASAP" | "Thu 14th — sprint planning Fri" |
| **Good enough** | The precision the decision needs | — | "±5 points is fine; I need the ranking of steps, not exact rates" |

That last row is the one PMs skip and analysts value most. Most decisions
need a direction and a rough magnitude, and saying so converts a three-day
job into a three-hour one.

## Metric definitions drift — govern them

The most expensive data problem in product orgs isn't bad pipelines; it's
two teams reporting different numbers for the same word in the same meeting.

| Term | Ambiguity | Pinned definition |
|---|---|---|
| Active user | Logged in? Did something? Over what window? | ≥1 `listing_published` in trailing 7 days, deduped by `account_id` |
| Churn | Cancelled, expired, or downgraded? | Subscription not renewed at period end; downgrades tracked separately as contraction |
| Signup | Account created or email verified? | `account_created` with a verified email; unverified excluded from all funnels |
| Activation | The vague one, always | Published to ≥2 distinct marketplaces within 14 days of signup |
| MRR | Does it include annual, tax, discounts? | Normalized monthly value, net of discounts, excluding tax and one-time fees |

Keep these in one versioned document that the analytics layer implements
literally. When a definition changes, **restate history** or clearly mark the
break — a metric that changes definition silently destroys every trend chart
that predates it.

## Self-serve versus asking

| Situation | Do it yourself | Ask an analyst |
|---|---|---|
| A number that exists on a dashboard | ✅ | |
| One filter or breakdown on a known metric | ✅ | |
| Joining across sources, or a new metric definition | | ✅ |
| Anything you'll put in a document that others act on | | ✅ (at minimum, get it reviewed) |
| Experiment readout | | ✅ always |
| Exploratory "poke around" | ✅ | |

PM SQL literacy is worth the investment even in self-serve orgs. You don't
need to write joins under pressure, but you should be able to read a query
and tell whether it answers your question — specifically: what table it hits,
what the `WHERE` clause excludes, what the grain of a row is (one row per
user? per event? per day?), and whether a `JOIN` could be duplicating rows
and inflating a count. Those four checks catch most wrong numbers.

## Working with a data scientist on a model

When a model is the deliverable, your job is to own the **decision
threshold**, because that is a product tradeoff, not a technical one.

ListUp builds a model that flags listings likely to contain a pricing error
before publish. Over 10,000 publishes, 300 truly contain an error:

| Threshold | Flagged | Caught (TP) | False alarms (FP) | Missed (FN) | Precision | Recall |
|---|---|---|---|---|---|---|
| 0.7 (conservative) | 150 | 95 | 55 | 205 | **63.3%** | 31.7% |
| 0.5 (balanced) | 400 | 180 | 220 | 120 | 45.0% | 60.0% |
| 0.3 (aggressive) | 900 | 240 | 660 | 60 | 26.7% | **80.0%** |

Now price the errors. A missed pricing error costs a seller ~$40 on average;
a false alarm costs about a minute of review. At 0.5, missed errors cost
120 × $40 = **$4,800** per 10,000 publishes, against 220 interruptions. At
0.3, missed errors cost 60 × $40 = **$2,400**, against 660 interruptions.
The aggressive threshold halves the money lost and triples the annoyance —
and choosing between those is a product decision about trust, not an
optimisation problem. Note that the "best F1" threshold here is 0.5 (0.514
vs 0.400), and it is *not* the one that minimises customer loss. Never let a
model ship on F1 alone.

Questions to ask before any model ships: what's the baseline a simple rule
achieves? What does the model do on new accounts with no history? How will
we detect drift? What does the user see when it's wrong, and can they
override it?

## Worked example — a request that worked

**The Slack version (rejected, politely):** "Hey, can you pull onboarding
numbers for the last quarter? Trying to figure out where people drop off."

**The brief version:**

> **Decision:** which onboarding step next sprint fixes — API-key entry or
> CSV import. One will be built, the other deferred a quarter.
> **Question:** which step of the signup→activation funnel has the worst
> step conversion, and does it differ by acquisition source?
> **Hypothesis:** the second-marketplace connect step, ~40–45%, worse for
> paid-search signups.
> **Population:** self-serve accounts created 2026-03-01 → 2026-05-31,
> excluding internal domains and accounts flagged as trial abuse.
> **Definitions:** activation = published to ≥2 marketplaces within 14 days.
> Step conversion = users reaching step N ÷ users reaching step N−1.
> **Cut by:** acquisition source, channel count at signup, plan tier.
> **Deadline:** Thursday, feeds Friday sprint planning.
> **Good enough:** ±5 points; I need the ranking of steps and whether the
> source split is large, not exact rates.

**What came back in four hours:** step 3 converts at 41.9% overall (worst on
the path); paid-search signups convert at 33.4% versus 46.1% organic; and an
unrequested finding the analyst noticed while scoping the population — 71%
of stuck accounts never reopened the connection settings, which pointed
straight at the API-key hypothesis.

**Why it worked:** the analyst knew the decision, so they knew the extra cut
was worth mentioning and that three decimal places weren't. The "good
enough" line is what turned a three-day job into an afternoon.

## Exercise

1. **Write an analysis brief** for a real question you have right now, using
   all eight fields. Send it. Compare the turnaround to your last request.
2. **Build a metric definitions table** for the five terms your team argues
   about most. Get one analyst and one engineer to sign off in writing, and
   note every place a current dashboard contradicts the agreed definition.
3. **Classify your last ten data requests** as descriptive, diagnostic,
   predictive, or causal. Flag any where you drew a causal conclusion from
   descriptive data, and say what experiment would actually settle it.
4. **Read one SQL query** behind a metric you rely on. Write down its grain,
   what its `WHERE` clause excludes, and one way it could be wrong.
5. **If your team has a model:** build the threshold table above with your
   real precision/recall numbers, attach a cost to each false positive and
   false negative, and recommend a threshold in business terms.
