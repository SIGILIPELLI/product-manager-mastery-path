# 06 · Working with Design & Engineering

A PRD is only useful if it leads to a good collaborative build process. This
module covers the fundamentals of working effectively with designers and
engineers — when to bring each in, how to run a design review, and how to
navigate the tradeoff conversations that come up in nearly every project.

## When to loop in design and engineering

The most common collaboration mistake is bringing design and engineering in
too late — after the PRD is "finished" — which turns their first contribution
into pushback on a document that already feels locked. The fix is
progressive involvement, not a document handoff.

| Stage | Design involvement | Engineering involvement |
|---|---|---|
| Problem discovery (Module 3) | Informal — can offer perspective on past user pain points | Informal — can flag "we already tried this" or technical context |
| Drafting the problem statement/goals | Light review for sanity-check | Light review for sanity-check |
| Drafting user stories | Active — starts sketching flows in parallel | Active — starts flagging feasibility/complexity concerns |
| Acceptance criteria & scope | Co-written with design and engineering, not handed to them | Co-written with design and engineering, not handed to them |
| Build | Design reviews implementation against intent | Engineering owns technical decisions |

The rule of thumb: anyone who will be asked to execute a plan should have had
a chance to shape it before it's finalized — not just review it afterward.

## Running a good design review

Design reviews go badly when PMs either rubber-stamp everything (no useful
feedback) or relitigate the problem statement at the mockup stage (too late,
wastes the designer's work). The fix is to review against a fixed set of
questions, in order:

1. **Does this solve the actual problem statement?** (Not: "do I personally
   like this layout?")
2. **Does it satisfy the acceptance criteria** written in the PRD?
3. **Are there edge cases the design doesn't yet handle** (empty states,
   error states, very long/short content, mobile)?
4. **Is anything here scope creep** relative to the agreed non-goals?
5. Only after 1-4: subjective polish feedback, held loosely.

Asking these in order prevents subjective taste feedback ("I'd prefer a
different color") from derailing a review that should really be about
whether the design solves the validated problem.

## Navigating tradeoff conversations

Nearly every build surfaces a tradeoff the PRD didn't anticipate. The PM's
job isn't to have all the answers — it's to make the tradeoff explicit and
get the right people deciding it together.

| Tradeoff type | Who should weigh in | Example |
|---|---|---|
| Speed vs. scope | PM (impact of cutting), Eng (time saved) | "We can ship in 1 week if we drop multi-select; 3 weeks with it." |
| Quality vs. speed | Eng (technical debt cost), PM (business urgency) | "Shipping without tests now means 2x the fix time later if there's a bug." |
| One segment's needs vs. another's | PM (weighing which segment matters more), Design (can one solution serve both?) | Enterprise wants bulk actions; SMB wants simplicity — can defaults + an advanced mode serve both? |

A useful habit: when a tradeoff surfaces mid-build, don't decide it alone in
a hallway conversation with just the engineer or just the designer — bring
it back to whoever else has context (sometimes that's a 10-minute sync, not
a full meeting), and document the decision and reasoning so it doesn't
re-litigate later.

## Common PM anti-patterns to avoid

| Anti-pattern | Why it damages trust |
|---|---|
| Specifying pixel-level UI details in the PRD | Undermines the designer's expertise; slows them down reconciling PM's sketch vs. their better idea |
| Dictating technical implementation | Undermines the engineer's expertise; can lock in a worse technical approach |
| Changing scope mid-sprint without discussion | Breaks the team's ability to commit to anything; erodes trust in future PRDs |
| Being the only one who talks to users | Design and engineering lose context that would improve their own decisions |

## Worked example

A PM drafts a PRD for an in-app notification center. Rather than attaching
their own rough mockup as "the design," they bring the problem statement and
user stories to the designer *first*, who proposes a slide-out panel instead
of the PM's imagined modal — a better solution the PM wouldn't have thought
of. During the design review, the PM catches that the mockup doesn't show an
empty state (no notifications yet) — a real gap caught by following the
review checklist's step 3, not a taste preference. Mid-build, engineering
flags that real-time updates (via websockets) would take 3 extra days versus
a 30-second polling refresh; the PM checks with the original problem
statement (notifications don't need to be truly instant for this use case)
and greenlights polling, documenting why in the PRD's open-questions log so
the decision isn't revisited without new information.

## Exercise

Using the PRD pieces you drafted in Module 5's exercise, write:

1. A short **design brief** (3-5 sentences) you'd hand a designer *before*
   they start sketching — focused on the problem and constraints, not a
   prescribed solution.
2. One **plausible tradeoff** that might come up during the build of your
   initiative (speed vs. scope, or one segment vs. another), and a sentence
   on who you'd loop in to help decide it and why.
