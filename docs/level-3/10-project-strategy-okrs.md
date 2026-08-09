# 10 · Project — Product Strategy Doc + OKRs

This project is the artefact a senior PM is hired to produce: an annual
product strategy with the operating plan attached. Below is a **finished
document**, written as it would actually be circulated — the year-3 strategy
refresh for ListUp, one year after the strategy in Module 1 was adopted.

A refresh is deliberately harder than a first draft, because it has to
answer the question a new strategy never faces: *did the last one work?*
Read it as a model, then build your own using the stretch goals at the end.
Every number is either a stated input or derived from one, and the bridge in
section 8 has to add up — which is exactly the standard your document should
meet.

---

## 1. Year in review — did last year's strategy work?

Last year's guiding policy: **own the decision, not just the publish.** The
proof points were written down in advance, which is the only reason this
section can be honest.

| Proof point | Target | Actual | Verdict |
|---|---|---|---|
| Pro accounts with repricing enabled, 6 months | 114 | 98 | Miss |
| Repricing attach across Growth + Pro, 12 months | 30% (347 accounts) | **15.5%** (271 accounts) | **Miss, badly** |
| Incremental ARR from repricing at $60/mo uplift | $249,840 | $195,120 | Miss |
| Revenue through agency-managed accounts, 18-month target | 25% | **21.8% at 12 months** | Ahead of pace |
| Pro share of revenue, 24-month target | 55% | **50.1% at 12 months** | Well ahead |

**Business result:**

| Metric | Year 1 end | Year 2 end | Change |
|---|---|---|---|
| Paying accounts | 1,780 | 2,510 | +41.0% |
| MRR | $143,790 | $230,069 | +60.0% |
| ARR | $1,725,480 | **$2,760,822** | **+60.0%** |
| ARPA | $80.78 | $91.64 | +13.4% |
| Blended logo churn | 2.66% | 2.47% | −0.19pt |
| Revenue-weighted churn | 1.92% | 1.73% | −0.19pt |

| Tier | Accounts | % of accounts | MRR | % of revenue |
|---|---|---|---|---|
| Starter | 757 | 30.1% | $21,939 | 9.5% |
| Growth | 1,174 | 46.8% | $92,762 | 40.3% |
| Pro | 580 | 23.1% | $115,368 | 50.1% |

**The finding that matters, and it is uncomfortable: we grew 60% for a
reason that was not in our strategy.** The strategy said repricing would
pull sellers up the value chain, and repricing attach came in at half its
target. What actually produced the year was the *other* two actions — the
tier fence and the agency channel. 27 agencies now manage 412 accounts
(16.4% of accounts, **21.8% of revenue**, ARPA $121.74 against $91.64
blended).

A strategy refresh that reported "we hit 60% growth" and moved on would
have learned nothing. The two questions this document has to answer are:
**is the repricing bet wrong, or early?** And **should the agency channel be
promoted from supporting act to the main event?**

**Evidence on the first question**, gathered specifically for this review:

| Question | Finding |
|---|---|
| Do enabled accounts get value? | Yes. Accounts with a rule live for 90+ days churn at 0.7%/mo vs 1.9% for comparable non-users |
| Why don't more enable it? | 61% of surveyed non-users cite "I don't trust it to run unattended", not price or awareness |
| Does the recommendation quality gate it? | Acceptance rate ended the year at 49% against a 55% target (Module 2). Below ~60%, sellers review every suggestion, which removes the labour saving |
| Is the audience wrong? | Attach among agency-managed accounts is 34%, more than double the direct rate of 13.9% |

**Conclusion: early, not wrong — and mis-targeted.** The bet was aimed at
individual sellers, who will not delegate pricing to software they cannot
audit. Agencies, who are paid on outcomes and manage dozens of catalogues,
adopt it at 2.4× the rate. The strategy does not need reversing; it needs
re-pointing.

## 2. Revised diagnosis

*ListUp's decision layer works and is under-adopted, because we aimed it at
the user least able to trust it. Individual sellers will not hand pricing to
an unattended system; agencies will, and already do at 34%. Meanwhile the
agency channel we built as distribution has become the highest-value
customer we have — 16.4% of accounts producing 21.8% of revenue at 1.33×
blended ARPA — and we are still serving them with a product designed for one
seller with one catalogue.*

The crux for year 3 is not whether to build recommendations. It is **who we
build the whole product for.**

## 3. Guiding policy

> **The agency is the customer; the seller is the user.** ListUp designs,
> prices and sells for the operator who manages many catalogues, and the
> decision layer is the reason they choose us. Single-seller self-serve
> remains the on-ramp and the trial, not the design centre.

What this rules out, explicitly: building a consumer-grade single-seller
experience as the primary surface, chasing Channelry's free tier, and
launching adjacent single-seller tools (repricing for one store, storefront
analytics) before the multi-catalogue product is complete.

## 4. Where to play

| | Playing | Not playing |
|---|---|---|
| **Customer** | Agencies and multi-brand operators managing 8–60 catalogues | Solo sellers as a design target |
| **User** | The catalogue manager inside the agency; the seller as a viewer/approver | — |
| **Job** | Decide and publish price, stock and content across many catalogues | Fulfilment, storefront, accounting |
| **Buyer** | Agency principal | Enterprise procurement (revisit year 4) |
| **Channel** | Agency-led, plus self-serve trial as the on-ramp | Outbound SDR |

## 5. How to win

- **Cross-catalogue data.** An agency's 40 catalogues make every
  recommendation better for all 40. A single seller's data cannot do this,
  and a competitor serving single sellers cannot assemble it.
- **The operator's workflow, not the seller's.** Approval queues, per-client
  reporting, bulk rule templates, white-glove audit trails. Boring, deep,
  and invisible to anyone building for individuals.
- **Economics that align.** Agencies are paid on their clients' results. A
  product that improves those results sells itself inside the agency.
- **Trust as a feature, not a claim.** Every recommendation carries its
  reason, its evidence, and a one-click revert. This is what unblocks the
  61% who won't run it unattended.

## 6. Coherent actions

| # | Action | Horizon | Squad | Reinforces |
|---|---|---|---|---|
| 1 | **Explainable recommendations**: reason, evidence, confidence and one-click revert on every suggestion; auto-apply mode gated on a confidence threshold | Q1–Q2 | Decide | 2 and 3 — trust is the gate on both |
| 2 | **Agency operating console**: approval queues, cross-catalogue rules, per-client reporting, role-based access | Q1–Q3 | Platform | 1 and 3 — where agencies consume recommendations |
| 3 | **Agency commercial model**: volume tiers, revenue share, co-selling, certification | Q2–Q3 | Growth | 1 and 2 — the reason agencies bring clients |
| 4 | **Self-serve as an on-ramp only**: trial and Starter maintained, no new investment; funnel work aimed at agency-sourced signups | Q1 | Growth | Frees capacity for 1–3 |

Coherence check: remove action 1 and the console is a dashboard over
suggestions nobody trusts; remove action 2 and explainability lands in a
single-catalogue UI an agency cannot operate; remove action 3 and both ship
into a channel with no commercial reason to expand.

## 7. Non-goals

| Non-goal | Why | What it costs us |
|---|---|---|
| Free tier | Subsidises the segment we exited last year and are still exiting | Continued unfavourable comparisons with Channelry |
| Marketplace/storefront features | Different buyer, no data advantage | A perennially popular request from Starter |
| Enterprise procurement motion (SOC 2 Type II, MSAs) | Agencies buy without it today | Two named prospects above $60k ARR; revisit at year 4 planning |
| Single-seller mobile app | The design centre has moved | The loudest self-serve request |
| Building the analytics layer ourselves | The partner app covers 5 of 7 cited deals (Module 6) | Ecosystem dependency; monitored quarterly |

## 8. The financial bridge

Target: **$4,280,000 ARR**, up 55% from $2,760,822. A strategy without a
bridge is a wish; here is where every dollar comes from.

| Component | Mechanism | ΔMRR at month 12 | **ΔARR** |
|---|---|---|---|
| New paying accounts | 160/month average (from 130), ARPA $80, churned forward at 2.1%/mo | +$137,514 | **+$1,650,174** |
| Churn on the existing base | 2.47% → 2.10% blended, applied to $230,069 | −$51,728 | **−$620,740** |
| Growth→Pro upgrades | 180 in the year × $120 delta, 8% churned before year end | +$19,872 | **+$238,464** |
| Repricing attach | 271 → 620 accounts (+349) × $60/mo | +$20,940 | **+$251,280** |
| **Net** | | **+$126,598** | **+$1,519,178** |
| **Year-3 exit ARR** | | | **$4,280,000** |

Three checks worth stating, because someone will ask:

- **160 new paying accounts/month is a 23.5% increase** on today's 130. It
  is a ramp, not a step: 137 in Q1, 152 in Q2, 168 in Q3, 183 in Q4 —
  averaging 160.
- **The bridge does not assume Starter grows.** Starter is an on-ramp; its
  9.5% revenue share is expected to fall further.
- **Concentration risk rises with this plan.** The largest agency today
  manages 44 accounts, $6,688 MRR — **2.91% of revenue**, $80,256 ARR. The
  policy threshold set in Module 5 (no single relationship above 8% of ARR
  without a board conversation) is not yet breached, and is now a tracked
  metric with a named owner.

## 9. Company OKRs — Q1

Three objectives, eight key results, each traceable to a coherent action.

**O1 — Sellers and agencies let ListUp decide the price.** *(Action 1)*

| KR | Baseline | Target | Type | Confidence |
|---|---|---|---|---|
| 1.1 Repricing attach across Growth + Pro | 271 accounts (15.5%) | 360 (19.6%) | Aspirational | 60% |
| 1.2 Recommendation acceptance rate | 49% | 60% | Aspirational | 50% |
| 1.3 Accounts running auto-apply above the confidence threshold | 0 | 40 | Aspirational | 45% |
| *Health* | Mis-published prices attributable to repricing | 0 | Guardrail | — |

**O2 — Agencies can run their whole book on ListUp.** *(Actions 2 and 3)*

| KR | Baseline | Target | Type | Confidence |
|---|---|---|---|---|
| 2.1 Agencies onboarded | 27 | 33 | Committed | 80% |
| 2.2 Accounts under agency management | 412 | 490 | Aspirational | 60% |
| 2.3 Agency-managed accounts using the approval queue weekly | 0 | 55% of 490 = 270 | Aspirational | 50% |
| *Health* | Largest single agency as a share of ARR | Below 5% | Guardrail | — |

**O3 — The acquisition engine supports a 160/month run rate.** *(Action 4)*

| KR | Baseline | Target | Type | Confidence |
|---|---|---|---|---|
| 3.1 New paying accounts per month, exiting Q1 | 130 | 145 | Aspirational | 55% |
| 3.2 Blended monthly logo churn | 2.47% | 2.30% | Aspirational | 55% |
| *Health* | CAC payback on agency-sourced accounts | Under 12 months | Guardrail | — |

## 10. Squad alignment

Four squads, 4 PMs, 16 engineers. Alignment is on objectives; each squad
chooses its own key results.

| Squad | Owns | Q1 objective | Squad-level KRs |
|---|---|---|---|
| **Decide** | Recommendations, rules, confidence model | O1 | Reason-and-evidence panel on 100% of suggestions; acceptance 49%→60%; auto-apply live for 40 accounts; suggestion latency p95 under 2s |
| **Platform** | API, adapters, agency console | O2 | Approval queue GA; cross-catalogue rule templates; per-client report export; adapter framework slice 3 complete |
| **Growth** | Funnel, pricing, lifecycle | O3 | Visitor→trial 3.1%→3.5%; agency-sourced signups 31%→40% of new; at-risk save play live for Starter→cancel |
| **Publish** | Sync pipeline, channel adapters, reliability | Health for all three | p95 sync latency under 4 min sustained; change failure rate 18%→12%; unplanned work 27%→20% |

Two deliberate choices worth copying:

- **Publish has no growth KR.** A reliability squad given a growth number
  starts shipping features and stops being a reliability squad. Its
  contribution is the health metrics that every other objective depends on.
- **No squad's KR is a slice of a company KR.** Decide does not own "attach
  360" — that number depends on Growth's funnel and Platform's console too.
  Cascading a number that a team does not control is how OKRs become theatre.

## 11. Communicating it

| Audience | Format | When | The one thing they must take away |
|---|---|---|---|
| Board | 6 slides + this doc as appendix | Week 1 | The bridge, and the concentration risk that comes with it |
| Exec team | 60-min working session, not a presentation | Week 1 | The re-pointing of the repricing bet, and why it isn't a reversal |
| Engineering | 45 min, full doc pre-read | Week 2 | Why the console is the year, and what it means for the platform |
| Sales & CS | 30 min + the non-goals table | Week 2 | What we will and will not commit to for the next 12 months |
| Whole company | 1 slide, 1 sentence | Week 3 | "The agency is the customer; the seller is the user" |
| Customers | 3 public themes, no dates | Week 4 | Direction, no commitments (Module 5's tiering) |

The non-goals table is the section GTM should be given first. It prevents
more work than the strategy creates.

## 12. Review cadence and falsifiers

| Cadence | Review | Decision it can force |
|---|---|---|
| Weekly | KR confidence | Escalate a blocker |
| Week 6 | Mid-quarter | Keep, re-target or drop any KR, in writing |
| Quarterly | OKR grading + strategy proof points | Re-plan the next quarter |
| Half-yearly | Diagnosis check | Amend the guiding policy |
| Annually | Full refresh | Rewrite this document |

| Falsifier | Threshold | Then what |
|---|---|---|
| Agencies want a tool of their own, not ours | Fewer than 38 agencies at 6 months, with churn among the 27 above 5% | Revert to direct Pro; the agency channel becomes distribution only |
| Explainability doesn't unblock trust | Acceptance rate below 55% at 6 months with the panel shipped to 100% | The model, not the UI, is the constraint — re-plan as an ML investment (Level 4, Module 7) |
| Concentration becomes existential | Any single agency above 8% of ARR | Board conversation; contractual protections; direct relationships with that agency's sellers |
| The bridge is unreachable | New paying accounts below 140/month at end of Q2 | Re-forecast to 40% growth and cut the Q3 hiring plan before, not after, the miss |

## 13. What made this document work

- **The proof points were written a year in advance**, so the review could
  be honest rather than reconstructed.
- **It named the uncomfortable finding** — growth came from a different
  action than the strategy predicted — instead of claiming credit for the
  headline number.
- **It distinguished "early" from "wrong"** with four specific pieces of
  evidence, so re-pointing the bet was a decision rather than a retreat.
- **The bridge adds up to the target exactly**, so the growth number is a
  plan and not an aspiration.
- **The non-goals cost something**, and the cost is stated.
- **The falsifiers have thresholds and dates**, so abandoning the strategy is
  a pre-made decision rather than an argument.

## Stretch goals

Write the same document for your own product. Match it section for section,
then push further:

1. **Write the full strategy doc** — year in review against pre-existing
   proof points, revised diagnosis, guiding policy, where to play, how to
   win, coherent actions, non-goals, financial bridge, OKRs, squad
   alignment, communication plan, review cadence and falsifiers.
2. **Build the bridge so it sums exactly** to your target. Show new business,
   churn, expansion and price/mix as separate lines, each with the mechanism
   and the arithmetic. If it does not reconcile to the dollar, the target is
   not yet a plan.
3. **Grade last year honestly.** If you have no pre-written proof points,
   say so explicitly in the document — and write this year's before anything
   else.
4. **Find your own uncomfortable finding.** Identify one result you achieved
   for a reason your strategy did not predict, and decide what it implies.
   Every real year has one.
5. **Distinguish early from wrong** for your weakest bet, using at least
   four pieces of evidence — value delivered to adopters, stated reason for
   non-adoption, a quality gate, and a segment comparison.
6. **Write the non-goals so that at least one is genuinely painful**, and
   take it to the person it will annoy before you circulate the document.
7. **Design your squad alignment** so that no squad owns a number it cannot
   control, and give at least one team health metrics instead of growth
   metrics. Justify both.
8. **Pre-write the six-month review**: the exact table you will fill in, with
   the target column complete and the actual column empty, and put the date
   in the calendar now.
9. **Compute your concentration risk** — largest customer, top 5, top 10 as
   a share of ARR — under your plan rather than today, and set the threshold
   that triggers a board conversation.
10. **Cut it to one sentence** that the whole company can repeat, and test it
    by asking three people outside product to say it back to you a week
    later.

Completing this project means you're ready for **Level 4 · Master**.
