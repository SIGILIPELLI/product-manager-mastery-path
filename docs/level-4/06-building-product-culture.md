# 06 · Building Product Culture

Culture is the least tractable-sounding word in management and one of the
most concrete things a product leader actually controls. The trouble is that
almost every attempt to build it starts in the wrong place — with values on
a wall, an offsite, a set of adjectives — and adjectives do not survive
contact with a quarter-end.

A more useful definition, and the one this module uses: **culture is the set
of behaviours that reliably happen when you are not in the room.** It is
produced by three things, in descending order of power: what gets rewarded,
what gets tolerated, and what gets said. Values statements are the third
category, which is why they change nothing on their own. Promote a PM who
ships without evidence and you have communicated your real standard more
loudly than any document.

At VP level this matters because it is your only remaining lever at scale.
With 76 people in R&D you cannot review the decisions; you can only shape
the conditions under which they get made.

## Norms, and the artefact that encodes each

A norm that lives only in people's heads decays with every hire. A norm
encoded in an artefact — a template, a checklist, a recurring forum, a
default in a tool — survives.

| Norm | The artefact that encodes it | What happens without it |
|---|---|---|
| Decisions are written down | A one-page decision record with owner, options, and rationale | The same argument is re-litigated every quarter |
| Claims come with evidence | The "how do you know?" column in every review template | Confident people win over correct people |
| Experiments are pre-registered | A registry with hypothesis and success criteria filed before launch | Post-hoc rationalisation of every result |
| Negative results are published | A standing agenda item in the monthly product review | Teams learn to hide failure, then to avoid risk |
| Customers are met directly | A quota — every PM does 3 customer conversations a month, logged | Product opinions drift into internal folklore |
| Strategy is repeatable by anyone | The one-page strategy, restated in every all-hands | Eight teams optimise eight different things |
| Disagreement is aired, then committed to | An explicit disagree-and-commit protocol with a named decider | Passive resistance in the execution phase |
| Bad news travels up fast | Leaders visibly thank the person who brought it | You find out from the churn report |
| Launches have pre-set success criteria | Criteria fixed in the launch doc before code is written | Everything is a success in retrospect |
| Postmortems are blameless | A template with no "who" field and a published output | The cause is recorded as "human error" and recurs |

**The test for any norm you claim to hold: name the artefact.** If you
cannot, you have an aspiration, not a norm.

## The four cultures product orgs drift into

| Culture | Optimises for | Feels like | Fails at | Common in |
|---|---|---|---|---|
| **Craft** | Quality of the thing built | Design reviews, high standards, slow | Speed; commercial urgency | Design-led companies |
| **Velocity** | Throughput | Ship weekly, dashboards everywhere | Coherence; nobody owns the whole | Growth-stage PLG |
| **Consensus** | Alignment | Everyone consulted, few things decided | Speed; strong opinions leave | Post-IPO, large orgs |
| **Command** | Speed of decision | The founder or VP decides | Scaling; the org stops thinking | Founder-led companies |

None is wrong; each is a trade. The failure is drifting into one without
choosing it, then hiring people suited to a different one. ListUp is
**velocity-leaning and needs more craft**, which is a sentence worth saying
out loud at an all-hands, because it tells 76 people which way to lean when
the trade-off appears on a Tuesday afternoon.

## Diagnosing the culture you actually have

Adjectives are unmeasurable. Behaviours are countable. Pick behaviours that
would be expensive to fake.

**ListUp's R&D culture diagnostic**, run over one quarter across 76 people:

| Behaviour | Measurement | Baseline | Target | Reads as |
|---|---|---|---|---|
| Experiments pre-registered | Registry entries ÷ experiments run | 34% | 90% | Results are decided after the fact |
| Negative results published | Count per quarter | 2 | 10+ | Failure is hidden |
| Launches with pre-set success criteria | Share of launches | 48% | 90% | Everything succeeds retrospectively |
| PM customer conversations | Per PM per month | 1.4 | 3.0 | Opinions are internal |
| Decisions with a written record | Share of significant decisions | 29% | 80% | Re-litigation is routine |
| Strategy stated consistently | Variance across 12 random skip-level answers | 6 distinct answers | Under 3 | The strategy is not landing |
| Postmortems published | Share of Sev-1/Sev-2 incidents | 62% | 100% | Learning stops at the team boundary |
| Bad news lead time | Days between a team knowing and leadership knowing | 11 | Under 3 | Escalation feels unsafe |
| Regretted PM attrition | Trailing 12 months | 12.5% | Under 10% | See exit interviews |
| Time in recurring status meetings | Person-hours per week, R&D | 88 | Under 30 | Coordination has replaced work |

The last two rows are the ones executives skip and the ones that cost most.
Take the meeting line seriously.

## The meeting audit, costed

Four recurring status meetings, average 22 attendees, one hour, 50 weeks a
year:

| Line | Value |
|---|---|
| Person-hours per year | 4 × 22 × 1 × 50 = **4,400** |
| Fully loaded cost at $97.50/hour | **$429,000** |
| Written replacement: 4 authors × 25 min + 22 readers × 8 min, weekly | **670 hours** |
| Cost of the written version | **$65,325** |
| **Annual saving** | **3,730 hours, $363,675** |

$363,675 is roughly **1.9 engineers**, recovered permanently, from a change
that costs nothing to make. And the hours are the smaller benefit: a written
update forces the author to have a position, and it can be read by someone
who was not invited, which is how context spreads in an org too big to fit
in a room.

**The rule that makes it stick:** a recurring meeting must have a decision
to make. If its purpose is for people to hear what happened, it is a
document. Audit every recurring meeting annually against that one test and
kill the ones that fail, rather than shortening them.

## Building the norms deliberately

Culture change is not announced, it is instrumented. Four levers, in
descending order of power:

| Lever | Mechanism | Example at ListUp | Time to effect |
|---|---|---|---|
| **What gets rewarded** | Promotion and calibration criteria | Add "publishes negative results" to the Staff PM bar | 1–2 cycles |
| **What gets tolerated** | What you let pass in review | Stop accepting launches without success criteria — in public, once | Immediate |
| **What you model** | Your own visible behaviour | VP publishes a written postmortem on a decision *they* got wrong | Immediate |
| **What you say** | Strategy memos, all-hands | Repeat the one-line strategy in every forum for a year | 2–4 quarters |

The second row is the fastest and the most uncomfortable. **Culture is
defined by the worst behaviour a leader walks past**, and the first time you
decline to walk past something is the moment the norm becomes real. Doing it
once, visibly, in a monthly product review, is worth more than a year of
memos.

## Worked example — ListUp's evidence norm

**Diagnosis:** 34% of experiments pre-registered, 2 negative results
published in a quarter, and a monthly product review where the team with the
best story consistently won the argument. The consequence was measurable in
Level 4, Module 1's org-health data: only 48% of launches had pre-set
success criteria, so nothing was ever falsified and the roadmap accumulated
features nobody could show worked.

**What was tried first, and failed:** a values memo on "evidence over
opinion", sent once, referenced by nobody after week two. Memos change what
people say, not what they do.

**What worked, over two quarters:**

| Change | Type | Detail |
|---|---|---|
| Launch template gained a mandatory criteria block | Artefact | The doc cannot be marked ready for review with it blank |
| Product review opens with last month's criteria vs actual | Ritual | Every team, every month, including the wins |
| "Learning of the month" award for a *disproven* hypothesis | Reward | Named in the all-hands; the first recipient was a Director |
| Pre-registration became a one-click template in the experiment tool | Friction | The default path became the compliant path |
| VP presented a personal decision that was wrong, with the data | Modelling | Went first, before asking anyone else to |
| Staff PM promotion bar amended | Reward | "Has changed their own mind publicly with evidence" |

**Result after two quarters:**

| Measure | Before | After |
|---|---|---|
| Experiments pre-registered | 34% | 91% |
| Negative results published per quarter | 2 | 11 |
| Launches with pre-set success criteria | 48% | 86% |
| Launches meeting their criteria | Not measurable | 44% |

That last row is the point, and it is the one that alarms executives who
have not thought it through. Before the change, every launch succeeded.
After it, **fewer than half** did — which was always true and is now simply
visible. A leadership team that treats 44% as a failure will destroy the
norm in a quarter; one that treats it as the first honest number the company
has ever had will compound on it for years.

## The things that quietly kill product culture

| Killer | Mechanism | Counter |
|---|---|---|
| Promoting the loudest | Confidence rewarded over calibration | Promotion packets require evidence of changed minds and measured outcomes |
| Punishing the messenger once | One public reaction ends escalation for a year | Thank the bearer, visibly, especially when the news is expensive |
| Hero culture | Praise for weekend rescues | Reward the boring prevention; ask why the rescue was needed |
| Roadmap as contract | Dates become promises to sales | Commit to outcomes and near-term dates; publish confidence bands |
| Silent standards | The bar exists only in the VP's head | Write the matrix; calibrate in a room, together |
| Hiring for culture "fit" | Reproduces the current org, including its blind spots | Hire for *values* alignment and *skill* difference |
| Under-managing a strong performer | One tolerated exception teaches everyone the rules are optional | The exception costs more than the performance is worth; act early |
| Re-orging to avoid a conversation | Structure used as a substitute for feedback | Have the conversation; keep the structure |

The last one is common at exactly this level and nearly always visible to
everyone except the person doing it.

## Culture at scale: the onboarding multiplier

At 37.9% growth ListUp will add roughly 30 R&D people next year — about 28%
of the org will have been there under a year. Norms do not transmit by
osmosis at that rate.

| Mechanism | What new joiners get in week 1 | Why |
|---|---|---|
| The strategy one-pager | The same page everyone else has | Removes the folklore version |
| Three decision records | Real ones, including a reversed decision | Teaches the format and the tolerance for being wrong |
| Two published postmortems | Real incidents, real detail | Proves blamelessness is not a slogan |
| A customer conversation | Booked before day 10 | Sets the direct-contact norm before habits form |
| A named buddy outside their team | Not their manager | Cross-group context, and someone safe to ask |

An onboarding pack made of real artefacts teaches culture faster than any
values deck, because it is evidence rather than assertion.

## Exercise

1. **Write down five norms you believe your org holds**, and name the
   artefact that encodes each. Delete every one you cannot attach an
   artefact to — those are aspirations.
2. **Name which of the four cultures you are**, which you need to be, and
   the single behaviour that would have to change first.
3. **Run the culture diagnostic**: pick eight countable behaviours, measure
   the baseline honestly, and publish the results to your leadership team.
4. **Audit your recurring meetings.** Count person-hours per year, cost them
   at a fully loaded hourly rate, and apply the one test: is there a
   decision to make? Convert the failures to documents.
5. **Identify the last thing you walked past** — the launch with no criteria,
   the missed commitment, the tolerated behaviour — and decide whether you
   will walk past it again.
6. **Change one artefact this month**, not one memo: a template field, a
   review agenda item, a default in a tool.
7. **Model the norm yourself first.** Present a decision you got wrong, with
   the data, before you ask anyone else to.
8. **Amend one promotion criterion** so that the behaviour you want is
   rewarded rather than merely praised, and take it through calibration.
9. **Build the week-1 onboarding pack** from real artefacts — three decision
   records, two postmortems, the strategy page — and compute what share of
   your org will be under a year tenured twelve months from now.
