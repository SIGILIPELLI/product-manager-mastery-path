# 07 · AI/ML Product Management

Most of product management transfers to AI products unchanged. Discovery is
still discovery, prioritisation is still prioritisation, and a model that
solves a problem nobody has is as worthless as a feature that does. What
does not transfer is the part that trips up experienced PMs: **you are
shipping a system that is wrong a predictable percentage of the time, and
the product decision is what to do about that.**

Deterministic software has bugs, which are defects to be fixed. A model has
an error rate, which is a property to be designed around. Confusing the two
produces the two classic AI product failures — promising accuracy that
cannot be delivered, and building a beautiful model with no mechanism for
what happens when it is wrong.

ListUp's Decide line is the running example: it recommends price changes
across seller catalogues, and after the Pricewell acquisition (Level 4,
Module 4) it carries the acquired model too. $14.7M ARR, 71% growth, and an
error rate that is not going to zero.

## What is genuinely different

| Dimension | Deterministic product | AI/ML product |
|---|---|---|
| **Correctness** | Binary — works or is a bug | A distribution; there is an error *rate* |
| **Spec** | Describes behaviour | Describes acceptable error and its cost |
| **QA** | Test cases pass | An evaluation set with a score and a regression bar |
| **Failure** | Visible, reproducible | Often silent, plausible, and confidently wrong |
| **Improvement** | Write code | Data, evaluation, then sometimes a model |
| **Marginal cost** | ≈ 0 | Real, per inference, and scales with success |
| **Latency** | Predictable | Variable, sometimes seconds |
| **Regression risk** | Caught by tests | A model update can silently degrade a subgroup |
| **Trust** | Assumed | Earned, and lost permanently by one bad experience |
| **Roadmap unit** | Feature | Capability plus threshold plus fallback |

The last row is the one to internalise. **Nothing in an AI product ships
without three decisions: what it does, at what confidence threshold it acts,
and what happens below that threshold.** A roadmap item missing the second
and third is not specified.

## The cost of being wrong is asymmetric, and that sets the threshold

Almost every AI product decision reduces to one comparison: the value of a
correct output against the cost of an incorrect one. These are rarely equal,
and when they are not, the confidence threshold is an arithmetic result, not
a taste judgement.

**Decide's economics per auto-applied price change:**

| Quantity | Value | Source |
|---|---|---|
| Margin gained on a correct change | **+$11.00** | Median over 4.1M labelled historical changes |
| Margin lost on an incorrect change | **−$34.00** | Underpriced units sold before rollback, plus the reprice |
| Recommendations generated per month | **312,000** | Across 6,150 direct accounts and 214 agencies |

Break-even precision is where expected value is zero:
`p × 11 − (1 − p) × 34 = 0`, so `45p = 34`, so **p = 75.6%**.

Any auto-apply threshold that admits recommendations below 75.6% precision
destroys margin. That single number kills the most common AI roadmap
proposal — "auto-apply everything, the model is 71% accurate" — before a
single engineer is assigned.

## Choosing the threshold

Precision rises and volume falls as the confidence bar rises. The optimum is
interior, and you have to compute it.

| Threshold | Auto-applied | Precision | Correct | Incorrect | Recall | **Net margin / month** |
|---|---|---|---|---|---|---|
| 0.50 | 312,000 | 71.0% | 221,520 | 90,480 | 100% | **−$639,600** |
| 0.70 | 198,000 | 84.0% | 166,320 | 31,680 | 75.1% | **+$752,400** |
| **0.85** | **121,000** | **93.0%** | **112,530** | **8,470** | **50.8%** | **+$949,850** |
| 0.95 | 47,000 | 98.1% | 46,107 | 893 | 20.8% | **+$476,815** |

Three things this table teaches that no amount of model discussion will:

- **Shipping everything is worse than shipping nothing.** At 0.50 the
  feature loses $639,600 a month while being, in a narrow sense, 71%
  accurate. Accuracy without a cost model is not a product metric.
- **The optimum sacrifices half the recall.** At 0.85 the model acts on 39%
  of its own recommendations and captures 50.8% of the available correct
  ones. That is the right answer, and it will feel like underuse to everyone
  who built the model.
- **Maximum precision is not the goal either.** At 0.95 net margin halves.
  Being too cautious is a real cost, just a quieter one.

**What happens to the other 191,000 recommendations** is the actual product
design, and it is where most of the differentiation lives. They go to a
review queue, sorted by value at stake, presented with the reason for the
recommendation, and accepted or rejected in one click — which produces
labelled training data as a by-product. The rejections are worth more than
the acceptances.

## The design pattern: confidence tiers

| Confidence | Behaviour | Interface | Reversibility |
|---|---|---|---|
| **High** (≥ 0.85) | Act automatically | Notify after the fact; show the reason | One-click undo, 30-day log |
| **Medium** (0.60–0.85) | Recommend | Review queue, sorted by value at stake | Nothing happens without a click |
| **Low** (< 0.60) | Stay silent | Not surfaced at all | — |
| **Out of distribution** | Refuse | "Not enough data for this SKU" | — |

That fourth row is the most under-built and the most trust-preserving.
**A model that says "I don't know" for genuinely unfamiliar inputs earns
more trust than one that is right slightly more often overall.** Users
forgive an abstention; they do not forgive a confident, expensive error, and
one such error can end a customer's willingness to use auto-apply forever.

## Evaluation: the real deliverable

The evaluation set is a product artefact, and owning it is the highest-value
thing an AI PM does. It is also the one thing a PM can own that a research
team usually will not.

| Element | Requirement | Why |
|---|---|---|
| **Held out** | Never trained on, never tuned against | Otherwise the score is theatre |
| **Representative** | Matches the production distribution, including rare categories | Aggregate scores hide subgroup collapse |
| **Sliced** | Scored per segment: category, catalogue size, seller tenure, region | The average is almost always misleading |
| **Cost-weighted** | Errors scored by their business cost, not counted equally | 75.6% break-even, not 50% |
| **Versioned** | Frozen; changes are announced and dual-reported | A moving eval measures nothing |
| **Adversarial** | Deliberate hard and weird cases | Production is adversarial |
| **Regression-barred** | No model ships if any slice drops more than 2 points | Prevents silent subgroup damage |

The subgroup rule prevents the most common AI product disaster: a model
update raises aggregate accuracy by 1.4 points while collapsing on a
category that happens to be 30% of one large customer's catalogue. The
aggregate says ship. The slice says do not.

## Unit economics: the cost that scales with success

Model inference has a real marginal cost, which makes AI features
structurally unlike ordinary software. ListUp's listing-copy generator, sold
as a $49/month add-on:

| Line | Value |
|---|---|
| Accounts on the add-on (18% of 6,150) | 1,107 |
| Generations per account per month | 340 |
| Total generations per month | 376,380 |
| Tokens per generation | 1,900 in / 700 out |
| Input cost at $3.00 per million tokens | $2,145.37 |
| Output cost at $15.00 per million tokens | $3,951.99 |
| **Total inference cost per month** | **$6,097.36** |
| Annualised | $73,168 |
| Add-on ARR (1,107 × $49 × 12) | $650,916 |
| **Blended gross margin** | **88.8%** |

88.8% looks like a software business, and the average is hiding the entire
risk. Usage in AI features is heavy-tailed: **the top 5% of accounts — 55 of
them — generate about 40% of the volume**, roughly 2,737 generations each
per month, at a cost of **$44.34 per account against a $49 price**. Those
accounts run at **9.5% gross margin**.

| Segment | Accounts | Cost/month each | Margin at $49 |
|---|---|---|---|
| Top 5% by usage | 55 | $44.34 | **9.5%** |
| Remaining 95% | 1,052 | $3.48 | 92.9% |

Two product consequences follow, and neither is a pricing negotiation:

- **Flat pricing on a metered cost needs a cap or a meter.** A fair-use
  allowance with paid overage above it, disclosed at purchase, keeps the
  tail from inverting the economics as adoption grows.
- **Watch the trend, not the average.** If the heavy tail grows faster than
  the base — which it does, because heavy users are the ones who renew —
  blended margin falls quarter after quarter while every dashboard shows
  growth.

## The AI product roadmap

| Stage | Question | Exit criterion | Common mistake |
|---|---|---|---|
| **Problem** | Is a probabilistic answer acceptable here at all? | A human currently does this and tolerates being wrong sometimes | Applying ML to a problem that requires certainty |
| **Baseline** | What does a simple rule achieve? | Heuristic scored on the eval set | Skipping it; a rule often wins on cost |
| **Feasibility** | Can a model beat the baseline meaningfully? | Offline lift on cost-weighted eval | Celebrating aggregate accuracy |
| **Cost model** | What are a correct and an incorrect output worth? | Break-even precision computed | Never done, so the threshold is arbitrary |
| **Threshold + fallback** | When does it act, and what happens otherwise? | Confidence tiers specified | Shipping a model with no fallback |
| **Shadow** | Does it behave in production? | Runs live, takes no action, logged for 2–4 weeks | Going straight to auto-apply |
| **Limited launch** | Does it hold on real users? | One segment, holdout, guardrails | No holdout, so no attribution |
| **Scale** | Does it hold at volume, per slice? | Per-slice monitoring and drift alarms | Assuming the launch score persists |

**Shadow mode is the highest-return stage and the most often skipped.** For
two to four weeks the model runs on live traffic and takes no action; you
compare what it would have done against what happened. Decide's shadow
period is what revealed that its raw precision was 71%, not the 88% the
offline evaluation suggested — a gap caused entirely by the offline set
under-representing low-volume SKUs.

## Trust, explanation and the things that go wrong

| Risk | Mechanism | Mitigation |
|---|---|---|
| **Silent degradation** | Input distribution drifts; accuracy falls with no error raised | Monitor input distribution, not just outputs; alarm on drift |
| **Feedback loop** | The model's own actions become its training data | Hold out a random control slice permanently |
| **Automation complacency** | Users stop checking, so errors compound | Periodic sampled review; surface confidence, not just answers |
| **Confident hallucination** | Plausible, wrong, unhedged | Ground in retrieved data; refuse when unsupported |
| **Subgroup collapse** | Aggregate improves, one segment breaks | Per-slice regression bar on every release |
| **Explanation theatre** | A rationale generated after the decision | Show the *inputs* that drove it, not a narrative |
| **Data rights** | Training on data you lack rights to combine | Settle before building, not at legal review |
| **Cost inversion** | Heavy users make the feature unprofitable | Caps, meters, per-account cost monitoring |

On explanation: users do not need the model's internals, they need enough to
decide whether to trust *this* output. "Recommended because three competing
listings dropped 12% in 48 hours and your stock cover is 61 days" is
actionable. "Confidence: 0.87" is not. **Explanations should give the user
grounds to overrule you** — that is their function, and a feature that
cannot be overruled on informed grounds will not be trusted with anything
expensive.

## Exercise

1. **Write the error-cost model** for one AI feature: the value of a correct
   output and the cost of an incorrect one, in currency, with the source of
   each figure.
2. **Compute break-even precision** from those two numbers. State plainly
   whether your current model clears it.
3. **Build the threshold table** — at least four thresholds, with volume,
   precision, recall and net value. Identify the interior optimum and how
   much recall it costs you.
4. **Specify the confidence tiers**, including the abstention behaviour for
   out-of-distribution inputs. If you have no abstention path, design one.
5. **Design what happens below the threshold.** Describe the review queue,
   its ordering, and how the decisions it produces become training data.
6. **Audit your evaluation set** against the seven requirements. Fix the
   worst gap this quarter, and set a per-slice regression bar.
7. **Compute per-account inference cost**, then the distribution — not the
   average. Report the margin of your top 5% of users by volume.
8. **Decide the packaging consequence**: cap, meter, or accept the tail, with
   the arithmetic that supports it at three times current adoption.
9. **Run shadow mode** on your next model change for at least two weeks and
   compare the production result against the offline score. Write down the
   gap; it is the most useful number you will collect this quarter.
