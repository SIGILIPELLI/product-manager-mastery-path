# 04 · M&A and Product Integration

At some point a corp dev deck lands in your inbox with two days' notice and
a request for "the product view". This is one of the few moments where a
product leader's judgement is worth tens of millions of dollars and where
being unprepared is very visible. It is also where the most reliable
statistic in business applies: **most acquisitions destroy value**, and they
do it in ways that are entirely predictable from the diligence stage.

Your job in an acquisition is not to be enthusiastic. It is to be the person
who asks what specifically gets better for a customer, when, and what it
costs to make that true — and who says the uncomfortable thing while it is
still cheap to say.

## First: is buying even the right instrument?

| | Build | Buy | Partner |
|---|---|---|---|
| **Cost profile** | Predictable, mostly people | Large, up front, plus integration | Low, ongoing revenue share |
| **Time to value** | 12–24 months | 3–9 months, if integration goes well | 1–3 months |
| **Control** | Total | High, degrades if the team leaves | Low |
| **Learning retained** | All of it | Only if the team stays | Little |
| **Main risk** | Too slow; opportunity lost | Overpay; team leaves; integration stalls | Partner's roadmap and survival |
| **Use when** | Core to the strategy, and you have time | The gap is capability plus market, and time matters | Adjacent, not core |

**The default should be build**, and buying should have to beat it on an
argument you can write down. The honest reason to buy is usually one of
three: time, a team you cannot hire, or customers you cannot reach.

## Deal rationales, and what each one really costs

| Rationale | You're buying | Integration difficulty | Most common failure |
|---|---|---|---|
| **Acqui-hire** | A team | Low — no product to merge | Team leaves after the vesting cliff |
| **Product / capability** | Working technology and its team | Medium | Stack incompatibility; a rewrite nobody budgeted |
| **Market / customers** | An installed base | High | The customers were loyal to the acquired company, not the product |
| **Technology / IP** | Something hard to replicate | Medium | The advantage was the team, not the code |
| **Defensive** | Denying a competitor | High | You now own something you did not want |
| **Consolidation** | Cost synergies | Very high | The synergies are people, and people leave |

Say the rationale in one sentence before diligence starts. Deals with three
rationales usually have none.

## Product diligence checklist

You have two to four weeks and limited access. Prioritise the questions
whose answers would change the price or kill the deal.

| Area | Questions that change the decision |
|---|---|
| **Customers** | Concentration — top 10 as % of ARR? Logo and revenue churn by cohort? How many are also our customers? |
| **Revenue quality** | Contracted vs usage? Discounting? Any revenue tied to founder relationships? |
| **Product** | What actually works vs what is demoed? Feature usage distribution — how much of the product is dead? |
| **Architecture** | Multi-tenant or per-customer forks? Data model compatibility with ours? Rewrite required to integrate? |
| **Data** | Rights to use customer data for models? Residency and consent? Anything that blocks combining datasets? |
| **Team** | Who are the 3–5 people the product cannot survive losing? Are they vested? What do they want next? |
| **Roadmap** | What have they promised customers in writing, with dates? |
| **Debt** | Unplanned work ratio; change failure rate; on-call load (Level 3, Module 9) |
| **Security / compliance** | Certifications, open findings, incidents in the last 24 months |
| **Ecosystem** | Integrations, partners, anything that breaks when they change ownership |

**The single most predictive diligence question:** *which three people must
stay, and have you actually asked them what they want?* Product acquisitions
fail on people far more often than on technology.

## Worked example — ListUp acquires Pricewell

**Target.** Pricewell, an AI-native repricing startup: $3.1M ARR growing
94%, 24 employees (11 engineers), 140 customers, a materially better pricing
model than ListUp's Decide line, and no publishing capability at all.

**Rationale, in one sentence:** *buy 18 months of model maturity and the
team that built it, for a capability that is already our fastest-growing
line.*

**Build alternative, costed:** 9 engineers for 20 months = 690
engineer-weeks at $3,804 = **$2,624,760** — and ListUp does not have 9 spare
engineers, so it also costs a year of Decide's roadmap. **Price asked:**
6× ARR = **$18,600,000**.

The build option is seven times cheaper and that is exactly why the
comparison must be about *time*, not cost. The only question that matters:
what is 18 months of acceleration worth on a line growing 71% off a $14.7M
base?

**The naive model, and why it is a trap.** Assume Pricewell's model lifts
Decide's growth from 71% to 92% this year and 58% to 74% next year. Decide
in two years: **$49,109,760** with the acquisition against **$39,716,460**
organically — a $9,393,300 acceleration. Add Pricewell's own ARR compounding
to $7,192,000 and you get $16,585,300 of incremental ARR, worth
**$132,682,400** at ListUp's 8× multiple, against an $18.6M price.

A model that says a deal creates $114M of value is not a good model. It is
an unfalsifiable one, and it will be used to justify any price. Two
disciplines fix it:

1. **Attribution.** Decide was going to improve anyway. Only a fraction of
   the acceleration is caused by the acquisition, and that fraction is a
   variable, not an assumption.
2. **Scenarios with probabilities**, including a real failure case where the
   answer is negative.

**The model that should go to the board:**

| Scenario | P | Acquired ARR at yr 2 | Attribution of acceleration | Accel. ARR | ΔARR | EV at 8× | Net value |
|---|---|---|---|---|---|---|---|
| Failure | 15% | $900,000 | 0% | $0 | $900,000 | $7,200,000 | **−$13,900,000** |
| Downside | 25% | $3,200,000 | 15% | $1,408,995 | $4,608,995 | $36,871,960 | +$16,319,548 |
| Base | 40% | $7,192,000 | 40% | $3,757,320 | $10,949,320 | $87,594,560 | +$67,042,148 |
| Upside | 20% | $8,500,000 | 70% | $6,575,310 | $15,075,310 | $120,602,480 | +$100,050,068 |
| **Weighted** | | | | | | | **+$48,821,760** |

Net value is EV minus the $18.6M price minus integration cost ($1,952,412 in
most scenarios: 5.5 engineer-years of integration plus $990,000 of retention
bonuses; $2.5M in the failure case, where you pay the costs and get nothing).

The deal is worth doing. It is worth doing **because a 15% chance of losing
$13.9M is acceptable against this expected value** — and the board should be
shown that sentence, not the $132M headline.

**Diligence findings that changed the deal:**

| Finding | Impact | Deal response |
|---|---|---|
| Top 3 customers = 31% of ARR, all founder-sourced | Revenue quality much worse than headline | $2.4M of the price moved into an earn-out on 18-month retention |
| 41 of 140 customers already use ListUp | Overlap is a synergy *and* a churn risk on double-billing | Migration plan and combined pricing agreed pre-close |
| Model trained on data with unclear consent for cross-customer use | Could block the whole point of the deal | Legal review; retraining plan on ListUp's own 4.1M labelled changes |
| Single-tenant deployment per customer | 140 migrations, not a switch | Integration re-estimated from 3 to 5.5 engineer-years |
| 3 of 11 engineers already interviewing | The team is the asset | Retention packages agreed before signing, not after |

The fourth row is the classic one. A demo does not reveal deployment
architecture, and a single-tenant target is a multi-year integration
disguised as a product purchase.

## Integration models

| Model | What happens | Use when | Cost |
|---|---|---|---|
| **Standalone** | Keeps its brand, product, team | Different customer or market; thesis is financial | Low integration cost, near-zero synergy |
| **Tuck-in** | Product becomes a feature; team joins a group | Capability buy | Medium |
| **Full integration** | One product, one data model, one roadmap | Same customer, overlapping product | High, and the only route to real synergy |
| **Absorb and sunset** | Customers migrated, product retired | Acqui-hire or defensive | High customer risk |

ListUp chose **full integration into the Decide group**, because the thesis
was capability and the customer is the same. That choice commits to the 5.5
engineer-years, and it should be made explicitly at signing rather than
drifted into over a year.

**Day 1 / Day 100:**

| Horizon | Must be true |
|---|---|
| **Day 1** | Everyone knows who their manager is; no product changes announced; customers hear it from a named human, not a press release; retention packages already signed |
| **Week 2** | Combined roadmap drafted; the 3 must-keep engineers have a written scope they want |
| **Day 30** | Migration plan published for the 41 overlapping customers, with a combined price that never increases anyone's bill at the point of migration |
| **Day 60** | First joint capability shipped — something small and visible, to prove the thesis internally |
| **Day 100** | Single roadmap, single on-call, single metric set; Pricewell's brand retired or explicitly kept, decided not drifted |
| **Month 18** | Earn-out measured; retention of the acquired team and ARR reported honestly against the model above |

**The most under-rated Day 1 item:** nobody at the acquired company should
learn about a product decision from a slide. Give the acquired PMs real
scope in week one. The signal that they have been demoted travels faster
than any integration plan.

## How these deals fail

| Failure | Mechanism | Prevention |
|---|---|---|
| **Synergy fiction** | Attribution set to 100% in the model | Attribution as an explicit variable, with a failure scenario |
| **Team exodus** | Acquired leaders lose scope and leave at the cliff | Written scope in week one; retention tied to outcomes, not just time |
| **Integration drift** | No decision on the integration model, so it stays standalone forever | Decide at signing; fund it as a named initiative |
| **Customer churn on migration** | Bills change, feature parity gaps | Never raise a bill at migration; publish the parity gap honestly |
| **Roadmap freeze** | Both products stop shipping during integration | Ring-fence one team on each side to keep shipping |
| **Culture mismatch** | Two operating systems, unresolved | Pick one operating cadence in month one, and say which |
| **Data rights** | The dataset you bought cannot legally be combined | Diligence question, not a post-close discovery |

## Exercise

1. **Write the build/buy/partner comparison** for a capability gap your
   product has: cost, time to value, control, risk, and the one-sentence
   condition under which each is right.
2. **Cost the build option properly** in engineer-weeks and dollars, and add
   the opportunity cost of what those engineers stop doing.
3. **State the acquisition rationale in one sentence.** If you need three,
   write down why each one alone is insufficient.
4. **Write your product diligence list**, prioritised so the top five
   questions are the ones that would change the price or kill the deal.
5. **Build the scenario model** with at least four scenarios including a real
   failure case, an explicit attribution variable, integration costs, and
   probability weights. Report the weighted value and the downside.
6. **Stress the attribution.** Recompute at 0% attribution — that is, the
   value of the acquired business alone. If the deal only works at high
   attribution, say so plainly.
7. **Name the three people the product cannot survive losing** and write what
   you would offer each: scope, reporting line, and money, in that order.
8. **Choose the integration model at signing** and write the Day 1 / Day 100
   plan with the owner for each milestone.
9. **Write the honest month-18 review** in advance: the table you will fill
   in, comparing acquired ARR, retention of the team, and realised
   attribution against this model.
