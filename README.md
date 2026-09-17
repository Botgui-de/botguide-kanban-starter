# Botguide Kanban — Practice Project

Fork this repo, clone your fork, and build inside it.

**This is practice.** Nothing is being judged, there's nothing to hand in, no deadline, and no prize. Build it because building it teaches you something. The value is the habit, not the hand-off.

## Getting set up

1. Click **Fork** at the top right. That gives you your own copy under your own GitHub account.
2. Clone it:

```bash
git clone https://github.com/YOUR-USERNAME/botguide-kanban-starter.git
cd botguide-kanban-starter
```

3. Commit before you write a line:

```bash
git commit --allow-empty -m "chore: starting work"
```

Version control is a save-game system. It's what lets you experiment without fear.

You need a free GitHub account to fork. Nothing to pay for, nothing to install beyond git and your AI tool.

## What you're building

Read **[`BRIEF.md`](BRIEF.md)**. It has the required features, the three people who use it, the data model, and the tech stack.

Then write `.projects/0001-get-started/ask.md` in your own words, before you open the bot.

**If you get stuck on a question, `BRIEF.md` tells you what to do first** — ask it as the owner, as the contractor, and as the client. Most questions answer themselves that way. Write down the ones that don't; those are the ones worth carrying into a real project.

## The box

Work comes in **boxes**. A box opens, gets built, and closes. Yours is `0001-get-started`, and it closes when:

> **The Kanban board runs on localhost, you can log in as all three — owner, contractor, client — and every screen has seed data in it.**

That's the whole definition of done. Nothing about deployment.

Everything about a box lives in one folder:

```
.projects/0001-get-started/
  ask.md      what's in this box, in YOUR words, before you open the bot
  prd.md      the plan. APPROVED before any code.
  log.md      every turn of the loop — the bot writes this as you go
  test.md     what you tested, what broke, what you skipped
  audit.md    you read your own code. What would you change?
  chat/       raw transcripts from whatever AI tool you used
```

`.projects/0002-next/ask.md` is the next box. You're not building it — you're scoping it.

## The gate

**No code until `prd.md` says APPROVED.**

**You approve your own.** Nobody is checking, which is exactly why it's worth doing — the discipline is writing a plan and reading it properly before you build, not getting permission.

Getting there is a conversation. You describe the problem, the bot writes a plan, you read it, you push back, it revises. Keep going until there are no holes.

### Read the PRD twice

**Did it understand me?** Anywhere it says something you didn't mean, your ask was ambiguous. Fix the ask.

**Do I understand this?** Look for questions it raises that *you can't answer*. Those are holes in your own understanding. This is the pass people skip.

### Then ask the bot

> **"What did you assume that I didn't tell you?"**

Everything it lists either goes into the PRD as a stated assumption or gets answered. This one question does most of the work.

Two more checks:

- **Brief-back** — ask it to restate the PRD as a build plan. If the restatement drifts, there's a hole.
- **Handoff** — could someone else build roughly the right thing from this alone? If it needs you in the room, it isn't approved.

## The loop

Once the PRD is approved, every piece of work runs the same five steps:

**Plan → Prompt → Test → Refine → Commit**

It runs dozens of times inside one box. Each turn gets one line in `log.md` and one commit.

**The bot keeps `log.md` current.** It writes an entry each turn — what you were trying to do, what happened, what you decided, and the times you rejected what it gave you. Your job is to check it says what actually happened, not to write it from scratch at the end.

Prefix commits with the box number so the history reads as a story:

```
feat(0001): sign-in page renders
fix(0001): contractor could see another contractor's tasks
```

## Use AI. All of it.

That's not cheating, it's the job. Everyone has the same models. What separates you is what you ask them to do.

Ask it to teach you while it works:

- **Why this instead of the alternative? What are the trade-offs?**
- **Show me a completely different way to write this.**
- **What should I learn next to understand this better?**

Those three turn every session into a lesson, and they leave a trail in `log.md` worth more than the code.

## Two files already here

**`CLAUDE.md`** — your AI assistant reads it automatically. It holds the gate, the box convention, and the rule that everyone at Botguide is a contractor. Leave it in place.

**`/team-onboarding`** — type it in your AI session and it walks you through all of this. Nothing to install.

## Tell us what didn't make sense

**[`FEEDBACK.md`](FEEDBACK.md)** is where you record where these instructions let you down, and which AI skills you used.

Where it's confusing or wrong, that's a problem with the instructions, not with you. Your assistant will offer to log things as you go. Let it — it's a useful habit, and it's how this gets better for whoever picks it up next.

## Finishing

Push as you go. **Push after each feature or fix**, not once at the end — small working pieces keep the work modular and make a bad change easy to roll back.

```bash
git push
```

Fill in `log.md`, `test.md` and `audit.md` as you go. On a real project they're read as carefully as the code; here they're the part that turns building into learning.

The box closes when the board runs, the three logins work, and every screen has seed data. Anything past that — deploying it somewhere, extending it — is yours to take as far as you feel like.
