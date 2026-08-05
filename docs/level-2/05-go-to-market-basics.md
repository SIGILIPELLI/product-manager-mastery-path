# 05 · Go-to-Market Basics

A feature that ships and is never adopted cost the same to build as one that
worked. Go-to-market is the set of decisions that turn "it's in production"
into "the right people know, understand, try, and keep using it" — and in
most companies nobody owns it end to end except the PM. You are not
expected to write the campaign, but you are expected to decide **who it's
for, what it replaces, why they should care, how they'll find out, and what
number tells us it worked**. Marketing, sales, and support execute from
those five answers; if you don't supply them, they'll invent them, and
you'll spend the launch correcting positioning you didn't choose.

This module covers positioning, launch tiering, the messaging house,
channel selection, internal enablement, and launch measurement.

## Positioning before messaging

Messaging is what you say. Positioning is the decision that makes the
message inevitable. Do it in this order.

| Component | Question | ListUp example |
|---|---|---|
| **Competitive alternative** | What would they do if we didn't exist? | Re-typing listings by hand, or a $600/mo enterprise PIM |
| **Unique attributes** | What do we have that alternatives don't? | One edit publishes to every connected channel, with a pre-publish diff |
| **Value** | What does that attribute *do* for them? | A season's stock is live everywhere the day it lands, with no pricing mistakes |
| **Target segment** | Who cares most about that value? | Sellers on 2+ channels with 100–2,000 SKUs and no ops staff |
| **Market category** | What frame makes the value obvious? | Multi-channel listing management (not "e-commerce tools") |

**Positioning statement template:**

> For **[target segment]** who **[situation / problem]**, **[product]** is
> a **[category]** that **[key benefit]**. Unlike **[alternative]**, we
> **[unique differentiator]**.

Two failure modes to avoid: choosing a category so large you're invisible in
it ("e-commerce software"), and differentiating on something the alternative
also has — if your competitor's landing page could carry your sentence
unchanged, you have a description, not a position.

## Tier the launch

Not everything deserves a launch. Over-launching burns your audience's
attention on things they don't care about; under-launching wastes a real
differentiator.

| Tier | Criteria | Activities | Lead time |
|---|---|---|---|
| **T1 — Major** | New category entry, pricing change, or flagship capability | Full campaign: press, webinar, homepage, sales enablement, exec comms | 6–8 weeks |
| **T2 — Significant** | Notable feature that changes what a segment can do | Blog, email, in-app, docs, sales one-pager, support training | 3–4 weeks |
| **T3 — Standard** | Useful improvement, no behaviour change required | Release notes, in-app tooltip, changelog | 1 week |
| **T4 — Invisible** | Bug fixes, perf, internal refactors | Changelog line only | 0 |

Decide the tier at kickoff, not at ship. Tier decides budget, lead time, and
how many people you're allowed to ask for help — deciding it late means all
three arrive late.

## The messaging house

One structure that every asset derives from, so the blog post, the sales
deck, and the in-app tooltip say the same thing in different lengths.

| Layer | Content | Length |
|---|---|---|
| **Roof — positioning statement** | The one sentence everything must be consistent with | 1 sentence |
| **Pillars (3)** | The three reasons to believe, each a customer benefit | 1 phrase each |
| **Proof under each pillar** | Data, demo moment, customer quote, or screenshot | 2–3 items per pillar |
| **Foundation** | The audience-specific value props | 1 line per segment |

| Pillar | Benefit statement | Proof |
|---|---|---|
| Publish once, everywhere | "One edit reaches every channel you sell on" | 30-second demo; 8 marketplaces supported |
| Never push a wrong price | "See exactly what changes before it goes live" | Diff preview screenshot; "caught a $40 pricing error in my own data" — beta seller |
| Live in an afternoon | "Connect your channels without a developer" | Guided setup; median time-to-first-publish 41 min |

**Message-to-segment mapping** matters as much as the pillars — the same
feature is a different benefit to different people:

| Segment | Their pain | Lead with |
|---|---|---|
| Solo seller, 2 channels | Loses weekends to re-typing | Pillar 3 (fast setup), then 1 |
| Growing seller, 4+ channels | Pricing errors cost real money | Pillar 2 (diff preview) |
| Agency managing seller accounts | Client trust and reporting | Pillar 1 + audit trail |

## Choosing channels

Rank channels by **where the segment already is**, not by what's cheap to
produce.

| Channel | Best for | Typical cost | Lead time | Measure |
|---|---|---|---|---|
| In-app announcement / banner | Existing users; highest intent | Low | 1 week | CTR → activation of the new feature |
| Lifecycle email | Existing users not currently logged in | Low | 1–2 weeks | Open → click → activation |
| Docs + changelog | Everyone; drives long-tail discovery | Low | 1 week | Organic sessions to the doc page |
| Landing page + SEO | New demand | Medium | 3–6 weeks | Visitor → trial |
| Webinar / live demo | Complex features needing explanation | Medium | 4 weeks | Registrations → attendance → trials |
| Partner / app directory | Borrowed audience with matching intent | Medium | 4–8 weeks | Installs → activated accounts |
| Paid acquisition | Scaling something already converting | High | 2 weeks | CAC and payback period |
| Press / analysts | T1 only; credibility, not volume | High | 6–8 weeks | Coverage quality; assisted pipeline |

Rule of thumb: for a feature launch, **existing-customer channels convert 5–10×
better than acquisition channels** and cost far less. Most feature launches
should be 70% expansion and 30% acquisition; if yours is inverted, ask
whether you're launching a feature or repositioning the product.

## Internal enablement

The most common launch failure isn't the campaign — it's that support and
sales find out on launch day.

| Team | Needs | Deadline before launch |
|---|---|---|
| Support | Help doc, top 5 expected questions with answers, escalation path, known limitations | 1 week |
| Sales / CS | One-pager, demo script, objection handling, pricing implications, which accounts to call | 2 weeks |
| Marketing | Positioning, messaging house, assets, dates | 3–4 weeks |
| Execs | One paragraph they can repeat verbatim | 1 week |

**Known limitations, written down and shared, are the single highest-value
enablement asset.** A support rep who can say "that's not supported yet,
here's the workaround, it's on the roadmap for Q3" protects the launch. One
who guesses creates a refund.

## Measuring the launch

Set targets before launch, across three horizons:

| Horizon | Question | Metrics |
|---|---|---|
| Week 1 | Did anyone notice? | Reach, CTR, feature page views, trial starts |
| Weeks 2–4 | Did they try it? | Feature activation rate among eligible accounts, time to first use |
| Weeks 5–12 | Did it matter? | Retained usage at week 4+, upgrades attributable, effect on the North Star, churn among adopters vs non-adopters |

Only the third horizon is a real result. Week-1 numbers measure the
campaign; week-12 numbers measure the product.

## Worked example — ListUp launches the pre-publish diff preview

**Tier:** T2. It changes what sellers can safely do, but it doesn't create
a new category or change pricing. Lead time: 4 weeks.

**Positioning statement:** *For multi-channel sellers who can't afford a
pricing mistake on a live listing, ListUp's pre-publish preview is a
publishing safeguard that shows every field that will change, on every
channel, before it goes live. Unlike marketplace-native bulk editors, it
shows the diff across all channels in one screen.*

**Primary segment:** growing sellers on 4+ channels — the segment where a
wrong price is expensive enough to be remembered.

**Channel plan:**

| Channel | Audience | Target |
|---|---|---|
| In-app banner on the publish screen | All active sellers | 22% CTR to the explainer |
| Lifecycle email, 3-touch | Sellers with 4+ channels | 42% open, 12% click |
| Help doc + changelog | Everyone | Live at launch |
| Launch webinar "Publishing without pricing mistakes" | Growth + Pro tiers | 300 registrations |

**Enablement:** support brief two weeks out, including the known limitation
(the preview does not yet cover image changes) and the exact workaround.

**Success criteria:** 40% of active publishers use the preview at least once
in week 4; among those, first-try publish success rises from 87% to 92%;
support tickets tagged *wrong price published* fall by half within 90 days.

**What actually happened:** week-1 CTR came in at 26% and everyone
celebrated. Week-4 activation was 31%, under the 40% target — because the
banner drove people to a doc page rather than into the flow. The fix was a
product change, not a marketing one: default the preview on for accounts
with 4+ channels. That is the lesson of the third horizon — a launch that
reaches everyone and changes no behaviour is a failed launch with good
week-1 numbers.

## Exercise

Pick a feature you're shipping in the next quarter and produce:

1. **A positioning statement** using the template, plus the five-row
   positioning table filled in. Test it: could a competitor publish your
   sentence unchanged? If yes, rewrite the differentiator.
2. **A tier decision** with the criteria that justify it, and the lead time
   and budget that follow from it.
3. **A messaging house**: one positioning sentence, three pillars, 2–3
   proof points per pillar, and a message-to-segment mapping for at least
   two segments.
4. **A channel plan table**: 4+ channels with audience, cost, lead time, and
   the specific metric each will be judged on. Note your expansion vs
   acquisition split and justify it.
5. **An enablement checklist** with owners and dates for support, sales, and
   execs — including a written list of known limitations and workarounds.
6. **Success criteria across all three horizons**, with numeric targets set
   *before* launch. Include what result would make you roll the feature
   back.
