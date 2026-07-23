# 08 · Roadmapping Basics

A roadmap communicates direction and sequencing to a broader audience than a
single PRD does — it's how a PM shows leadership, sales, and the rest of the
company what's coming and, deliberately, how firm or loose those plans are.
This module covers roadmap formats, the crucial theme-vs-feature-list
distinction, and how to communicate uncertainty honestly.

## Theme-based vs. feature-list roadmaps

The most common roadmapping mistake is publishing a list of specific
features with specific dates far in the future — which becomes a promise the
team didn't mean to make, and a source of friction the moment priorities
shift (which they always do).

| Approach | What it looks like | Risk |
|---|---|---|
| **Feature-list roadmap** | "Q3: Dark mode. Q4: SSO. Q1 next year: Mobile app." | Reads as a fixed commitment; painful to change; encourages building the listed thing even after new evidence suggests otherwise |
| **Theme-based roadmap** | "Q3: Reduce onboarding friction. Q4: Enterprise readiness." | Communicates *intent and priority* without over-committing to a specific solution; leaves room for discovery to shape the actual feature |

A theme-based roadmap for "Q3: Reduce onboarding friction" might end up
shipping a redesigned setup wizard, or simplified default settings, or both
— discovery (Module 3) determines the specific solution, while the roadmap
communicated the *priority* months in advance, which is usually what
stakeholders actually need to plan around.

## Time-horizon confidence

Not every part of a roadmap deserves the same level of specificity — the
near term is knowable in detail; the far term isn't, and pretending
otherwise erodes trust when it inevitably changes.

| Horizon | Typical confidence | What to show |
|---|---|---|
| **Now** (this quarter) | High — specific initiatives, mostly locked | Named projects, rough dates |
| **Next** (next quarter) | Medium — themes with likely initiatives | Themes, maybe 1-2 named candidates, no firm dates |
| **Later** (2+ quarters out) | Low — directional only | Broad themes or strategic bets only, explicitly labeled as subject to change |

This "Now / Next / Later" structure (a common public-roadmap format) is
useful precisely because it makes the *confidence level itself* visible,
rather than presenting a Q4-next-year item with the same false precision as
next week's launch.

## Roadmap template

| Theme | Horizon | Status | Notes |
|---|---|---|---|
| Reduce onboarding friction | Now | In progress | Setup-wizard redesign shipping this month |
| Enterprise readiness (SSO, audit logs) | Next | Planned | Discovery starting; scope TBD |
| Expand to a second market segment | Later | Exploring | Directional bet, not yet resourced |

## Communicating a roadmap without over-promising

| Audience | What they need from a roadmap | What to avoid telling them |
|---|---|---|
| Engineering/design | Enough specificity to plan capacity 1-2 quarters out | Firm commitments on "Later" items |
| Sales | Themes that help set customer expectations honestly | Specific ship dates on unbuilt features (creates promises sales can't keep) |
| Leadership | How the roadmap ties to company goals/OKRs | Only a feature list with no "why" |
| Customers (if public) | Directional confidence, not a contract | Exact dates — use quarters or "later this year" instead |

!!! warning "A roadmap is a communication tool, not a contract"
    Every stakeholder audience above will, at some point, try to hold a
    roadmap item to its literal wording as a commitment. Building the habit
    of stating confidence level explicitly every time you share a roadmap
    (out loud, not just implied) heads this off before it becomes a
    trust-damaging surprise later.

## Worked example

A PM presents a Now/Next/Later roadmap in an all-hands. "Now" includes the
onboarding-friction fix from Module 7's example, already in build. "Next"
lists "Enterprise readiness" as a theme, explicitly noting discovery hasn't
started and the specific features (SSO? audit logs? both?) are still open —
sales, in the room, asks if SSO will be ready by a specific renewal date in
that quarter; the PM says clearly: "That's a Next-horizon theme, not a
committed Now item — I can flag your specific timeline need to
prioritization, but I can't commit a date today." This is a harder answer to
give live than a vague "yeah, probably" — but it's the answer that keeps the
roadmap trustworthy the next time it's shared.

## Exercise

Build a Now/Next/Later roadmap table (using the template above) with at
least one theme per horizon, drawing on the initiative you've built a PRD
around plus at least two invented additional themes. For the "Next" and
"Later" rows, write one sentence each on what you would and would not commit
to if a stakeholder pushed for a specific date.
