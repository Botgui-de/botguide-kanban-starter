# Botguide Portal — The Brief

Read this, then write `.projects/0001-get-started/ask.md` in your own words.

This is the brief, not the plan. Writing the plan is your job. It's short on purpose — the gaps are the exercise.

---

## The ask, in the owner's words

> I'd like to have a portal where I can log in and the owner of Botguide, or the client, can log in. As the Botguide owner, I can create a client and contractor for Botguide, create a project, a task, story points, and assign it to a contractor at Botguide. The client can log in, and he can view his projects in progress, next up, and backlog.
>
> I will have all role privileges, so I can approve everything during the project.

That's the whole request. Real requests arrive about this long.

Botguide is a software development company. It builds software for clients.

> **Everyone who does the work at Botguide is a contractor. There are no employees.** Don't build an `Employee` model and don't assume payroll. This is how the company actually works, and getting it wrong means the data model is wrong underneath everything else.

---

## The three people

### The owner
Runs the business. Creates projects and tasks, sizes them, assigns them, approves work. Sees everything.

### The client
Wants to know what's being built for them and how it's going. Sees their own projects — in progress, next up, backlog.

### The contractors
Do the work. Update their tasks as things move. They can see each other's work so they can help each other out.

---

## When you have a question, sit in all three chairs

Ask it three times before you send it:

1. **As the owner** — if this business were yours, what would you want to open on a Monday morning?
2. **As the client** — what would you want to see? What would annoy you if you couldn't?
3. **As a contractor** — what do you need to do your job? What would you rather a colleague couldn't see?

Most questions answer themselves. Send the ones that don't, to **ryan@botgui.de** and **cody@botgui.de**. Asking counts in your favour.

---

## What's wanted

These are wants, not instructions. How you build them is your call, and your reasoning is what gets read.

- Create a client. Create a project. Create features and tasks under it.
- Size the work — story points, t-shirt sizes, whatever you can defend.
- Assign work to a person. Let them update it as it moves.
- The owner approves things, and approval means something.
- The client sees their projects: in progress, next up, backlog.
- **Nobody sees what they shouldn't.** This is the hard part and it's worth more than any screen.

### It has to ship with seed data

Enough that every screen shows something real — projects underway, tasks assigned, work in each state. Anyone opening it should log in as each of the three and see a working picture without creating anything first.

An empty app can't be judged or demonstrated, so seeding it is part of the build.

## Not in this box

No money. No hours, rates, billing, invoices, cost or ROI — that's a later box and it's out of scope here.

Also out: importing real data, taking payments, a mobile app, document storage, chat.

**Your stack is your choice** — framework, database, styling, testing. Say why you picked it. That reasoning counts.

---

## Why this is short

An earlier version of these requirements ran to twelve numbered items. It produced fourteen source files and thirteen tests of its own process in five days, and shipped nothing.

The gaps here aren't oversights. Finding them and deciding what to do about them is the exercise.
