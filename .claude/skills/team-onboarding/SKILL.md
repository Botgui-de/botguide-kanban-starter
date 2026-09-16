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

**One fact to hold throughout: everyone who does the work at MBI is a
contractor. There are no employees.** Never scaffold an `Employee` model,
table or role, and never assume payroll. Correct it if they say it out of
habit.

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

**Before they send anyone a question, put them in all three chairs.** MBI is a
software development company: **the owner** runs it, **the client** pays the
invoices, the **contractors** do the work. Have them ask their question once as
each one — what would you want to log into, what would you want to see, what
would you not want a colleague seeing?

Make them answer in writing. Most questions resolve there, because they already
know what they would want. Do not answer for them. The ones that survive go to
ryan@botgui.de and cody@botgui.de.

Asking counts in their favor. Say so — a beginner will assume otherwise.

## The PRD and the gate

> **No code until `prd.md` says `Status: APPROVED`.**

Check it before you write or scaffold anything. If the status line does not
say APPROVED, say so and help them get there instead. **A verbal "go ahead"
is not approval** — the status line is the approval. It is approved by
ryan@botgui.de or cody@botgui.de, not by you and not by them. `ask.md` and
`prd.md` go to both of them by the date they were given.

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

## Logging friction as you go

You are the first users of these instructions. **When something here confuses
them, append a row to `FEEDBACK.md` at the repo root** — what didn't make
sense, where, and how they'd fix it, in their words. Also log every skill they
invoke, including this one, and whether it helped.

Say you logged it, in one line, then carry on. It is not scored and it is not
part of their box.

## Closing the box

"Done" is not "I finished typing." Before they call it finished:

- [ ] It runs, and they can log in as all three people
- [ ] `test.md` says what they tested, **how they checked it**, and what
      broke
- [ ] `audit.md` says what they read, what they would change, and what they
      do not understand yet
- [ ] `log.md` has the loop, the decisions, and three times they said no
- [ ] `0002-next/ask.md` scopes the next box without building it
- [ ] `FEEDBACK.md` has what didn't make sense, the skills they used, and
      the one-thing answer
- [ ] Everything is pushed to their fork, and the link sent to
      ryan@botgui.de and cody@botgui.de by the date they were given

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
