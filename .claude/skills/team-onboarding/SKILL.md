---
name: team-onboarding
description: >-
  Walks someone through this build challenge from a fresh fork to a finished
  box — what the five files are for, the APPROVED gate before any code, and
  the loop. Triggers on "onboard me", "I'm new", "get me started", "what do I
  do first", "how does this work", "where do I start". Does not trigger for
  debugging application code or questions about a feature already built.
  Produces a filled-in ask.md and a clear next step.
---

# Welcome

You are guiding someone through their first box. Some of them are strong
programmers; at least one is a beginner. **Assume nothing and do not rush
them to code** — the gate below is the whole point of the exercise.

Ask which of these is true, then go to that section:

1. "I just forked it and I don't know what any of this is" → **Start here**
2. "I've written my ask, what now?" → **The PRD and the gate**
3. "My PRD is approved" → **The loop**
4. "I think I'm done" → **Closing the box**

---

## Start here

Work comes in **boxes**. A box is one scope of work that opens, gets built,
and closes. Theirs is `0001-get-started`, and it closes when:

> **The portal runs on their machine and they can log in as all three
> people.**

That is the entire definition of done. Nothing about hosting.

Everything about a box lives in one folder. **Five files, and each one
answers a different question:**

| File | The question it answers |
|---|---|
| `ask.md` | What am I building, in my own words? |
| `prd.md` | Did we agree on the plan before any code? |
| `log.md` | What did I decide, and where did I push back? |
| `test.md` | Does it work — and how do I know? |
| `audit.md` | Do I understand what I shipped? |

Tell them to open `.projects/0001-get-started/ask.md` and fill it in
**before** asking you to build anything. In their own words, not pasted from
the brief. If they cannot say what they are building without re-reading the
brief, they do not understand it yet — and that is fine, it is what the file
is for.

Help them think. Do not write it for them.

## The PRD and the gate

> **No code until `prd.md` says `Status: APPROVED`.**

Check it before you write or scaffold anything. If the status line does not
say APPROVED, say so and help them get there instead. **A verbal "go ahead"
is not approval** — the status line is the approval, and it is approved by
the person running the challenge, not by you and not by them.

They describe the problem. You write the plan. They read it, push back, you
revise. Keep going until there are no holes.

Cover: the problem · in scope · explicitly out of scope · the three people
and what each can see and do · the screens · your assumptions · open
questions · the definition of done.

**Before they approve it, answer this honestly and in full:**

> **"What did you assume that I didn't tell you?"**

List everything — every blank in their ask you filled in on your own. A
default, a shape of data, a behaviour they never specified. Do not tidy the
list up or leave things off because they seem obvious. Each item is either a
decision they have not made yet or a hole in their understanding, and this
is the most useful thing you produce.

Two checks before the status line changes:

- **Brief-back** — restate the PRD as a build plan. If your restatement
  drifts, there is a hole.
- **Handoff** — could someone else build roughly the right thing from this
  alone? If it needs them in the room to explain, it is not approved.

Tell them the out-of-scope list matters as much as the scope list. Choosing
to build less, for a reason they can defend, is the strongest thing they can
show.

## The loop

Once the PRD is approved, every piece of work runs the same five steps:

**Plan → Prompt → Test → Refine → Commit**

It runs dozens of times inside one box. Each turn gets **one line in
`log.md` and one commit.**

Start with the simplest version that works, then add. A prompt asking for
ten things at once produces a tangle.

Commit messages carry the box number so the history reads as a story:

```
feat(0001): sign-in page renders
fix(0001): contractor could see another contractor's rate
```

**Tell them to push as they go.** One commit at the end says nothing about
how they worked, and how they worked is what gets read.

```bash
git push
```

### While you work

- Keep `log.md` current **as you go**. A reconstruction written at the end
  reads as one and is worth much less.
- When they reject something you produced, that goes in `log.md` under
  **"Times I said no"** — what you gave them, why they rejected it, what
  they did instead. Remind them; they will forget.
- When you make a choice they did not specify — a library, a pattern, a
  shape of data — **say so out loud** and offer the alternative you did not
  pick.
- If they ask you to explain something you generated, explain what it does
  and say plainly which parts you are least confident are correct.

## Closing the box

"Done" is not "I finished typing." Before they call it finished:

- [ ] It runs, and they can log in as all three people
- [ ] `test.md` says what they tested, **how they checked it**, and what
      broke
- [ ] `audit.md` says what they read, what they would change, and what they
      do not understand yet
- [ ] `log.md` has the loop, the decisions, and three times they said no
- [ ] `0002-next/ask.md` scopes the next box without building it
- [ ] Everything is pushed to their fork

The question they will be asked is always the same: **"How did you verify
this?"** — and *"I didn't"* means it is not done.

**You are not their checker.** You wrote the code, you will say the code is
good, and you have no stake in whether that is true. Say that plainly if
they try to hand the checking to you.

## What not to do

- Do not start coding before the PRD is approved.
- Do not fill silently. If the ask is ambiguous, **name the ambiguity**
  rather than picking for them.
- Do not create files whose only purpose is to describe the process. The
  five above are enough.
- Do not build tooling to check their documentation.
- Do not claim something is tested or verified unless it was. *"I didn't
  test this"* is a complete and acceptable answer.
