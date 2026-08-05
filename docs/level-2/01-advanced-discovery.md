# 01 · Advanced Discovery

Level 1 discovery gets you one validated problem at a time, usually in a
burst right before a planning cycle. That works until the questions get
harder: *why* did this customer switch to us, what else could we have built
instead, and what do we already know that we haven't acted on? This module
covers three upgrades — framing demand as a **job** rather than a feature
request, keeping a standing **opportunity solution tree** so "what next" is
answered from accumulated evidence, and **assumption mapping** so you test
the risky part of an idea before building all of it.

## Jobs-to-be-Done: what the customer hired the product to do

A *job* is the progress someone is trying to make in a specific
circumstance. Jobs are stable for decades; the solutions people hire to do
them churn constantly. If you write requirements at the solution level, you
inherit whatever the customer happened to imagine. Write at the job level
and you keep the freedom to solve it better than they asked.

**Job statement template:**

> When **[situation]**, I want to **[motivation]**, so I can
> **[expected outcome]**.

| Solution-framed (what you'll hear) | Job-framed (what to write down) |
|---|---|
| "Add a bulk CSV upload" | When I add a new season's stock all at once, I want every item listed without re-typing it per marketplace, so I can start selling the day it arrives |
| "We need a Slack integration" | When something breaks in a live campaign, I want to find out where I already am, so I can react before the client notices |
| "Give us more dashboard charts" | When my boss asks how the quarter is going, I want a defensible number in under a minute, so I can answer without looking unprepared |

Every job has three dimensions, and roadmaps usually fund only the first:

| Dimension | Question | Example — the "answer my boss" job |
|---|---|---|
| **Functional** | What task must get done? | Pull the current quarter's revenue |
| **Emotional** | How does the person want to feel? | Confident the number is right |
| **Social** | How do they want to be perceived? | As someone on top of their numbers |

A chart that is technically correct but that the user doesn't trust enough
to forward has solved the functional job and failed the emotional one —
which is exactly why it goes unused.

## The four forces of progress

People switch products only when the forces pushing them toward change
outweigh the forces holding them in place:

**A switch happens when (Push + Pull) > (Habit + Anxiety).**

| Force | What it is | Interview question that surfaces it | Product lever |
|---|---|---|---|
| **Push** of the situation | The problem with today that made them look | "What was going on the day you decided to look for something else?" | Positioning — name the pain out loud |
| **Pull** of the new solution | What attracted them to you | "What made you think this would be better?" | Features, demo, onboarding promise |
| **Habit** of the present | Inertia, sunk cost, workarounds that mostly work | "What would you have to give up to move?" | Import tools, parity on what they'd lose |
| **Anxiety** of the new | Fear of migration, data loss, looking foolish | "What worried you before you committed?" | Trials, guarantees, migration help, proof |

Most teams over-invest in Pull (more features) when the real blocker is
Anxiety or Habit. If your win rate is low but demos go well, you have an
anxiety problem, not a feature gap — and no amount of roadmap fixes it.

## The switch interview

Interview people who switched **recently** (ideally within 60–90 days) and
walk their timeline backwards. Ask about the last specific time, never what
they "usually" or "would" do.

| Stage | What you're reconstructing | Ask |
|---|---|---|
| First thought | The trigger event | "When did you first think today's setup wasn't working?" |
| Passive looking | Casual awareness | "What did you notice or read between then and actually searching?" |
| Active looking | Deliberate evaluation | "What did you type into Google? Who did you ask?" |
| Deciding | The final tradeoff | "What were the last two options, and what tipped it?" |
| First use | Whether the job got done | "What was the first thing you did after signing up? Did it work?" |

| Speculative (throw away) | Evidence-based (keep) |
|---|---|
| "Would you use a bulk import?" | "Walk me through the last time you added 50+ items." |
| "How important is speed, 1–5?" | "How long did that take? What were you doing while you waited?" |
| "What features are missing?" | "What did you do when the product couldn't do that?" |

The workaround is the most valuable thing you can find in an interview: a
workaround is a problem someone cared enough about to pay a cost for.

## Opportunity solution trees

An opportunity solution tree keeps everything you've learned in one visible
structure, so prioritization (Module 2) starts from a map, not a brainstorm.

| Layer | What belongs here | Well-formed test | Common mistake |
|---|---|---|---|
| **Outcome** | One measurable product outcome for the quarter | Is it a metric this team can move? | "Grow revenue" — too far from the team's control |
| **Opportunity** | An unmet need, pain, or desire, in customer language | Can you cite the observation it came from? | A solution in disguise ("needs a mobile app") |
| **Solution** | A way to address one opportunity | Are there 3+ competing options for this opportunity? | Taking the first idea and calling it the plan |
| **Assumption test** | The smallest experiment that de-risks a solution | Could it run this week? | "Testing" by shipping the whole thing |

| Weak opportunity | Rewritten |
|---|---|
| "Users want an API" | "Sellers running promotions can't get price changes live fast enough to match a competitor the same day" |
| "Onboarding is bad" | "New sellers stall connecting their second marketplace because they can't find the API key in the marketplace's own settings" |

Rule of thumb: if you can't name the interview or data point an opportunity
came from, it's an opinion, and opinions go on a separate list.

## Assumption mapping

Before building any solution, list what must be true for it to work, then
sort by importance and current evidence:

|  | **Weak evidence** | **Strong evidence** |
|---|---|---|
| **High importance** | Test these first — this is your entire risk | Proceed; write down why |
| **Low importance** | Ignore for now; revisit if scope grows | Ignore |

Four risk types, and the cheapest test for each:

| Risk | Question | Cheapest test |
|---|---|---|
| **Value** | Will anyone want it? | Fake door, landing page, or pre-sale conversation |
| **Usability** | Can they figure it out? | 5-user prototype test, unmoderated |
| **Feasibility** | Can we build it in a sane time? | Engineering spike, timeboxed to 2 days |
| **Viability** | Does it work for the business? | Back-of-envelope unit economics, legal/support review |

## Continuous discovery cadence

| Cadence | Activity | Output | Time cost |
|---|---|---|---|
| Weekly | 2 customer interviews (PM + designer + rotating engineer) | New/updated opportunities on the tree | 2 hours |
| Weekly | Update the opportunity solution tree | Current map of the problem space | 30 min |
| Biweekly | Run 1 assumption test on the top solution | Ship / rework / kill decision | Varies |
| Monthly | Review the tree with the team, prune stale branches | Shared, current picture of the space | 1 hour |

The point of a cadence is that you never have to *start* discovery — the
interview pipeline is always running, so a new question costs a week, not a
quarter.

## Worked example — ListUp

**Product:** ListUp, a tool for small e-commerce sellers managing listings
across their own store plus two marketplaces.

**Outcome for the quarter:** raise the share of sellers publishing to 2+
marketplaces weekly from 38% to 50%.

**Switch interviews (6 sellers who adopted in the last 60 days):**

- Push: "I lost a weekend re-typing 200 items for Marketplace B."
- Pull: "The demo showed one edit going to both places."
- Habit: "My spreadsheet has all my SKU notes; nothing imports those."
- Anxiety: "If it pushes a wrong price to a live listing, I eat the loss."

**Job statement:** *When I get a shipment of new stock, I want it listed
everywhere I sell before the weekend, so I can catch the traffic without
spending Saturday typing.*

**Opportunity solution tree (abbreviated):**

| Opportunity (with its source) | Candidate solutions |
|---|---|
| Sellers can't trust that a price edit actually reached Marketplace B (4/6 interviews; 7 support tickets) | (a) per-listing sync status badge, (b) push notification on sync failure, (c) pre-publish "diff" preview |
| Sellers lose their spreadsheet notes when migrating (3/6 interviews) | (a) custom notes field on import, (b) CSV column mapper, (c) attach the original CSV to the listing |
| Second-marketplace setup stalls at API key retrieval (2/6 interviews; 41% drop-off at that step in analytics) | (a) guided screenshots per marketplace, (b) OAuth instead of keys, (c) concierge setup call |

**Assumption mapped and tested:** the riskiest assumption behind solution
(c) *pre-publish diff preview* was **value** — "sellers will pause to read a
diff rather than click through it." Test: a 5-user prototype session plus a
fake-door link in the existing publish flow. Four of five read the diff and
one caught a real pricing error in her own data — enough evidence to build,
at a far smaller scope than the "full audit log" originally requested.

## Exercise

Pick a product you work on (or the ListUp scenario) and produce:

1. **Three switch interview scripts** — the five timeline stages above with
   your actual questions written out. If you can, run at least one.
2. **One job statement** in *When… I want… so I can…* form, plus a sentence
   each on its emotional and social dimension.
3. **A four-forces table** for your product: one concrete push, pull, habit,
   and anxiety, then note which force your last three shipped features
   addressed. If all three were Pull, say what that implies.
4. **An opportunity solution tree** with one outcome, at least four
   opportunities (each citing the observation it came from), and three
   competing solutions for your top opportunity.
5. **An assumption map** for that top solution: list every assumption, place
   them on the importance/evidence grid, and specify the exact test you'd
   run this week on the highest-risk one.
