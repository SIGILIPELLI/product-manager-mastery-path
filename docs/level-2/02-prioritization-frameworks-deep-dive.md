# 02 · Prioritization Frameworks Deep Dive

In Level 1 you learned RICE and MoSCoW, which are enough to sort a backlog
of comparable items. They start failing on the decisions that actually cost
you a quarter: a feature everyone asks for that adds nothing to
satisfaction, a boring reliability fix that outranks the exciting bet, two
items with the same score and different risk profiles. This module adds
four tools for those cases — **weighted scoring** for multi-criteria
tradeoffs, **Kano** for what a feature does to satisfaction, **opportunity
scoring** for which problem to attack at all, and **WSJF / cost of delay**
for sequencing when timing matters more than size.

The meta-skill is knowing that a framework is a **conversation structure,
not a calculator**. Its job is to make disagreement specific. When two
frameworks rank the same list differently, that gap *is* the decision — and
this module ends by showing exactly that.

## Weighted scoring

RICE hard-codes one opinion about what matters. Weighted scoring makes your
criteria and their weights explicit, so you argue about the weights *once*,
in the open, instead of re-litigating every item.

**Steps:** pick 4–6 criteria → assign weights summing to 1.0 → score each
item 1–5 per criterion → total = Σ(score × weight).

| Criterion | Weight | 1 means | 5 means |
|---|---|---|---|
| Outcome impact | 0.35 | No plausible link to the quarter's outcome | Directly moves the outcome metric |
| Reach | 0.20 | Under 10% of active accounts | Nearly every active account |
| Confidence | 0.15 | One anecdote | Interviews + analytics + support agree |
| Effort (inverted) | 0.20 | Multi-quarter | Under a week |
| Strategic fit | 0.10 | Off-strategy; we'd have to explain it | Extends our stated wedge |

Two rules keep this honest. **Weights are set before items are scored** —
otherwise people reverse-engineer weights to favour a pet feature. And
**effort is inverted** so every criterion points the same way (higher =
better); mixing directions is the most common arithmetic error in homemade
scoring models.

## The Kano model

Kano classifies a feature by what it does to satisfaction — which is *not*
proportional to how loudly customers ask for it.

| Category | If present | If absent | Investment rule |
|---|---|---|---|
| **Must-be** | No credit | Deal-breaker | Meet the bar, stop. Polish buys nothing |
| **Performance** | Better, roughly linearly | Proportionally worse | Invest where you compete — this is the scoreboard |
| **Attractive** | Delight, disproportionate | Nobody notices | A few, deliberately. This is differentiation |
| **Indifferent** | Nothing | Nothing | Cut. This is where roadmaps quietly die |
| **Reverse** | Actively worse | Better without it | Remove, or make it optional |

You classify by asking each user a **question pair** about the same feature:

| Question | Answer options |
|---|---|
| *Functional:* "If ListUp showed a price-change preview before publishing, how would you feel?" | I like it / I expect it / I'm neutral / I can tolerate it / I dislike it |
| *Dysfunctional:* "If ListUp did **not** show a price-change preview, how would you feel?" | (the same five) |

The pair maps to a category: *like it* + *dislike its absence* =
**Performance**; *like it* + *neutral about its absence* = **Attractive**;
*expect it* + *dislike its absence* = **Must-be**; *neutral* + *neutral* =
**Indifferent**.

The decay rule matters more than any single classification: **attractive
features become performance features, then must-be features**, usually
within a few years. Re-run Kano on your core set roughly annually, or you
will keep paying delight prices for table stakes.

## Opportunity scoring

Kano and weighted scoring rank *solutions*. Opportunity scoring tells you
which **problem** deserves a solution. Survey users on two 1–10 scales per
job step — how **important** it is, and how **satisfied** they are with
today's options:

**Opportunity = Importance + max(Importance − Satisfaction, 0)**

Roughly: above 10 is underserved, below 7 is served — and often *over*-served,
which is a signal to cut investment, not add.

| Job step | Importance | Satisfaction | Opportunity | Read |
|---|---|---|---|---|
| Trust that a price edit reached every channel | 9.1 | 4.2 | **14.0** | Badly underserved — fund it |
| Connect a second marketplace quickly | 8.2 | 5.1 | **11.3** | Underserved |
| Import without losing my own notes | 7.4 | 5.8 | **9.0** | Borderline |
| Bulk-edit listing titles | 6.0 | 5.9 | **6.1** | Served — stop investing |

## Cost of delay and WSJF

Everything above ranks by value and size. None of it asks what it costs to
ship *later*. **Cost of delay (CoD)** is value lost per unit of delay, and
**WSJF = CoD ÷ job size** sequences work so total delay cost is minimized.

| CoD component | Question | Scale |
|---|---|---|
| User/business value | What do we lose per month without it? | 1–10 |
| Time criticality | Does the value decay? Is there a fixed date? | 1–10 |
| Risk reduction / opportunity enablement | Does it unblock later work or kill a big unknown? | 1–10 |

Score in **relative** terms (1, 2, 3, 5, 8, 13). WSJF only needs the
ranking to be right, not the units.

| Item | Value | Time crit. | Risk/enable | CoD | Job size | WSJF |
|---|---|---|---|---|---|---|
| Sync failure alerts | 5 | 8 | 2 | 15 | 2 | **7.5** |
| Pre-publish diff preview | 8 | 5 | 8 | 21 | 5 | **4.2** |
| CSV column mapper | 3 | 1 | 2 | 6 | 3 | **2.0** |
| OAuth marketplace connect | 5 | 3 | 3 | 11 | 8 | **1.4** |

## Choosing a framework

| Situation | Use | Why |
|---|---|---|
| Comparable items, one team, one quarter | RICE | Fast, one number, everyone knows it |
| Stakeholders disagree about *what matters* | Weighted scoring | Forces the weights argument into the open, once |
| "Customers asked for it" is driving the roadmap | Kano | Separates asked-for from satisfaction-moving |
| You don't know which problem to attack | Opportunity scoring | Ranks outcomes, not features |
| Fixed dates, decaying value, dependencies | WSJF | The only one that prices *lateness* |
| Two options, high stakes, thin data | None — run an assumption test | A score cannot manufacture evidence |

## Worked example — ListUp

Five candidate solutions from the opportunity solution tree in Module 1,
run through three frameworks over the same quarter.

**RICE** — Reach = accounts touched per quarter, Impact 0.25–3, Effort in
person-months, score = R × I × C ÷ E:

| Item | R | I | C | E | Score |
|---|---|---|---|---|---|
| Sync failure alerts | 2,400 | 0.5 | 100% | 0.5 | **2,400** |
| Pre-publish diff preview | 1,800 | 2.0 | 80% | 2.0 | **1,440** |
| Sync status badge | 2,400 | 1.0 | 80% | 1.5 | **1,280** |
| CSV column mapper | 900 | 1.0 | 100% | 1.0 | **900** |
| OAuth marketplace connect | 1,500 | 2.0 | 50% | 3.0 | **500** |

**Weighted scoring** with the weights above (1–5, effort already inverted):

| Item | Impact ×.35 | Reach ×.20 | Conf ×.15 | Effort ×.20 | Fit ×.10 | Total |
|---|---|---|---|---|---|---|
| Pre-publish diff preview | 5 | 4 | 4 | 3 | 5 | **4.25** |
| Sync status badge | 3 | 5 | 4 | 4 | 3 | **3.75** |
| Sync failure alerts | 2 | 5 | 5 | 5 | 3 | **3.75** |
| OAuth marketplace connect | 4 | 3 | 3 | 2 | 4 | **3.25** |
| CSV column mapper | 2 | 2 | 5 | 5 | 2 | **3.05** |

**The frameworks disagree, and that is the finding.** RICE and WSJF both
put *sync failure alerts* first; weighted scoring puts *diff preview*
first. The gap has one cause: RICE multiplies broad reach by cheap effort,
rewarding a small change that touches everyone, while the weighted model
puts 45% of its weight on outcome impact and strategic fit — where alerts
score 2 and 3.

Kano settles it. From a 40-seller survey:

| Feature | Modal functional / dysfunctional answer | Category |
|---|---|---|
| Sync failure alerts | "I expect it" / "I dislike its absence" | **Must-be** |
| Pre-publish diff preview | "I like it" / "I'm neutral" | **Attractive** |
| CSV column mapper | "I'm neutral" / "I'm neutral" | **Indifferent** |

Must-be features never raise satisfaction — but their absence caps it. So
the decision isn't *which one*, it's **sequence**: ship alerts first,
because it is a half-person-month must-be that is currently missing and you
cannot buy delight below the floor; then spend the rest of the quarter on
the diff preview, the only attractive-category item and the only one
scoring 5 on the quarter's outcome. The CSV mapper — the highest-confidence
item in the RICE table — gets cut, because Kano says nobody will notice it.
Confidence that a feature will *land* is not evidence that it *matters*.

## Exercise

Take your own backlog (or ListUp's five candidates) and produce:

1. **A weighted scoring model**: 4–6 criteria with weights summing to 1.0,
   each with written definitions of what 1 and 5 mean. Get one stakeholder
   to agree to the weights *before* anything is scored, and note where they
   pushed back.
2. **Rankings from two frameworks** over the same 5+ items (weighted scoring
   plus RICE or WSJF). Wherever the rankings differ, write one sentence
   naming the specific input that caused the difference.
3. **A Kano question pair** for your top three items, run past at least five
   users. Classify each and state what the classification changes.
4. **An opportunity score table** for 4+ steps of your users' main job.
   Name one over-served step you should stop investing in, and where that
   capacity goes instead.
5. **A one-paragraph decision memo**: what you're building, what you're
   cutting, and — most importantly — which framework you *overruled* and
   why.
