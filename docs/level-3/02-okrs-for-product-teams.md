# 02 · OKRs for Product Teams

Most product teams have OKRs. Very few have OKRs that change what anybody
does. The tell is simple: if your quarter would have looked identical
without them, they were a reporting exercise, not a planning one.

OKRs are the translation layer between the three-year strategy you wrote in
Module 1 and the twelve weeks in front of you. Their real job is not
motivation, and it is definitely not performance management. It is
**forcing a small number of numeric commitments so that everything else
becomes negotiable**. When a stakeholder asks for the audit log in week
six, an OKR set lets you answer "yes, if it moves KR2 — otherwise it lands
in Q3", which is a conversation, rather than "we're pretty busy", which is
a plea.

This module covers OKR anatomy, how to set a target you can defend, the
difference between output and outcome KRs, cadence, grading, and the six
ways product teams break them.

## Anatomy

| Element | Question | Count | Rule |
|---|---|---|---|
| **Objective** | What are we trying to achieve, in plain language? | 2–3 per team per quarter | Qualitative, memorable, no numbers |
| **Key result** | How will we know we achieved it? | 2–4 per objective | Numeric, with a baseline, a target and a date |
| **Initiative** | What we'll do to move the KR | Any number | Never a KR; these are your bets, not your commitments |
| **Health metric** | What must not get worse while we chase this | 1–2 per objective | Guardrail; breaching it cancels the win |

The most common single error in product OKRs is putting an initiative in
the key-result slot.

| Written as | Actually a | Fix |
|---|---|---|
| "Ship repricing to GA by March 31" | Initiative — a date on a deliverable | "90 Pro accounts have at least one repricing rule live" |
| "Run 12 experiments" | Activity count | "Lift trial-to-paid from 22% to 26%" |
| "Improve onboarding" | Aspiration | "Day-7 activation rises from 41% to 50%" |
| "Reduce p95 latency" | Direction with no target | "p95 sync latency under 4 min for 30 consecutive days" |

The test: **could you hit the KR and still have failed?** If shipping to GA
and nobody enabling it counts as a win, it is an initiative.

## Choosing key results that are worth committing to

A good KR set covers more than one dimension of the same outcome, so it
cannot be gamed by pushing a single lever.

| KR type | Measures | Example | Gaming risk if used alone |
|---|---|---|---|
| **Adoption** | Did people turn it on? | Accounts with a live rule | Force-enable it for everyone |
| **Depth / engagement** | Are they really using it? | % of price changes originating from a recommendation | Drive volume of low-value changes |
| **Quality** | Is it good? | Suggestion acceptance rate | Only suggest the obvious |
| **Business** | Did it pay? | Growth→Pro upgrades per quarter | Discount your way there |
| **Health (guardrail)** | What must not break? | Zero mis-published prices attributable to repricing | — |

Pair at least one adoption KR with one quality KR. That pairing is what
stops the team from shipping a feature everyone enables once and nobody
trusts.

### Setting the target number

| Step | Method | Example |
|---|---|---|
| 1. Baseline | Measure the last 4–8 weeks. No baseline, no KR. | Growth→Pro upgrades ran 11/quarter |
| 2. Trajectory | What happens if you do nothing? | ~12, with normal growth |
| 3. Mechanism | What specific change produces the lift, and how much? | In-app upgrade prompt on the repricing paywall; comparable prompt lifted a similar flow 2.4× |
| 4. Target | Trajectory × mechanism, rounded to a number you can say out loud | 30 |
| 5. Confidence | State it at set time: 50% for aspirational, 80% for committed | 60% |

A target with no mechanism behind it is a wish. If you cannot answer step 3,
the honest KR is a learning KR for one quarter: "determine the upgrade
conversion rate of the paywall prompt across 400 exposures."

## Commit vs aspirational

| Type | Confidence at set time | Good grade | Consequence of missing |
|---|---|---|---|
| **Committed** | ~80–90% | 1.0 | Genuinely bad; something is wrong with planning |
| **Aspirational** | ~50% | 0.6–0.7 | Expected; the point was the stretch |

Label each KR. Mixing them silently is how a team either sandbags
everything or gets punished for ambition. And never tie either type to
compensation — the moment bonus depends on the grade, every target becomes
one the team already knows it can hit.

## Cadence

| Ritual | When | Length | Output |
|---|---|---|---|
| Draft | 2 weeks before quarter start | — | PM drafts from strategy; team red-teams it |
| Set | Week 1 | 90 min | Confidence recorded per KR |
| Weekly check-in | Every Monday | 15 min | Confidence updated; blockers named |
| Mid-quarter review | Week 6 | 45 min | Explicit decision: keep, re-target, or drop a KR |
| Grade + retro | Week 13 | 60 min | Scores, written read, carry-over decisions |

The week-6 review is the one people skip and the one that matters. A KR that
is clearly unreachable by week 6 should be dropped in writing with a reason,
not quietly carried to a week-13 post-mortem.

## Worked example — ListUp Q1

These follow directly from the strategy in Module 1: own the decision, build
the agency channel, move revenue toward Pro. Three objectives, eight key
results.

**Objective 1 — Sellers start trusting ListUp to propose prices.**

| KR | Baseline | Target | Type | Confidence |
|---|---|---|---|---|
| 1.1 Pro accounts with ≥1 repricing rule live | 0 | 90 (31.5% of 286) | Aspirational | 55% |
| 1.2 Share of price changes originating from a ListUp recommendation, in enabled accounts | 0% | 8% | Aspirational | 50% |
| 1.3 Recommendation acceptance rate | 38% (beta) | 55% | Aspirational | 60% |
| *Health* | Mis-published prices attributable to repricing | 0 | Guardrail | — |

**Objective 2 — Agencies can build a business on ListUp.**

| KR | Baseline | Target | Type | Confidence |
|---|---|---|---|---|
| 2.1 Agencies onboarded managing ≥5 accounts | 0 | 6 | Aspirational | 50% |
| 2.2 Accounts under agency management | 0 | 42 | Aspirational | 50% |
| 2.3 Partners live on the read API | 0 | 3 | Committed | 85% |
| *Health* | Agency-managed account churn no worse than direct | ≤2.2%/mo | Guardrail | — |

**Objective 3 — Revenue shifts toward the tier we intend to win.**

| KR | Baseline | Target | Type | Confidence |
|---|---|---|---|---|
| 3.1 Growth→Pro upgrades in the quarter | 11 | 30 | Aspirational | 60% |
| 3.2 Pro share of revenue | 39.6% | 43.0% | Aspirational | 55% |
| *Health* | Growth-tier logo churn | ≤2.2%/mo | Guardrail | — |

**Mechanism behind 3.1**, written down at set time: repricing is Pro-only,
and Growth accounts hitting the rule builder see an upgrade prompt with a
90-day price. 11 → 30 is a 2.7× lift, which is roughly what a comparable
in-app paywall prompt delivered on the Live Sync launch. If the prompt
converts at the historical rate, 30 upgrades is worth
30 × ($199 − $79) × 12 = **$43,200 ARR**.

### What did not become an OKR

| Request | Decision | Reason |
|---|---|---|
| SSO and SOC 2 | Q3 backlog | Named as a non-goal in the strategy until Q3 |
| Mobile app | No | Strategy non-goal |
| Bulk CSV import v2 | Ships anyway, not a KR | Maintenance; small, already scheduled, moves nothing |
| Channelry feature parity on templates | No | No deal lost on it in two quarters of win/loss |

This table is the most useful page in the whole document. OKRs earn their
keep by producing it.

### Grading at week 13

Scores are `(actual − baseline) / (target − baseline)`, capped at 1.0.

| KR | Baseline | Target | Actual | Score |
|---|---|---|---|---|
| 1.1 Pro accounts with a live rule | 0 | 90 | 62 | 0.69 |
| 1.2 Changes from a recommendation | 0% | 8% | 5.1% | 0.64 |
| 1.3 Acceptance rate | 38% | 55% | 49% | 0.65 |
| 2.1 Agencies onboarded | 0 | 6 | 4 | 0.67 |
| 2.2 Accounts under agency management | 0 | 42 | 29 | 0.69 |
| 2.3 Partners live on the read API | 0 | 3 | 3 | 1.00 |
| 3.1 Growth→Pro upgrades | 11 | 30 | 34 | 1.00 |
| 3.2 Pro share of revenue | 39.6% | 43.0% | 41.8% | 0.65 |

| Objective | Score | Read |
|---|---|---|
| O1 — Trust the recommendations | **0.66** | Adoption and quality moved together, both short. Acceptance at 49% says the model is useful but not yet trusted; the honest read is one more quarter, not a pivot. |
| O2 — Agency channel | **0.79** | The API landed; the channel is slower than hoped because onboarding an agency takes 5 weeks, not 2. Re-target 2.1 to 10 for Q2 with a realistic ramp. |
| O3 — Revenue mix | **0.82** | 34 upgrades beat the target and delivered **$48,960 ARR**, yet Pro's revenue share moved only 2.2 points because the Growth base grew too. A useful lesson: a ratio KR can be dragged down by success elsewhere. |
| **Overall** | **0.76** | A good aspirational quarter. |

**Decisions taken from the grades:**

1. **Keep O1 into Q2** with acceptance rate as the lead KR, not adoption.
   Turning it on is no longer the constraint; trusting it is.
2. **Replace 3.2 with an absolute KR** (Pro MRR in dollars). Share-of-total
   KRs punish you for growing the denominator.
3. **Re-baseline agency onboarding** to a 5-week ramp and set Q2 targets on
   that, rather than repeating an assumption already proven wrong.
4. **Guardrails all held** — zero mis-published prices, agency churn at
   1.9%. Had the health metric broken, O1 would be scored 0 regardless of
   the KR numbers.

## Six ways product teams break OKRs

| Anti-pattern | What it looks like | Fix |
|---|---|---|
| Roadmap in OKR clothing | Every KR is a ship date | Ask "could we hit this and still have failed?" |
| Too many | 5 objectives, 20 KRs | Cap at 3 objectives; the cap *is* the prioritisation |
| Cascading literally | Every team's KR is a slice of the VP's number | Align on the objective, let teams choose their own KRs |
| No baseline | "Increase activation significantly" | No baseline, no KR — spend week 1 measuring instead |
| Set once, read at quarter end | No week-6 review | Weekly confidence, week-6 keep/drop decision in writing |
| Tied to compensation | Everyone lands 0.95 every quarter | Grades inform planning, never pay |

## Exercise

Write a full OKR set for your team's next quarter, traced to a strategy.

1. **Trace.** Start from your strategy's coherent actions (Module 1) and
   write one sentence per action naming which objective it feeds. Any
   objective with no strategic parent should be cut or justified explicitly.
2. **Draft 2–3 objectives**, qualitative and memorable, no numbers.
3. **For each objective, write 2–4 key results** covering at least two of:
   adoption, depth, quality, business. Every KR needs a measured baseline —
   go and get the number before you write the target.
4. **Document the mechanism** for your most ambitious KR: what specific
   change produces the lift, and what comparable evidence sizes it. If you
   cannot, downgrade it to a learning KR.
5. **Add a health metric per objective** and state what happens to the grade
   if it breaks.
6. **Label each KR** committed or aspirational, and record your confidence
   as a percentage on the day you set it.
7. **Write the "did not make the cut" table** — at least five things you are
   declining this quarter, and the one-line reason for each. Circulate this
   table to stakeholders before the quarter starts, not after.
8. **Pre-write the week-6 review agenda**: for each KR, the number that would
   make you drop it and the number that would make you raise it.
9. **Grade last quarter** if you have one, using the baseline-adjusted
   formula, and write one decision per objective that the grade forces.
