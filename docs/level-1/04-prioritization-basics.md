# 04 · Prioritization Basics

Once you have several validated problems (Module 3), you'll never have
enough engineering time to solve all of them at once. Prioritization is the
discipline of making that scarcity explicit and defensible, instead of
letting it be decided by whoever complained most recently or most loudly.
This module covers three complementary frameworks: RICE, MoSCoW, and
value-vs-effort.

## RICE — a scoring model for comparing initiatives

RICE scores each candidate initiative on four factors and combines them into
one comparable number, which is most useful when you have many competing
ideas and need a defensible ranking.

| Factor | Question it answers | Typical scale |
|---|---|---|
| **Reach** | How many users/accounts does this affect in a given period? | A real number, e.g. "400 users/quarter" |
| **Impact** | How much does it move the needle for each user affected? | 3 = massive, 2 = high, 1 = medium, 0.5 = low, 0.25 = minimal |
| **Confidence** | How sure are we about the Reach/Impact estimates? | 100% = high confidence, 80% = medium, 50% = low |
| **Effort** | How much team-time will this take (person-months)? | A real number, e.g. "1.5" |

**RICE score = (Reach × Impact × Confidence) ÷ Effort**

| Initiative | Reach | Impact | Confidence | Effort | RICE score |
|---|---|---|---|---|---|
| Digest-frequency setting | 800/qtr | 2 | 80% | 0.5 | 2,560 |
| SSO support | 40/qtr | 3 | 100% | 2 | 60 |
| Dark mode | 1,200/qtr | 0.5 | 50% | 1 | 300 |

Even though SSO has the highest per-user impact, its low reach and high
effort drop its score well below the digest-frequency fix — which is exactly
the kind of counter-intuitive result RICE is designed to surface. (Note: a
strategic initiative like SSO might still get prioritized despite a low RICE
score, if it unblocks a specific large deal — RICE informs the decision, it
doesn't replace judgment.)

## MoSCoW — for scoping a single release, not ranking many ideas

MoSCoW answers a different question than RICE: not "which of these many
ideas should we do," but "within *this* release, what's actually required
versus nice-to-have." It's most useful once you've already decided *what*
you're building and need to scope *how much* of it ships in v1.

| Category | Meaning | Example (checkout redesign) |
|---|---|---|
| **M**ust have | Release is not viable without this | Users can complete a purchase |
| **S**hould have | Important, but release could ship without it if forced | Saved payment methods |
| **C**ould have | Nice, genuinely optional | Order confirmation animation |
| **W**on't have (this time) | Explicitly out of scope for this release | Multi-currency support |

The "Won't have" column is doing real work here — writing it down explicitly
prevents scope-creep arguments later ("but I thought we were doing X") and
gives stakeholders a clear, deliberate answer rather than silence.

## Value vs. Effort — the fastest framework, best for a quick gut-check

When you need to prioritize quickly (a backlog grooming session, a
roadmap-planning workshop) without building a full RICE spreadsheet, a
2x2 value/effort plot works well as a first pass.

|  | **Low effort** | **High effort** |
|---|---|---|
| **High value** | Quick wins — do these first | Major projects — plan deliberately |
| **Low value** | Fill-ins — do if there's slack time | Time sinks — avoid or deprioritize |

This framework is intentionally rougher than RICE (no precise numbers) —
it's meant for fast triage of a long backlog, not for making the final call
on a handful of finalists, where RICE's precision earns its extra effort.

## Choosing which framework to use

| Situation | Best fit |
|---|---|
| Large backlog, need a first-pass triage | Value vs. Effort |
| A handful of finalist initiatives, need a defensible ranking | RICE |
| Already decided what to build, need to scope a specific release | MoSCoW |

These aren't mutually exclusive — a common flow is: triage the backlog with
value/effort, RICE-score the top 10-15 candidates that survive triage, then
MoSCoW-scope whichever one gets greenlit into its release.

## Worked example

A team has 20 backlog items after a discovery sprint. Using value/effort,
they quickly sort them into the four quadrants and discard the "low value,
high effort" quadrant entirely (6 items) without further analysis. The
remaining 14 get RICE-scored; the top 3 are selected for the next quarter.
For the winning initiative — a redesigned reporting export — the team then
runs a MoSCoW session: "export to CSV" and "export to PDF" are Musts, "export
to Google Sheets directly" is a Should, "custom report templates" is a Could,
and "scheduled recurring exports" is explicitly a Won't for this release
(flagged as a strong Level 2 candidate instead).

## Exercise

Take the three problem statements you validated (or drafted) in Module 3's
exercise, plus two more you invent. RICE-score all five using the table
format above (estimate Reach/Impact/Confidence/Effort plausibly, but be
explicit these are estimates). Then take whichever initiative scores highest
and run a MoSCoW pass on it, producing at least 2 items in each of the four
categories.
