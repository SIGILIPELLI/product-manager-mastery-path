# 09 · Pricing Basics

Pricing is the fastest lever you own and the one you are least likely to be
invited to pull. A 10% price increase drops almost entirely to the bottom
line; a 10% improvement in acquisition costs money to get and decays the
moment you stop spending. Yet pricing usually sits in a drawer marked
"finance" or "the founders decided that in 2021", and the PM who owns the
product doesn't own the number attached to it.

That's a mistake, and it's usually yours to fix. Pricing is a **product
decision wearing a finance costume**. What you charge for determines which
customers you attract, which behaviours you encourage, what your roadmap is
allowed to be, and whether the feature you just shipped can ever be
monetised. The PM is the only person in the building who knows all of: what
the product does, who values which part of it, and what it costs to serve.
Nobody else can pick the value metric.

This module covers value metrics, packaging, willingness-to-pay research,
discounting, and the arithmetic you need before you can argue for a price
change without being talked out of it.

## Start with the value metric, not the number

The **value metric** is the unit you charge by. Choosing it is a bigger
decision than choosing the price, because the price can be changed next
quarter and the value metric usually can't — it's wired into your billing
system, your contracts, and your customers' mental model.

A good value metric passes four tests:

| Test | Question | Fails if |
|---|---|---|
| **Aligned** | Does the customer's bill grow as they get more value? | Charging by API call when value comes from accuracy, not volume |
| **Predictable** | Can the customer forecast next month's bill? | Pure usage metrics that spike without warning |
| **Countable** | Can both sides agree on the number without arguing? | "Monthly active contributors" with a fuzzy definition |
| **Expandable** | Does it grow naturally as the account succeeds? | Flat per-company fee — a customer 10× larger pays the same |

Common metrics, and what each one quietly optimises for:

| Value metric | Best when | Encourages | Watch out for |
|---|---|---|---|
| Per seat | Value scales with people using it | Adding users | Seat-sharing; teams that get value from few users |
| Per usage unit (API call, message, GB) | Value scales with volume | Efficiency — customers optimise you away | Bill shock; unforecastable revenue |
| Per business outcome (orders, revenue processed) | Your value is directly attributable | Customer growth = your growth | Requires trust; hard to meter fairly |
| Per capacity tier (SKUs, channels, records) | Value scales with the size of the thing managed | Consolidating onto you | Customers gaming the count |
| Flat per account | Simple products, small deals | Nothing | Leaves money on the table at the top end |
| Hybrid (platform fee + usage) | Mixed value, mature markets | Commitment plus growth | Complexity in the sales conversation |

For ListUp — a listing manager for multi-channel e-commerce sellers — seats
fail the alignment test (a solo seller with 4,000 SKUs gets far more value
than a three-person team with 80), and pure usage fails predictability. The
capacity metrics that actually track value are **channels connected** and
**SKUs managed**.

## Packaging: good, better, best

Once you have a value metric, packaging decides who lands where. The
standard three-tier structure works because it converts a yes/no decision
("should I buy?") into a which-one decision.

| Tier role | Job | Design rule |
|---|---|---|
| **Good** | Remove the reason not to start | Genuinely useful alone; capped by the value metric, not crippled by removing basics |
| **Better** | Where most customers should land | Contains the features the *majority* of your ICP names as must-have; price it as the obvious default |
| **Best** | Capture the top of the market | Control, scale, trust and admin features; a small number of accounts, a large share of revenue |

**Fencing** is how you keep tiers apart. The fence must map to the
customer's own sense of "I'm bigger now":

| Fence type | Example | Good fence? |
|---|---|---|
| Capacity | 300 SKUs vs 2,500 vs 25,000 | Yes — grows with the customer |
| Feature | Audit log, SSO, roles | Yes, for admin and trust features only larger orgs need |
| Segment | Non-profit or education pricing | Yes, if verifiable |
| Support level | Email vs priority vs named CSM | Yes, if the levels are real |
| Arbitrary crippling | CSV export locked behind the top tier | No — reads as punishment; drives churn and resentment |

Rule of thumb for tier spacing: each tier roughly **2.5–3× the price of the
one below**. Closer than 2× and customers feel nickel-and-dimed by upgrades;
wider than 4× and the jump becomes a wall that stalls expansion.

## Finding willingness to pay

You cannot ask "what would you pay?" and believe the answer. These four
methods are what real pricing work uses, in increasing order of cost.

| Method | What it gives you | Sample needed | Effort | Main weakness |
|---|---|---|---|---|
| **Win/loss and discount data** | What you *actually* clear, and where deals stall | Your existing pipeline | Low | Only covers people who already talked to you |
| **Van Westendorp (4 questions)** | An acceptable price *range* | 60–150 per segment | Low | A range, not a revenue-maximising point |
| **Gabor-Granger (price ladder)** | A demand curve and a revenue-maximising point | 100–200 per segment | Medium | Tests price in isolation from packaging |
| **Conjoint analysis** | Which features drive willingness to pay, and by how much | 200–400 per segment | High | Needs a specialist; slow |

**Van Westendorp** asks the same respondent four questions about a described
product: at what price is it *too cheap* (you'd doubt the quality), *a
bargain*, *getting expensive*, and *too expensive to consider*. The overlap
of the resulting curves gives a plausible band.

**Gabor-Granger** shows a single price and asks purchase intent, then walks
the price up or down. Multiply price by the share who'd still buy to get a
revenue index — the peak is your revenue-maximising point for that package.

The most under-used source is the free one: your **discount ledger**. If
sales discounts an average of 18% to close, your list price is 18% too high
*for that segment* — or your packaging is putting the wrong things in the
wrong tier.

## The arithmetic you must be able to do in a meeting

Two calculations settle most pricing arguments.

**1. Breakeven volume for a price change.** With a contribution margin of
*m*% and a price increase of *x*%, you can lose `x / (m + x)` of your volume
before you're worse off. At ListUp's 78% gross margin:

| Price change | Breakeven volume move |
|---|---|
| +5% | Can lose 6.0% of accounts |
| +10% | Can lose 11.4% |
| +20% | Can lose 20.4% |
| +30% | Can lose 27.8% |
| −10% | Must gain 14.7% |
| −20% | Must gain 34.5% |

Note the asymmetry. Price increases are forgiving; price cuts are brutal. A
20% discount needs a 34.5% volume increase just to stand still — which is
why "let's lower the price to grow" is almost always wrong for a software
product with high gross margins.

**2. Payback and LTV/CAC.** At $79/mo, 78% gross margin, 3% monthly logo
churn and a $600 blended CAC:

| Quantity | Calculation | Result |
|---|---|---|
| Expected lifetime | 1 / 0.03 | 33.3 months |
| Monthly gross profit | $79 × 0.78 | $61.62 |
| Lifetime value | $61.62 × 33.3 | $2,054 |
| CAC payback | $600 / $61.62 | 9.7 months |
| LTV / CAC | $2,054 / $600 | 3.4× |

The usual bars are LTV/CAC above 3× and payback under 12 months. Both are
met here — but a 20% discount cuts monthly gross profit to $49.30, pushing
payback to 12.2 months and the ratio to 2.7×. **A discount is not a
marketing expense; it is a permanent reduction in the value of that
customer.** Twenty percent off $79 gives up $189.60 per account per year.

## Worked example — ListUp moves from one price to three tiers

**Situation.** ListUp has 1,240 paying accounts on a single $49/mo plan —
$60,760 MRR, $729,120 ARR. Two symptoms say the pricing is wrong: the
largest accounts (4+ channels, thousands of SKUs) are visibly underpaying
and never churn, while trial-to-paid conversion among solo sellers with two
channels sits at half the rate of everyone else. $49 is simultaneously too
low and too high.

**Value metric chosen:** channels connected × SKUs managed. Both track value
directly, both are countable from data ListUp already stores, and both grow
as the seller's business grows.

**Research.** A Gabor-Granger ladder run with 180 sellers matching the
Growth profile:

| Price | Would buy | Revenue index (price × share) |
|---|---|---|
| $39 | 64% | 24.96 |
| $59 | 52% | 30.68 |
| **$79** | **40%** | **31.60** |
| $99 | 24% | 23.76 |
| $129 | 12% | 15.48 |

The revenue index peaks at $79. Note it is nearly flat between $59 and $79 —
a real finding, not a rounding artefact. The segment is not very price
sensitive across that band, so the extra $20 is close to free. Van
Westendorp on the same segment gave an acceptable band of roughly $49–$99,
consistent with the ladder.

**Resulting packaging:**

| Tier | Price | Fences | Who it's for |
|---|---|---|---|
| Starter | $29/mo | 2 channels, 300 SKUs | Solo sellers testing a second channel |
| Growth | $79/mo | 6 channels, 2,500 SKUs, pre-publish diff preview | The default — sellers whose pricing errors cost real money |
| Pro | $199/mo | Unlimited channels, 25,000 SKUs, roles, audit log, priority support | Agencies and sellers with staff |

Spacing is 2.7× and 2.5× — inside the guideline. The diff preview sits in
Growth because it is the feature that separates "this is a side project"
from "a wrong price costs me money", which is exactly the moment a seller
should graduate.

**Modelled outcome.** Mapping the existing base onto the new tiers by their
actual channel and SKU counts gives 471 Starter (38%), 583 Growth (47%),
186 Pro (15%).

| | Today | After |
|---|---|---|
| MRR | $60,760 | $96,730 |
| ARR | $729,120 | $1,160,760 |
| ARPA | $49.00 | $78.01 (+59%) |

**The number that makes it defensible:** blended ARPA rises 59%, so the
change is revenue-neutral even if you lose **37.2%** of the base — you need
only 62.8% retention (49 / 78.01) to break even. Nobody expects to lose a
third of their customers to a repricing, and stating that ceiling out loud
is what converts a nervous conversation into a decision.

**Migration plan** — the part that actually determines whether this works:

| Decision | Choice | Why |
|---|---|---|
| Existing accounts | Grandfathered at $49 for 12 months, then moved to their mapped tier | Buys goodwill; avoids a churn spike in the quarter you change |
| Accounts that would *lose* capability | None — grandfathered limits held at current usage +25% | Never take something away from a paying customer |
| Annual prepay | 12 months for the price of 10 (16.7% discount) | Cash up front; measurably lower churn |
| New accounts | New pricing immediately | Clean measurement — new-cohort conversion is the real read |
| Announcement | 60 days' notice, email plus in-app, from the founder | Surprise generates the angry thread, not the price |

**What to watch after launch:** new-cohort trial-to-paid by tier (the real
test of the $29 entry point), Starter→Growth upgrade rate at 90 days (the
test of the fence), and grandfathered-cohort churn at the 12-month mark (the
test of the migration).

## Common pricing mistakes

| Mistake | Why it happens | What to do instead |
|---|---|---|
| Cost-plus pricing | Feels objective | Price to value; cost sets a floor, not a price |
| Pricing to the loudest competitor | Easy to justify | Price to your differentiated value; match only where you're undifferentiated |
| Never raising prices | Fear of churn | Small annual increases on new cohorts; the breakeven table shows the room |
| Discounting to hit a quarter | Sales pressure | Trade the discount for something: annual term, case study, reference call |
| Putting the best feature in the cheapest tier | Wanting everyone to love it | Put it in the tier you want people to land in |
| Changing price without changing packaging | Simplest to ship | A packaging change gives customers a story; a bare increase gives them a grievance |

## Exercise

Take a product you know well — yours, or one you use daily — and produce a
pricing proposal:

1. **Value metric.** Name the current one, then score two candidate metrics
   against the four tests (aligned, predictable, countable, expandable).
   State which you'd choose and what would break if you changed it.
2. **A three-tier package table** with prices, fences, and the target
   customer for each tier. Check your spacing sits between 2× and 4×, and
   justify why each fenced feature is where it is.
3. **A research plan.** Which of the four methods you'd run, in what order,
   with what sample size, and what decision each result would change.
   Include what your discount ledger or win/loss data already tells you.
4. **The arithmetic.** Using your product's gross margin, build the
   breakeven table for +10%, +20% and −10% price moves. Then compute LTV,
   CAC payback and LTV/CAC at your proposed middle-tier price — and the same
   three numbers under a standard 20% discount.
5. **A migration plan** for existing customers covering: grandfathering
   period, what happens to accounts that would lose capability, notice
   period, and who sends the announcement.
6. **A kill criterion.** Write the specific number that would make you
   revert the change, and the date you'd measure it on.
