# MBI Portal - Build Challenge Starter

This repository is your starting point. **Fork it, clone your fork, and build inside it.**

### Getting set up

1. Click **Fork** at the top right of this page. That gives you your own copy, under your own GitHub account.
2. Clone it to your machine:

```bash
git clone https://github.com/YOUR-USERNAME/mbi-portal-starter.git
cd mbi-portal-starter
```

3. Commit before you write a line:

```bash
git commit --allow-empty -m "chore: starting work"
```

Yes, really. Version control is a save-game system. It is what lets you experiment without fear.

You need a free GitHub account to fork. That is all - there is nothing to pay for and nothing to install beyond git and your AI tool.

## Stuck? Type `/team-onboarding`

This repository ships a skill that walks you through the whole thing — what
the five files are for, the gate before any code, and the loop. In your AI
session, type:

```
/team-onboarding
```

It works as soon as you open the folder and trust it. Nothing to install.

## One more file: CLAUDE.md

There's a `CLAUDE.md` in the root of this folder. Your AI assistant reads it automatically and it explains the box, the loop, and the gate — so the bot will prompt you for `prd.md` before it starts building, rather than you having to remember.

It also tells the bot to answer "what did you assume that I didn't tell you?" in full, and to say plainly which parts of its own output it's least sure about. Leave it in place.

---

## The box

Work comes in **boxes**. A box is a scope of work that opens, gets built, and closes. Not a phase, not a sprint - a box.

Your box is `0001-get-started`, and it closes when:

> **The portal runs on your machine and you can log in as all three people.**

That is the whole definition of done. Nothing about hosting.

Later, in real work, a new box opens when a person has a problem - a feature they want or a bug they hit. `0002` is that next box. You are not building it. You are only writing down what would go in it.

## What is in a box

```
.projects/0001-get-started/
  ask.md      what is in this box, in YOUR words, before you open the bot
  prd.md      the bot's version, after the back-and-forth. APPROVED before any code.
  log.md      every turn of the loop. Decisions, redirections, the times you said no.
  test.md     what you tested, what broke, what you skipped
  audit.md    you read your own code. What would you change?
  chat/       raw transcripts from whatever AI tool you used
```

## The loop

Every piece of work runs the same five steps. It will run dozens of times inside this one box.

**Plan -> Prompt -> Test -> Refine -> Commit**

Each turn of the loop gets one line in `log.md` and one commit. Prefix your commit messages with the box number so the history reads as a story:

```
feat(0001): sign-in page renders
fix(0001): contractor could see another contractor's rate
```

## The gate

**No code until `prd.md` says APPROVED.**

Your `0001` is approved personally, by the person who set you this. Send `ask.md` and `prd.md` by **Thursday September 18**.

Getting there is a conversation, not a document you write once. You describe the problem, the bot writes a plan, you read it, you push back, it revises. You keep going until there are no holes.

### Two passes when you read the PRD

Read it twice, looking for two different things.

**Pass 1 - did it understand me?** Anywhere the PRD says something you did not mean, your ask was ambiguous. Fix the ask.

**Pass 2 - do I understand this?** Look for questions it raises that *you cannot answer*. Those are holes in your own understanding, and you were about to build on top of them. This pass is the valuable one and it is the one people skip.

### The question that finds the holes

Before you approve anything, ask the bot:

> **"What did you assume that I didn't tell you?"**

Everything it lists either goes into the PRD as a stated assumption, or gets answered. This one question does most of the work.

### Two tests for "no holes"

- **Brief-back.** Ask the bot to restate the PRD as a build plan. If the restatement drifts, there is a hole.
- **Handoff.** Could a different person build roughly the right thing from this alone? If it needs you in the room to explain, it is not approved.

## Use AI. All of it.

That is not cheating, it is the job. Everyone has the same models, so the AI is not what separates you - what you ask it to do is.

Ask it to teach you while it works:

- **Why did you choose this instead of the alternative? What are the trade-offs?**
- **Show me a completely different way to write this.**
- **What should I learn next to understand this better?**

Those three questions turn every session into a lesson. They also leave a trail in `log.md` that is worth more than the code.

## Submitting

**Push your work to your fork and send the link.** That is the whole submission.

```bash
git push
```

> Push as you go, not once at the end. The commit history is part of what gets
> read - a single commit saying "done" tells us nothing about how you worked,
> and it is the how we are looking at.

Make sure `log.md`, `test.md` and `audit.md` are filled in and pushed. Those
are read as carefully as the code.

**One bonus rung, optional, noticed:** it is deployed somewhere that can be
opened in a browser.

---

Questions are welcome and they count in your favor. Ask.
