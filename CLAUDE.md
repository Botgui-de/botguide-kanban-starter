# CLAUDE.md

Instructions for any AI assistant working in this project. Read this first.

## How work is organised here

Work comes in **boxes**. A box is one scope of work that opens, gets built, and closes. Everything about a box lives in one folder.

```
.projects/0001-get-started/
  ask.md      what's in this box, in the human's own words
  prd.md      the plan. APPROVED before any code gets written.
  log.md      every turn of the loop — decisions, redirections, the times they said no
  test.md     what was tested, what broke, what was skipped
  audit.md    reading the code back. What would change?
  chat/       raw transcripts
```

## The gate — this is the important part

**Do not write application code until `prd.md` says `Status: APPROVED`.**

Before you write or scaffold anything, check:

1. Does `.projects/0001-get-started/ask.md` exist and have content?
2. Does `prd.md` exist, and does its Status line say APPROVED?

If either is missing, **say so and help write it instead.** Offer to draft the PRD from their ask. Do not start building and do not treat a verbal "go ahead" as approval — the status line is the approval.

This is not bureaucracy. The person you're working with is being evaluated on the thinking, not the output, and skipping this step is the single thing that costs them most.

## Writing the PRD

They describe the problem. You write the plan. They read it, push back, you revise. Keep going until there are no holes.

Your PRD should cover: the problem · what's in scope · what's explicitly out · the people who use it and what each can see and do · the screens · your assumptions · open questions · the definition of done.

**Before they approve it, you must answer this question honestly and in full:**

> **"What did you assume that I didn't tell you?"**

List everything. Every blank in their ask that you filled in on your own — a default, a shape of data, a behaviour they never specified. Do not tidy this list up or leave things off because they seem obvious. It is the most useful thing you produce, because each item is either a decision they haven't made yet or a hole in their understanding.

Two checks before the status line changes:

- **Brief-back.** Restate the PRD as a build plan. If your restatement drifts from the PRD, there's a hole.
- **Handoff.** Could a different person build roughly the right thing from this alone? If it needs the author in the room to explain, it isn't approved.

## The loop

Once the PRD is approved, every piece of work runs the same five steps:

**Plan → Prompt → Test → Refine → Commit**

It runs dozens of times inside one box. Each turn gets one line in `log.md` and one commit.

Start with the simplest version that works, then add. A prompt asking for ten things at once produces a tangle.

## Commits

Prefix with the box number so the history reads as a story:

```
feat(0001): sign-in page renders
fix(0001): contractor could see another contractor's rate
```

Commit at the end of each loop, not at the end of the day.

## While you work

Keep `log.md` current as you go — a reconstruction written at the end is obvious to read and worth much less.

When they reject something you produced, that goes in `log.md` under "Times I said no," with what you gave them, why they rejected it, and what they did instead.

When you make a choice they didn't specify — a library, a pattern, a shape of data — say so out loud rather than burying it. Offer the alternative you didn't pick.

If they ask you to explain something you generated, explain what it does and say plainly which parts you are least confident are correct.

## What not to do

- Don't start coding before the PRD is approved.
- Don't fill silently. If the ask is ambiguous, name the ambiguity rather than picking for them.
- Don't create files whose only purpose is to describe the process. The five above are enough.
- Don't build tooling to check their documentation.
- Don't claim something is tested or verified unless it was. "I didn't test this" is a complete and acceptable answer.
