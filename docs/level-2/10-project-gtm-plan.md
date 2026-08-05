# 10 · Project — GTM Plan for a Feature Launch

This project pulls Level 2 together into the artefact a PM is most often
judged on and least often taught to write: a complete go-to-market plan for
a real feature launch. Below is a **finished plan, start to finish**, for a
launch that continues the ListUp story from Level 1 — the sync-delay problem
you wrote a PRD for is now built, and someone has to launch it.

Read it as a model, then produce your own using the stretch goals at the
end. Every number here is either a stated assumption or derived from one, so
you can check the arithmetic — which is exactly the standard your own plan
should meet.

## The launch brief

| Field | Value |
|---|---|
| **Feature** | ListUp **Live Sync** — price and inventory changes propagate to every connected marketplace in under 5 minutes, replacing a 4–6 hour batch |
| **Launch tier** | T1 — flagship capability, changes the product's core promise, gated to paid tiers |
| **Launch date** | Tuesday, week 0 (Tue–Thu ships best; avoid Mondays and Fridays) |
| **Lead time** | 6 weeks |
| **PM (DRI)** | You |
| **Eligible audience** | 769 accounts on Growth and Pro (of 1,240 paying) |
| **Budget** | $10,700 |
| **One-sentence pitch** | Change a price once and it's live everywhere before your next customer sees the old one |

Tier is decided at kickoff, not at ship. T1 is justified here because the
feature changes what the product fundamentally promises — not because it was
hard to build. Effort is never a launch-tier criterion.

## 1. Positioning

| Component | Answer |
|---|---|
| **Competitive alternative** | Manually re-checking each marketplace after every price change, or accepting that some channels are wrong for half a day |
| **Unique attributes** | Sub-5-minute propagation across all connected channels, with per-channel confirmation |
| **Value** | You can run a flash sale, or fix a mispriced item, without a window where customers see the wrong number |
| **Target segment** | Sellers on 4+ channels who change prices weekly or more |
| **Market category** | Multi-channel listing management |

> For **multi-channel sellers who change prices frequently**, **ListUp Live
> Sync** is a **publishing engine** that **puts every price and stock change
> live everywhere in under five minutes**. Unlike **marketplace-native
> tools and batch-sync competitors**, we **confirm each channel individually
> and show you exactly when it landed**.

Test applied: could a competitor publish this sentence unchanged? No — the
per-channel confirmation and the stated time bound are specific and
verifiable. Had the sentence said "faster, more reliable syncing", any
competitor could have used it, and it would have been a description rather
than a position.

## 2. Messaging house

| Pillar | Benefit statement | Proof |
|---|---|---|
| **Live, not eventually** | "Under five minutes to every channel" | Live latency counter in the UI; 30-second side-by-side demo; median 2m 40s in beta |
| **You can see it landed** | "Per-channel confirmation, with a timestamp" | Sync log screenshot; "I stopped opening four browser tabs after every change" — beta seller |
| **Safe by default** | "Runs through the same pre-publish preview you already trust" | Diff preview integration; zero mis-published prices across 11,400 beta syncs |

Message-to-segment mapping — the same feature is a different benefit to
different people:

| Segment | Their pain | Lead with | Channel |
|---|---|---|---|
| Growth sellers, 4–6 channels | Flash sales are unusable; the price is wrong somewhere for hours | Pillar 1 | In-app + email |
| Pro sellers and agencies | Can't prove to a client when a change went live | Pillar 2 | Webinar + CSM outreach |
| Starter sellers (2 channels) | Less acute, but the upgrade story | Pillar 1, framed as "what you get on Growth" | Upgrade prompt in-app |
| Prospects | Evaluating against marketplace-native tools | Pillar 1 + 3 | Landing page, paid retargeting |

## 3. Six-week countdown

| Week | Milestone | Owner | Gate to pass |
|---|---|---|---|
| T-6 | Positioning + messaging house signed off; tier confirmed | PM | Marketing, sales and support all agree on the one sentence |
| T-5 | Assets briefed: landing page, demo video, blog, screenshots | Marketing | Brief includes known limitations |
| T-4 | Beta expanded to 40 accounts; sales one-pager drafted | PM | Beta latency p95 under 5 min for 7 consecutive days |
| T-3 | Support brief + help doc in review; pricing/packaging confirmed | Support lead | Top 5 questions answered in writing |
| T-2 | Sales and CS enablement session; objection handling delivered | PM + Sales | Two reps can demo unaided |
| T-1 | Assets final; in-app banner staged; exec paragraph circulated | Marketing | Everything staged behind a flag, dry-run completed |
| **T-0** | **Launch: banner live, email 1 sends, blog + docs publish** | PM | Rollback flag tested that morning |
| T+1 | Email 2 (non-openers), webinar | Marketing | — |
| T+2 | Email 3 (Starter upgrade prompt); first metrics review | PM | — |
| T+4 | 30-day review against targets | PM | Written retro shared |

## 4. Channel plan and budget

| Channel | Audience | Cost | Target | Judged on |
|---|---|---|---|---|
| In-app banner on the publish screen | All 1,240 active accounts | $0 | 24% CTR ≈ 298 clicks | Click → first Live Sync use |
| Lifecycle email, 3-touch | 769 eligible accounts | $0 | 44% open (338), 13% click (44) | Click → activation |
| Help doc + changelog | Everyone | $0 | Live at T-0 | Organic sessions; ticket deflection |
| Launch webinar, "Selling on four channels without a pricing window" | Growth + Pro | $1,200 | 400 registrations, 38% attendance (152) | Attendance → activation |
| Landing page + demo video | Prospects | $3,500 | Live at T-0 | Visitor → trial |
| Paid retargeting, 2 weeks | Lookalike + site visitors | $6,000 | 40 trials at $150 each | Trial → paid, then CAC |
| **Total** | | **$10,700** | | |

**Expansion vs acquisition split: 71% / 29%** of effort by channel, weighted
toward existing customers. That's deliberate — existing-customer channels
convert several times better than acquisition for a feature launch. If your
split is inverted, you are repositioning the product, not launching a
feature, and the plan should say so.

**Paid channel sanity check.** $6,000 for 40 trials is $150 per trial; at
the historical 22% trial-to-paid rate that's 8.8 customers, or a CAC of
**$682**. Against the Growth-tier LTV of $2,054 from Module 9, that's 3.0× —
just above the 3× bar. This channel is worth running and worth killing fast
if the conversion rate comes in lower.

## 5. Enablement

| Team | Deliverable | Deadline | Owner |
|---|---|---|---|
| Support | Help doc, top-5 questions with answers, escalation path, **known limitations** | T-1 week | Support lead |
| Sales / CS | One-pager, demo script, objection handling, list of 60 accounts to call | T-2 weeks | PM |
| Marketing | Positioning, messaging house, assets, dates | T-4 weeks | Marketing |
| Execs | One paragraph they can repeat verbatim | T-1 week | PM |
| Finance | Packaging impact and forecast | T-3 weeks | PM |

**Known limitations, written down and shared** (the highest-value enablement
asset in this plan):

| Limitation | Workaround | Fix ETA |
|---|---|---|
| Image and description changes still use the 4-hour batch | Publish media changes the evening before | Q3 |
| One marketplace rate-limits to 1 update/minute per SKU | Bulk changes there queue; the log shows position | Vendor-dependent |
| Sub-5-minute target is p95, not a guarantee | Latency counter shows live actuals; no SLA language anywhere | n/a |

Objection handling, the three that actually come up:

| Objection | Response |
|---|---|
| "We were told sync was already real time." | It wasn't, and we were not clear enough about that. Here's the old latency, the new one, and where you can see it live. |
| "Is this on my plan?" | Growth and Pro. Starter accounts see the upgrade path in-app; here's the 90-day upgrade offer. |
| "What happens when a marketplace is down?" | The change queues and retries, the log shows *pending*, and you get a notification if it hasn't landed in 30 minutes. |

## 6. Pricing and packaging decision

Live Sync ships in **Growth ($79) and Pro ($199)**, not Starter. The
reasoning follows Module 9's fencing rule: the feature matters exactly when
a wrong price costs real money, which is the moment a seller should move up
a tier. It is a genuine capability fence, not a crippled Starter experience
— Starter accounts keep the batch sync they already have and lose nothing.

Starter accounts see an in-app prompt offering the upgrade. If 120 of the
471 Starter accounts (25.5%) upgrade within 90 days, that's
120 × ($79 − $29) = **$6,000 incremental MRR**, or **$72,000 ARR**. At 78%
gross margin that's $4,680/month of gross profit, which pays back the
$10,700 launch budget in **2.3 months** — before counting any new-customer
acquisition at all.

## 7. Success criteria, set before launch

| Horizon | Question | Metric | Target |
|---|---|---|---|
| Week 1 | Did anyone notice? | Banner CTR | 24% |
| Week 1 | | Email 1 open / click | 44% / 13% |
| Week 1 | | Landing page → trial | 6% |
| Weeks 2–4 | Did they try it? | Eligible accounts using Live Sync ≥ once | 55% of 769 = **423** |
| Weeks 2–4 | | Median time from banner click to first sync | Under 10 minutes |
| Weeks 5–12 | Did it matter? | Still using at week 8 (of those who tried) | 70% |
| Weeks 5–12 | | Starter → Growth upgrades | 120 accounts in 90 days |
| Weeks 5–12 | | Support tickets tagged *stale price on channel* | Down from 90/month to under 56 |
| Weeks 5–12 | | Churn among adopters vs non-adopters | Adopter churn at least 1pt lower |

Only the third horizon is a real result. Week-1 numbers measure the
campaign; week-12 numbers measure the product.

**Rollback triggers**, agreed before launch so nobody has to argue in the
moment:

| Trigger | Action |
|---|---|
| p95 sync latency exceeds 15 minutes for 2 consecutive hours | Flag off Live Sync, fall back to batch, notify affected accounts |
| Any mis-published price attributable to Live Sync | Immediate flag off, incident review before re-enabling |
| Paid trial-to-paid below 12% at day 14 | Kill the paid channel, reallocate to the webinar |

## 8. Risk register

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Sellers read "live" as an SLA | High | Medium | No SLA language; p95 stated plainly in docs and marketing |
| Marketplace rate limits make one channel look broken | Medium | High | Queue position visible in the log; named in the support brief |
| Starter accounts feel a capability was taken away | Medium | Medium | Nothing is removed; framing is "new on Growth", never "no longer on Starter" |
| Support volume spikes on launch day | Medium | Medium | Support briefed at T-1; two extra staffed hours on launch day |
| Launch lands the same week as a marketplace API change | Low | High | Check partner changelogs at T-2; slip a week rather than collide |

## 9. Day-30 review — what actually happened

| Metric | Target | Actual | Read |
|---|---|---|---|
| Banner CTR | 24% | 27% | Beat — the latency counter in the banner did the work |
| Email 1 open / click | 44% / 13% | 46% / 11% | Roughly on target |
| Webinar registrations | 400 | 287 | Missed — announced only 8 days out; needed 3 weeks |
| Eligible accounts activated | 423 (55%) | 469 (61%) | Beat — the strongest signal in the launch |
| Paid trials | 40 | 31 | Missed at $194/trial; CAC would be $882, above the 3× bar |
| Starter upgrades (day 30 run rate) | 40 | 33 | Slightly behind pace |

**Decisions taken from the review:**

1. **Kill the paid channel** at day 30. It missed its own kill criterion;
   reallocate the remaining $2,100 to a second webinar with proper lead time.
2. **Keep and expand the in-app banner pattern.** Showing a live number
   rather than a claim was the single highest-performing element; make it the
   default for T1 and T2 launches.
3. **Move webinars to a 3-week minimum lead time** in the launch checklist.
   This was a process failure, not an audience failure.
4. **The activation beat is the result that matters.** 61% of eligible
   accounts used the feature within 30 days, against a 55% target — the
   launch changed behaviour, which is the only thing a launch is for.

## 10. What made this plan work

- The tier was decided at kickoff, so lead time and budget were real rather
  than retrofitted.
- Positioning was written before any asset, so nine deliverables said the
  same thing.
- Known limitations were written down and shared, so support never had to
  guess.
- Numeric targets existed before launch, so "27% CTR" could be read as a
  beat rather than celebrated as a big number with nothing to compare it to.
- Kill criteria were agreed in advance, so shutting the paid channel down
  was a decision the plan had already made.

## Stretch goals

Build the same plan for a feature you are actually shipping in the next
quarter. Match the structure above section for section, then push further:

1. **Write the full plan** — brief, positioning statement, messaging house
   with three pillars and proof, six-week countdown, channel plan with
   budget, enablement table with known limitations, success criteria across
   three horizons, risk register, and rollback triggers.
2. **Model the economics.** Compute the incremental MRR and ARR your launch
   should produce, the gross profit on it, and how many months it takes to
   pay back your launch budget. If the payback is longer than six months,
   argue for a smaller budget or a bigger target.
3. **Write the day-30 review before you launch**, filling in only the target
   column. Commit to the date. A plan whose review is scheduled behaves very
   differently from one whose review is optional.
4. **Add a segment you were going to ignore** — usually the cheapest tier or
   a non-buying influencer — and write the one line of messaging that makes
   the launch land for them.
5. **Downgrade your own tier by one and re-plan.** If you called it T1,
   write the T2 version with a quarter of the budget. If it produces 80% of
   the outcome, you have learned something expensive about your default.
6. **Run a pre-mortem.** It is 90 days after launch and the feature failed.
   Write the three most plausible reasons, then add a mitigation for each to
   your risk register.

Completing this project means you're ready for **Level 3 · Advanced**.
