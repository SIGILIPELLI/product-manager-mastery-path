# 01 · Leading Product Orgs

The hardest transition in a product career is not IC to manager. It is the
moment you stop being paid for the decisions you make and start being paid
for the decisions other people make. Your judgement stops being the output.
The **system that produces judgement** becomes the output — who is on which
team, what those teams are accountable for, what information reaches them,
and how disagreements get settled when you are not in the room.

Most new product leaders fail here in one of two symmetrical ways. They keep
doing the PM job, becoming a bottleneck on eight teams' decisions and a
frustration to eight PMs. Or they abandon judgement entirely, becoming a
scheduler of other people's meetings who cannot say what the product should
be. The job is neither: it is setting context tight enough that good
decisions become likely, and loose enough that people make them.

**Where ListUp is for the rest of Level 4:** $52.4M ARR, growing 37.9%;
6,150 direct accounts plus 214 agencies managing 3,900 more; 310 employees;
three product lines — Publish ($27.2M), Decide ($14.7M) and Console
($10.5M). The R&D org is 76 people: 52 engineers, 8 PMs, 8 designers, 6
engineering managers, 2 product ops, at 28.3% of revenue. You are VP
Product.

## What changes at each altitude

| | Senior PM | Group PM / Director | VP Product |
|---|---|---|---|
| **Output** | Product decisions | Your team's decisions | The org's decision quality |
| **Time horizon** | 1–2 quarters | 2–4 quarters | 1–3 years |
| **Main input** | Customers, data | Your PMs, peers in eng/design | Board, market, exec peers |
| **Main risk** | Wrong feature | Wrong team boundaries | Wrong strategy or wrong people |
| **How you scale** | Prioritise better | Delegate with context | Hire, design the org, set operating rhythm |
| **Failure mode** | Overcommitting | Becoming a super-PM | Becoming a scheduler |
| **What you must stop** | Doing design and QA yourself | Writing the PRDs | Making the calls your directors should make |

The most reliable test at any level: **how many decisions this week required
you specifically?** If the number keeps rising as the org grows, you have
built a hub-and-spoke org and you are the single point of failure.

## Org design: how you slice the teams *is* the strategy

Conway's Law is not a warning, it is a design tool. Your product will end up
shaped like your org chart, so pick the org chart that produces the product
shape you want.

| Slicing | Teams organised by | Best when | Cost |
|---|---|---|---|
| **Customer journey** | Acquire / activate / retain / expand | One product, growth-driven | Nobody owns feature depth |
| **Product line** | Publish / Decide / Console | Multiple products with distinct customers | Duplication; shared surfaces get orphaned |
| **Customer segment** | Self-serve / agency / enterprise | Segments need genuinely different products | The same feature built twice |
| **Job to be done** | Connect / decide / publish / verify | The product is a workflow | Boundaries blur as the workflow evolves |
| **Component / platform** | API / data / infra | Real shared infrastructure exists | Teams with no customer; queue behaviour |
| **Hybrid: value streams + platform** | Product groups plus an enabling platform group | 40+ engineers, multiple products | Requires an explicit platform-as-product contract |

Three principles that survive contact with reality:

1. **Optimise for the boundary that carries the most change traffic.** Put
   the seams where change is rare, not where the org chart looks tidy.
2. **A team should be able to ship to a customer without another team's
   sprint.** If it cannot, you have drawn a boundary through a workflow.
3. **Platform teams need a product contract**: named internal customers, a
   roadmap, an SLA and a way to be told no. Otherwise they become ticket
   queues and their best engineers leave.

## Worked example — ListUp's re-org

**Before:** 8 squads, each with a PM, formed opportunistically as the
company grew. Naming them tells you the problem immediately: Sync, Channels,
Rules, Model, Console, Onboarding, Billing, Reporting.

**Symptoms measured over one quarter**, which is what made the re-org a
decision rather than a preference:

| Symptom | Measurement |
|---|---|
| Cross-squad dependencies per quarter | 34, up from 19 a year earlier |
| Roadmap items blocked on another squad | 41% |
| Squads that could ship to a customer alone | 3 of 8 |
| Median time from decision to release | 6.2 weeks |
| VP Product hours per week in dependency arbitration | 9 |
| PM attrition, trailing 12 months | 2 of 8 |

With 8 peer squads there are 28 possible pairwise relationships, and
essentially all of them were live. The 9 hours a week of arbitration were
not a symptom of a weak PM bench — they were the arithmetic of the
structure.

**After:** three product groups plus a platform group, each led by a
Director or Group PM.

| Group | Squads | Engineers | Owns | Accountable for |
|---|---|---|---|---|
| **Publish** | Sync, Channels | 14 | Core publishing pipeline, marketplace adapters | Reliability, channel coverage, $27.2M line |
| **Decide** | Rules, Model | 15 | Recommendations, confidence, auto-apply | Attach, acceptance rate, $14.7M line |
| **Console** | Console, Onboarding | 13 | Agency workflow, approvals, reporting | Agency retention and expansion, $10.5M line |
| **Platform** | Data, Foundations | 10 | Event pipeline, API, identity, billing | Internal SLAs, external API, developer experience |

Grouping 8 squads as 3 / 3 / 2 turns 28 possible pairs into **7 intra-group
pairs and 21 cross-group pairs**. The intra-group ones are resolved by a
Director inside their own group. Only the cross-group ones reach you — and
in practice most run through Platform, which has an explicit contract rather
than an ad-hoc negotiation.

**Two quarters after:**

| Metric | Before | After |
|---|---|---|
| Cross-group dependencies per quarter | 34 | 12 |
| Roadmap items blocked on another team | 41% | 17% |
| Teams able to ship alone | 3 of 8 | 6 of 8 |
| Decision-to-release median | 6.2 weeks | 4.1 weeks |
| VP hours in arbitration | 9/week | 3/week |

**What got worse, stated plainly** — every re-org has a bill:

| Cost | Detail | Mitigation |
|---|---|---|
| Duplication | Console and Publish both built a bulk-edit grid | Design system ownership moved to Platform; one grid, two consumers |
| Orphaned surfaces | Search sat between three groups | Assigned to Publish with a written cross-group review |
| Local optimisation | Decide's attach KR pulled against Publish's reliability | Shared health metrics across groups (Level 3, Module 10) |
| Human cost | Two PMs lost scope; one left | Told individually, first, before the announcement — and it still cost one person |

**Re-org rules worth stealing:**

- **Measure the pain before, or you cannot prove the gain after.** The
  dependency count is the cheapest number to collect and the most persuasive.
- **Re-org at most annually.** The productivity dip is 4–8 weeks each time.
- **Tell affected people individually and first.** The all-hands is the
  third conversation, never the first.
- **Publish the new decision rights**, not just the boxes: who decides
  pricing, who decides API changes, who breaks a tie.

## Levelling and the competency matrix

You cannot hire, promote or develop consistently without a written matrix.
Four dimensions, five levels; here are the anchors that matter most.

| Dimension | PM | Senior PM | Staff / Group PM | Director | VP |
|---|---|---|---|---|---|
| **Scope** | A feature area | A product area | A product line or hard cross-cutting problem | A group and its P&L line | The product org and strategy |
| **Ambiguity** | Given a problem | Finds problems in their area | Defines which problems are worth solving | Sets the area's strategy | Sets the company's product strategy |
| **Influence** | Their squad | Squad plus adjacent teams | Cross-org without authority | Exec peers | Board, market, exec team |
| **Craft** | Writes clear specs, ships | Strong discovery and judgement | Sets the bar; others copy their artefacts | Builds the system that produces the craft | Hires and develops the leaders who do |
| **People** | — | Mentors | Mentors formally | Manages PMs | Manages managers |

Two rules that prevent most levelling arguments: **level on demonstrated
scope, not tenure or team size**, and **promote into the level someone is
already operating at**, never as an incentive to reach it.

## Hiring

| Element | Practice | Why |
|---|---|---|
| **Scorecard first** | Write the outcomes this hire owns in year 1 before opening the role | Prevents "we'll know it when we see it" |
| **Loop** | Portfolio review (past work), product sense, execution/prioritisation, analytics, cross-functional (an engineer and a designer as interviewers) | Each signal tested once, by someone who can judge it |
| **Written exercise** | A one-page memo on a real ambiguous problem, 90 minutes, paid if extensive | Writing is the job; almost nothing predicts as well |
| **Reference checks** | Two, done by you, asked about specific behaviours | The single highest-signal, most-skipped step |
| **Debrief** | Written positions before discussion, then discuss | Stops the loudest interviewer setting the anchor |
| **Bar** | "Would I want this person running my hardest problem in 18 months?" | Hiring below the bar compounds faster than any technical debt |

Ratios to sanity-check an org, not to obey: **6–8 engineers per PM** (ListUp
runs 6.5), **1 designer per PM** at product-led companies, **4–7 direct
reports** for a product manager of managers (ListUp Directors run 4), and
**1 product ops per 6–10 PMs**.

## The operating system you own

| Cadence | Forum | Your job in it |
|---|---|---|
| Weekly | Product leadership, 60 min | Unblock, decide the 2–3 things only you can |
| Weekly | Metrics review with eng and design leaders | Ask about the number that moved unexpectedly |
| Bi-weekly | 1:1 with each direct | Coaching, not status |
| Monthly | Product review — one group presents deeply | Raise the bar in public; model how to critique |
| Monthly | Skip-levels, 3 per month | Find out what your directors are not telling you |
| Quarterly | Planning, OKR grading, talent review | Own the trade-offs and the calibration |
| Quarterly | Written strategy memo to the company | Repetition is the job |
| Annually | Strategy refresh, org design review, comp calibration | The two or three decisions that set the year |

**The monthly product review is the highest-leverage hour you have.** How
you critique one team's work teaches every other team what the bar is —
which questions matter, which evidence counts, and whether it is safe to
present a result that disappointed you.

## Measuring the health of a product org

| Dimension | Metric | ListUp target |
|---|---|---|
| Autonomy | Decisions escalated to VP per week | Under 5 |
| Flow | Decision-to-release median | Under 5 weeks |
| Coupling | Cross-group dependencies per quarter | Under 15 |
| Quality | Share of launches meeting their pre-set success criteria | Over 50% |
| Learning | Experiments pre-registered; negative results published | Over 90%; monthly |
| Talent | Regretted PM attrition, trailing 12 months | Under 10% |
| Bench | Roles with a ready internal successor | Over 50% |
| Clarity | Random PM can state the strategy in one sentence | 100% |

The last row is measured by actually asking, in skip-levels, and writing
down what people say. The variance in those answers is the most accurate
measure of your communication that exists.

## Exercise

1. **Count your decisions.** For two weeks, log every decision that required
   you specifically. Categorise each as: only I could decide, someone else
   should have, or nobody needed to. Report the split.
2. **Measure your coupling.** Count cross-team dependencies last quarter, the
   share of roadmap items blocked externally, and how many teams can ship to
   a customer alone. Compute the number of pairwise team relationships your
   structure permits.
3. **Design two alternative org structures** for your product using different
   slicing principles. For each, state what gets easier, what gets
   duplicated, and which surface becomes orphaned.
4. **Write the platform contract** for one shared team: internal customers,
   roadmap, SLA, and how a customer team is told no.
5. **Write the competency matrix** across four dimensions and five levels,
   then place every PM on it. Note anyone operating a level above their
   title — those are your promotions — and anyone a level below, which is
   your hardest conversation this quarter.
6. **Write a hiring scorecard** for your next role: the outcomes it owns in
   year 1, the loop, who assesses what, and the written exercise.
7. **Draw your operating calendar** and mark which forums exist to *inform*
   you versus *develop* the org. If the first list is longer, redesign it.
8. **Set org health baselines** on all eight metrics, publish them to your
   leadership team, and put the re-measurement date in the calendar.
9. **Ask five people at random** to state the product strategy in one
   sentence. Write down all five answers verbatim. That variance is your
   real communication score.
