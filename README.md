# MBI Portal — Build Challenge Starter

This repository is your starting point. **Fork it, clone your fork, and build inside it.**

## Getting set up

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

You need a free GitHub account to fork. That is all — there is nothing to pay for and nothing to install beyond git and your AI tool.

## The box

Work comes in **boxes**. A box is a scope of work that opens, gets built, and closes. Not a phase, not a sprint — a box.

Your box is `0001-get-started`, and it closes when:

> **The portal runs on your machine and you can log in as all three people.**

That is the whole definition of done. Nothing about hosting.

Later, in real work, a new box opens when a person has a problem — a feature they want or a bug they hit. `0002` is that next box. You are not building it. You are only writing down what would go in it.

### What is in a box

```
.projects/0001-get-started/
  ask.md      what is in this box, in YOUR words, before you open the bot
  prd.md      the bot's version, after the back-and-forth. APPROVED before any code.
  log.md      every turn of the loop. Decisions, redirections, the times you said no.
  test.md     what you tested, what broke, what you skipped
  audit.md    you read your own code. What would you change?
  chat/       raw transcripts from whatever AI tool you used
```

Five files. **Each one answers a different question**, and each is read on its own.

## Start with the brief

Read **[`BRIEF.md`](BRIEF.md)** first. It is one page: what the thing is, the three people who use it, the nine screens, and what is explicitly out of scope.

It is a brief, not a plan. **The gaps in it are deliberate** — finding them, naming them and deciding what to do about them is most of what gets judged. Do not paste it into `ask.md` or `prd.md`.

Then write `.projects/0001-get-started/ask.md` in your own words, before you open the bot.

## The gate

**No code until `prd.md` says APPROVED.**

Send `ask.md` and `prd.md` to **ryan@botgui.de** and **cody@botgui.de** by **Thursday September 18**. Approval comes back from one of them — a verbal "go ahead" is not approval, and neither is the bot telling you it looks good. The status line is the approval.

Getting there is a conversation, not a document you write once. You describe the problem, the bot writes a plan, you read it, you push back, it revises. You keep going until there are no holes.

### Two passes when you read the PRD

Read it twice, looking for two different things.

**Pass 1 — did it understand me?** Anywhere the PRD says something you did not mean, your ask was ambiguous. Fix the ask.

**Pass 2 — do I understand this?** Look for questions it raises that *you cannot answer*. Those are holes in your own understanding, and you were about to build on top of them. This pass is the valuable one and it is the one people skip.

### The question that finds the holes

Before you approve anything, ask the bot:

> **"What did you assume that I didn't tell you?"**

Everything it lists either goes into the PRD as a stated assumption, or gets answered. This one question does most of the work.

### Two tests for "no holes"

- **Brief-back.** Ask the bot to restate the PRD as a build plan. If the restatement drifts, there is a hole.
- **Handoff.** Could a different person build roughly the right thing from this alone? If it needs you in the room to explain, it is not approved.

## The loop

Once the PRD is approved, every piece of work runs the same five steps. It will run dozens of times inside this one box.

**Plan → Prompt → Test → Refine → Commit**

Each turn of the loop gets one line in `log.md` and one commit. Prefix your commit messages with the box number so the history reads as a story:

```
feat(0001): sign-in page renders
fix(0001): contractor could see another contractor's rate
```

## Use AI. All of it.

That is not cheating, it is the job. Everyone has the same models, so the AI is not what separates you — what you ask it to do is.

Ask it to teach you while it works:

- **Why did you choose this instead of the alternative? What are the trade-offs?**
- **Show me a completely different way to write this.**
- **What should I learn next to understand this better?**

Those three questions turn every session into a lesson. They also leave a trail in `log.md` that is worth more than the code.

## Two things already in this repo

**`CLAUDE.md`** — your AI assistant reads it automatically. It explains the box, the loop and the gate, so the bot prompts you for `prd.md` before it starts building rather than you having to remember. It also tells the bot to answer *"what did you assume that I didn't tell you?"* in full, and to say plainly which parts of its own output it is least sure about. **Leave it in place.**

**`/team-onboarding`** — a skill that walks you through all of this. Type it in your AI session:

```
/team-onboarding
```

It works as soon as you open the folder and trust it. Nothing to install.

## Questions

**Questions are welcome and they count in your favor.** Send them to **ryan@botgui.de** and **cody@botgui.de**.

### Before you ask, sit in all three chairs

MBI is a software development company. Three people use this thing: **the owner** who runs it, **the client** who pays for it, and **the contractors** who do the work. Everything hard about the job lives in the difference between them.

Take the question and ask it three times — **as the owner** (if this business were yours, what would you want to log into on a Monday morning, and what would make you trust the numbers enough to show a client?), **as the client** (you pay the invoices — what would you want to see, and what would annoy you to find you couldn't?), and **as a contractor** (you do the work and get paid for it — what do you need to see, and what would you be uncomfortable about a colleague seeing?).

Write the answers down. Most questions answer themselves at that point, because you already know what you'd want. The ones that survive are the good ones, and those are exactly the ones we want to hear.

`BRIEF.md` has more on the three of them.

## Submitting

**Push your work to your fork and send the link.** That is the whole submission.

```bash
git push
```

> Push as you go, not once at the end. The commit history is part of what gets read — a single commit saying "done" tells us nothing about how you worked, and it is the how we are looking at.

Make sure `log.md`, `test.md` and `audit.md` are filled in and pushed. Those are read as carefully as the code. `FEEDBACK.md` too — that one is for us.

**One bonus rung, optional, noticed:** it is deployed somewhere that can be opened in a browser.
