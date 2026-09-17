# CLAUDE.md

Instructions for any AI assistant working in this project. Read this first.

## One fact you must not get wrong

**Everyone who does the work at Botguide is a contractor. There are no employees.**

Never generate an `Employee` model, table, type or role. Never assume payroll or employment status. If the person says "employee" out of habit, use "contractor" anyway and tell them once.

This isn't a naming preference. An employee entity makes the data model wrong underneath everything built on top of it.

## The stack is fixed

Next.js (App Router, server components and server actions, no separate API backend), React, TypeScript, Node.js with pnpm, ESLint, MySQL with Drizzle ORM, Tailwind CSS. `BRIEF.md` has the list.

This is not the person's choice and it is not yours. If they want to use something else, tell them it's fixed and why — a shared stack is what makes the work reviewable across three builds.

## No money in this box

No hours, rates, billing, invoices, cost or ROI. If the person asks for any of it, say it's out of scope for `0001` and belongs in a later box.

## How work is organised

Work comes in **boxes**. A box is one scope of work that opens, gets built, and closes. Everything about a box lives in one folder:

```
.projects/0001-get-started/
  ask.md      what's in this box, in the human's own words
  prd.md      the plan. APPROVED before any code gets written.
  log.md      every turn of the loop — you write this
  test.md     what was tested, what broke, what was skipped
  audit.md    reading the code back. What would change?
  chat/       raw transcripts
```

Point them at **`BRIEF.md`** for what they're building, and at **`/team-onboarding`** if they seem lost.

## The gate — this is the important part

**Do not write application code until `prd.md` says `Status: APPROVED`.**

Before you build or scaffold anything, check:

1. Does `ask.md` exist and have content?
2. Does `prd.md` say APPROVED?

If either is missing, say so and help write it instead. They approve their own PRD here — nobody else is checking. That makes the gate easy to skip, so hold it for them.

This is practice, and the thinking is the part worth practising. Skipping the gate is what costs them most.

## Writing the PRD

They describe the problem. You write the plan. They read it, push back, you revise. Keep going until there are no holes.

Cover: the problem · in scope · explicitly out · the three people and what each can see and do · the screens · your assumptions · open questions · the definition of done.

**Before they approve it, answer this honestly and in full:**

> **"What did you assume that I didn't tell you?"**

List everything — every blank in their ask you filled in on your own. Don't tidy the list or leave things off because they seem obvious. Each item is either a decision they haven't made or a hole in their understanding.

Two checks before the status line changes:

- **Brief-back** — restate the PRD as a build plan. If it drifts, there's a hole.
- **Handoff** — could someone else build the right thing from this alone?

## Questions

Before they settle one, make them run it past all three personas — the owner, the contractor, the client. `BRIEF.md` has the three questions. Walk them through it and let them arrive at the answer; don't answer for them.

What's left, have them write down rather than guess at. On a real project those go to whoever owns the decision; here, naming them is the exercise.

## The loop

Once the PRD is approved, every piece of work runs the same five steps:

**Plan → Prompt → Test → Refine → Commit**

Start with the simplest thing that works, then add. A prompt asking for ten things produces a tangle.

### log.md is yours to write

**You keep `log.md` current — not them.** Write an entry as each turn of the loop finishes, while it's fresh:

- What they were trying to do, what happened, what they decided
- **Times they said no** — what you gave them, why they rejected it, what they did instead
- Choices you made that they didn't specify: a library, a pattern, a shape of data. Say so out loud and note the alternative you didn't pick

Don't wait to be asked and don't reconstruct it at the end — a log written afterwards is obvious to read and worth much less. Tell them when you've written an entry so they can correct it.

## Commits

Prefix with the box number so the history reads as a story:

```
feat(0001): sign-in page renders
fix(0001): contractor could see another contractor's tasks
```

Commit at the end of each turn of the loop. Push after each feature or fix, so the work stays modular and a bad change is easy to roll back.

## FEEDBACK.md is yours too

`FEEDBACK.md` records where **these instructions** failed, and which skills got used. It isn't part of their box. They'll forget it exists; you won't.

Append a row, without being asked, whenever:

- They say an instruction was confusing, ambiguous or wrong — including in passing
- They look for something that isn't there, or ask you something this repo should already answer
- Two of our files contradict each other
- They get stuck for a while, or nearly give up
- **A skill is invoked.** Log which, what for, and whether it helped. Log it when it didn't — that's the more useful row

Write it in their words. Don't soften a complaint into a suggestion and don't leave it out because it criticises the people running this. Then say you logged it, in one line, and carry on.

## What not to do

- Don't start coding before the PRD is approved.
- Don't fill silently. If the ask is ambiguous, name the ambiguity rather than picking for them.
- Don't create files whose only purpose is to describe the process. The five above are enough.
- Don't build tooling to check their documentation.
- Don't claim something is tested unless it was. "I didn't test this" is a complete answer.
