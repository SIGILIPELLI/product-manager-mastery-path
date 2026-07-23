# 09 · Stakeholder Communication Basics

Even a perfectly prioritized, well-scoped, well-metriced initiative can stall
if the people around it — leadership, sales, support, engineering — aren't
aligned. This module covers identifying stakeholders, tailoring updates to
different audiences, and running (or contributing to) an effective status
update.

## Mapping your stakeholders

Before writing any update, identify who actually needs one and what they
need from it — a single generic status email to "everyone" usually
under-serves all of them.

| Stakeholder | What they care about | What they need to hear |
|---|---|---|
| Engineering lead | Scope clarity, technical risk, timeline realism | Confirmed requirements, any scope changes, blockers |
| Design lead | Whether the problem/user need is still accurately represented | Any changes to the problem statement or user stories |
| Sales | Whether/when a feature can be promised to a prospect | Honest confidence level and rough timing (see Module 8) |
| Customer support | What's changing that will generate tickets | What's shipping, when, and any known rough edges |
| Executive/leadership | Business impact, how this ties to company goals | Progress against the success metric and the "why" |

## The influence/interest grid

For a larger initiative, it helps to plot stakeholders on how much influence
they have over the decision versus how much interest they have in the
outcome — this determines how much time to invest in each relationship.

|  | **Low interest** | **High interest** |
|---|---|---|
| **High influence** | Keep satisfied — brief updates, no detail overload | Manage closely — regular, detailed updates |
| **Low influence** | Monitor — minimal effort | Keep informed — clear updates, less frequent |

A common mistake is spending equal time on everyone; a VP with high
influence but low day-to-day interest usually wants a two-line summary, not
a 10-slide deck — while an engineer with high interest and (formally) lower
influence over the roadmap often deserves more detail, since they're
executing the plan daily.

## Writing a good status update

A status update should answer four questions, in this order, so a busy
reader gets the important part first even if they stop reading after
sentence two.

1. **What's the current status** (on track / at risk / blocked)?
2. **What changed since the last update?**
3. **What's the plan/next milestone?**
4. **What do you need from the reader (if anything)?**

| Weak update | Strong update |
|---|---|
| "Working on the notifications feature, going okay, will update soon." | "Status: On track. Since last update: engineering finished the backend filter logic; design review happens Thursday. Next milestone: feature-flagged launch to 20% of accounts on the 15th. Need from you: none — flagging in case sales asks about timing this week." |

The strong version front-loads the status (busy readers can stop after
sentence one and still know the headline), and closes with an explicit ask
(or explicit "no ask"), which prevents the reader from wondering if they're
supposed to do something.

## Running an effective status meeting

| Do | Don't |
|---|---|
| Send a written update before the meeting; use meeting time for discussion, not read-aloud | Read the status doc out loud live — wastes attendees' time |
| Timebox open questions/decisions that need a room | Let the meeting drift into solving problems that need a smaller follow-up |
| End with clear action items and owners | End with a vague "let's sync more on this" |

## Handling disagreement from a stakeholder

When a stakeholder pushes back on a prioritization or scope call, the goal
is understanding their underlying concern (often it's about a specific
customer, deal, or risk they're accountable for) rather than treating it as
a fight to win or simply cave to.

1. **Restate their concern** in your own words to confirm you understood it.
2. **Share the reasoning** behind the current decision (referencing the
   problem statement, RICE score, or roadmap theme it ties to).
3. **Identify what would change your mind** — new data, a bigger deal at
   stake, a technical constraint you didn't know about.
4. If genuinely unresolved, **escalate transparently** rather than letting it
   quietly fester — loop in whoever has the authority to make the final call,
   with both perspectives represented fairly.

## Worked example

A sales lead pushes back hard when they see "Enterprise readiness" listed
only as a "Next" (not "Now") theme on the roadmap from Module 8, citing a
specific deal they believe needs SSO to close. Rather than either dismissing
the concern or immediately re-prioritizing on the spot, the PM restates it
("so this specific deal is blocked without SSO — is that right?"), asks for
the deal size and close-date, and takes it back to the next prioritization
session with that new, concrete data point — which is exactly the kind of
signal (Module 3) that can legitimately shift a RICE score's Impact or
Confidence input. The PM follows up in writing within 48 hours either way,
rather than letting the sales lead wonder if they were heard.

## Exercise

For the initiative you've been developing through this level's exercises,
write:

1. A **stakeholder map** (using the influence/interest grid) listing at
   least 4 stakeholders relevant to it.
2. A **status update** (using the 4-question structure) as if the initiative
   is currently "at risk" due to a specific, plausible reason you invent
   (e.g., a dependency slipped, a design review surfaced a new edge case).
