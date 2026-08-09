# 05 · Executive Communication & Board Reporting

There is a specific, recognisable moment when a good product leader loses a
room. They open with context. They explain the market, then the customer
research, then the three options considered, and somewhere around minute
seven a board member interrupts to ask what the ask is. The content was
correct. The ordering was fatal.

Executive and board communication runs on an inverted contract. Everywhere
else in product you build to a conclusion, because you are bringing people
along. Here you **lead with the conclusion and defend it backwards**,
because your audience has thirty minutes, four other companies on their
plate this week, and no memory of last quarter's context. They are not
reading to learn what you think. They are reading to decide whether to trust
your judgement and whether anything needs to change.

This module covers the two audiences (they are not the same), the metric
pack, the ARR bridge, delivering bad news, and the arithmetic that has to be
right before anyone will listen to the narrative.

## The two audiences are not the same

| | Exec team | Board |
|---|---|---|
| **Frequency** | Weekly to monthly | Quarterly |
| **Context they hold** | Most of it | Almost none — reconstruct it every time |
| **What they want** | Decisions, trade-offs, unblocking | Confidence in the plan and in the team |
| **Time budget** | 15–30 min | 5–10 min of the agenda is yours |
| **Their real question** | "What do you need from me?" | "Is this team going to hit the plan, and do they know why or why not?" |
| **Detail tolerance** | High, if it is decision-relevant | Low — detail belongs in the pre-read appendix |
| **Bad news reaction** | Wants the fix | Wants evidence you saw it early and have a plan |
| **How you lose them** | Status without an ask | Metrics without a narrative, or narrative without metrics |

A board does not want your roadmap. It wants to know whether the roadmap is
a consequence of a strategy, whether the strategy is a consequence of
evidence, and whether last quarter's forecast turned out to be true. That
last item is the one that quietly determines how much rope you get.

## The structure: BLUF, then the spine

Every executive artefact — memo, slide, email, hallway answer — uses the
same four-part spine.

| Part | Length | Contains | Test |
|---|---|---|---|
| **Bottom line** | 1–3 sentences | The conclusion and the ask | Could someone act on this alone? |
| **Evidence** | 3–5 bullets or one table | The numbers that make it true | Does each one survive "how do you know?" |
| **Risk** | 2–3 lines | What would make you wrong, and the leading indicator | Would a sceptic add anything you left out? |
| **Ask** | 1 line | Decision, resource, or nothing ("no ask, awareness only") | Is it specific enough to say yes to? |

**Bad opening:** "Decide has had a strong quarter and the team has been
doing great work on the acceptance-rate improvements we discussed last
time."

**Good opening:** "Decide attach reached 34%, ahead of the 31% plan, and
that alone accounts for $1.9M of the $3.3M net new ARR this quarter. I am
asking for four engineers in Q1 rather than two."

The second version is shorter, contains three numbers, states the ask, and
gives the room something to push on. The first version is a mood.

## The board metric pack

Boards do not want your team's operational dashboard. They want the eight to
ten numbers that describe the business, the same ones every quarter, with
last quarter's value beside them so the trend is visible without arithmetic.

**ListUp's product-relevant pack**, Q3:

| Metric | This quarter | Plan | Definition being used |
|---|---|---|---|
| Ending ARR | $52,400,000 | $52,100,000 | Contracted annualised recurring, excl. services |
| YoY growth | 37.9% | 38% | vs $37,998,550 a year ago |
| Net new ARR (quarter) | $3,300,000 | $3,000,000 | Ending minus starting |
| Net revenue retention | 112.0% annualised | 110% | Quarterly cohort, compounded |
| Gross revenue churn | 11.9% annualised | Under 13% | Contraction plus churn |
| Gross margin | 78.1% | 78% | Revenue minus COGS |
| Burn multiple | 0.37 | Under 0.75 | Net burn ÷ net new ARR, trailing 12 months |
| Rule of 40 | 27.6 | 30 | Growth % plus FCF margin % |
| CAC payback | 9.4 months | Under 12 | Blended, gross-margin adjusted |
| Magic number | 2.24 | — | 4 × quarterly net new ARR ÷ prior-quarter S&M |
| % of new ARR with no human | 71% | Above 65% | See Level 4, Module 3 |

Two disciplines that separate a credible pack from a decorative one:

- **Publish the definition column and never change it silently.** If you
  redefine a metric, show both old and new for two quarters and say why.
  A board that catches an undisclosed definition change will re-audit
  everything else you have ever shown them.
- **Explain the number that looks too good.** ListUp's magic number of 2.24
  is roughly double a strong sales-led benchmark, and the honest reason is
  structural, not heroic: 71% of new ARR closes without a salesperson, so
  the denominator is small by design. Say that before someone else works it
  out — otherwise the one quarter it drops to 1.4 will read as a collapse
  rather than a mix shift.

Rule of 40 at **27.6** is below the 40 threshold and below plan. Put it in
the pack anyway. Metrics that only appear when they are flattering are worth
nothing, because the board learns to discount everything else you show.

## The ARR bridge

The single most useful board slide in a subscription business, and the one
most often replaced by a growth percentage.

| Component | Q3 | What it tells the board |
|---|---|---|
| Starting ARR | $49,100,000 | |
| **+** New logo | $1,890,000 | Is acquisition working? |
| **+** Expansion | $2,940,000 | Is the product getting more valuable to existing customers? |
| **−** Contraction | −$710,000 | Are customers downgrading, and from which product? |
| **−** Churn | −$820,000 | Are they leaving, and were they ever a fit? |
| **=** Ending ARR | **$52,400,000** | |
| Net new | **$3,300,000** | |

Retained ARR is $49,100,000 + $2,940,000 − $710,000 − $820,000 =
$50,510,000, a quarterly retention factor of 1.0287, which compounds to
**112.0%** annualised.

The bridge is powerful because it makes the *composition* of growth visible.
$3.3M of net new ARR built from $2.94M of expansion is a fundamentally
different business from $3.3M built mostly from new logos, and the two
demand different investment. A single growth percentage hides that
completely — which is exactly why struggling companies prefer it.

## Worked example — ListUp's Q3 product section

Ten minutes, five slides, a fourteen-page appendix nobody will read live and
several people will read afterwards.

| Slide | Content | Why it is there |
|---|---|---|
| **1 — Bottom line** | "Ahead of plan on ARR and attach, behind on Rule of 40. One ask: four engineers into Decide in Q1." | The whole meeting in four lines |
| **2 — Metric pack** | The eleven rows above, with plan and prior quarter | Establishes that the numbers are known and stable |
| **3 — ARR bridge** | Composition of the $3.3M | Shows growth is expansion-led, which supports slide 5 |
| **4 — The one thing that went wrong** | Publish reliability: three Sev-2s, and the churn they caused | Bad news, volunteered, with a fix and a date |
| **5 — The ask** | Four engineers, the marginal-ROI evidence, what gets dropped | A decision, not a wish |

**Slide 5 as it should be written**, because this is where most product
leaders get vague:

> **Ask:** four additional engineers into Decide in Q1, not two.
>
> **Evidence:** Decide's marginal ARR per engineer is $620,000 against
> Publish's $180,000, estimated from the last four hires into each group.
> Confidence is medium — the estimate is confounded with agency-channel
> growth, so treat it as an upper bound.
>
> **Cost:** $780,000 fully loaded. Trade-off: Publish drops from 14 to 13
> engineers, which is a floor, not an optimum — below 13, incident load
> rises on the line carrying 52% of revenue.
>
> **What would make me wrong:** if Decide's acceptance rate stalls below
> 82%, the marginal estimate is inflated and I will say so at the Q1 review
> rather than defending the hire.

That last paragraph is the one that buys credibility. Naming your own
falsifier before anyone asks for it is the cheapest trust you will ever
purchase, and the reason boards let some leaders run and micromanage others.

## Delivering bad news

| Rule | Why |
|---|---|
| **You say it first, and early** | The only unrecoverable version is the one they hear from someone else |
| **Lead with the number, not the context** | "Publish churn was $820k, 40% above plan" before any explanation |
| **Separate what you knew from what you learned** | Boards forgive being wrong; they do not forgive being surprised twice |
| **Bring the diagnosis, not just the fact** | "Three Sev-2s in one quarter, all in the marketplace adapters, all from the same untested retry path" |
| **Bring the fix with an owner and a date** | Without these it is a complaint |
| **State the leading indicator you will watch** | Proves you will detect a recurrence before the next board meeting |
| **Never bundle it with good news in the same breath** | The sandwich reads as spin and devalues the good news |
| **Do not pre-brief only your allies** | Pre-brief the sceptic first; their objection is the one that will land in the room |

A useful private test before any bad-news slide: **if this gets worse next
quarter, does this slide make me look like someone who saw it coming?** If
not, rewrite it until it does — honestly, by adding the risk you are
currently hoping nobody raises.

## Handling the room

| Question type | Example | How to answer |
|---|---|---|
| **Testing the number** | "How is attach defined?" | Definition, in one sentence, immediately. Hesitation here is fatal |
| **Testing the judgement** | "Why not put those four engineers in Console?" | Give the comparison you already ran, including the case for their option |
| **Out of scope** | "What's our position on tariffs?" | "I don't know. I'll come back by Friday." Then do |
| **Rhetorical / directive** | "Have you considered acquiring Channelry?" | Treat as a real question, answer the substance, do not commit in the room |
| **Hostile** | "This looks like last quarter's slide." | Agree with the true part, correct the false part, no defensiveness |

**"I don't know, I'll find out by Friday" is a complete and excellent
answer**, used at most twice per meeting, and only when followed by actually
doing it. Improvising an answer that turns out to be wrong costs more
credibility than three quarters of good results restore.

## Anti-patterns

| Anti-pattern | What it signals | Instead |
|---|---|---|
| Roadmap slide with no strategy | You are executing without a thesis | One strategy line, then the roadmap as its consequence |
| Vanity metrics (signups, features shipped) | You cannot connect work to money | Metrics that appear in the business model |
| Different metrics each quarter | Cherry-picking, whether or not you meant it | A fixed pack; add rows, never quietly drop them |
| No forecast, or no reference to last quarter's | Nobody is holding you to your own numbers | Open with last quarter's forecast versus actual |
| Everything is green | Nobody believes it, including you | Grade honestly; one red with a plan builds more trust than eight greens |
| Forty slides | You have not decided what matters | Five slides, deep appendix |
| Reading the slides aloud | Wastes the only expensive hour you get | Send the pre-read 48 hours ahead; spend the meeting on discussion |
| Asking for headcount without a trade-off | You are asking them to do your prioritisation | Every ask names what it displaces |

## Exercise

1. **Rewrite your last executive update as a four-part spine**: bottom line,
   evidence, risk, ask. If the bottom line takes more than three sentences,
   you have not decided what it is yet.
2. **Build your metric pack** — eight to twelve rows, each with the value,
   the plan, and the definition. Fix the definitions in writing.
3. **Find the metric in your pack that looks too good** and write the
   structural explanation for it, before someone else asks.
4. **Build the ARR bridge** for your last quarter: starting, new, expansion,
   contraction, churn, ending. State what the composition implies about
   where the next dollar of investment should go.
5. **Compute net revenue retention from the bridge**, not from a dashboard,
   and reconcile the two. If they disagree, find out why before your next
   board meeting.
6. **Write the five-slide board section** for your product, with slide 4
   reserved for the thing that went wrong.
7. **Write the ask slide in full**, including cost, the explicit trade-off,
   and the falsifier — the condition under which you will come back and say
   you were wrong.
8. **Draft the bad-news slide** for your worst current metric and apply the
   private test: does this make you look like someone who saw it coming?
9. **List the five hardest questions** you could be asked next quarter, write
   the one-sentence answer to each, and identify which one you currently
   cannot answer. That is your work for the next month.
