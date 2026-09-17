# Botguide Kanban — The Brief

Read this, then write `.projects/0001-get-started/ask.md` in your own words.

This is the brief, not the plan. Writing the plan is your job — that's `prd.md`, and it's where most of the learning is.

---

## What you're building

**Botguide Kanban** is a traditional software Kanban board for task tracking among Botguide contractors. It's used for organising work, coordinating, and estimating workload.

Botguide doesn't have an application for organising work tasks and visualising workload across contractors. This solves that.

Botguide is a software development company that builds software for clients.

> **Everyone who does the work at Botguide is a contractor. There are no employees.** Don't build an `Employee` model and don't assume payroll. Getting this wrong makes the data model wrong underneath everything else.

## The data is purposely vague

You're told to create certain objects — client, project, feature, task — but not told exactly what they are. You'll have to come up with your own from vague descriptions. Draw inspiration from examples online.

The **data model** below is given to you. Everything else is yours to decide.

---

## The three personas

All three log in. Each one wants something different from the same application, and the difference between them is most of the work.

### The owner
Runs Botguide. Creates clients, projects, features and tasks, assigns them, and sees everything.

### The contractor
Does the work. Picks up tasks, moves them across the board, sees what everyone else is working on so the team can help each other out.

### The client
The work is being done for them. Logs in to see how their own projects are going.

**Decide what each of them can see and do.** Full authorization hardening is out of scope — but a client is an outside party, and letting one client see another client's work is not a judgement call you get to make freely. Say what you decided and why.

The same goes for how they sign in. **Logging in is the requirement; the method is open.** It's one of the few genuinely free decisions in this brief, so treat it as one — pick an approach, and be able to say what it costs and what it buys.

## When you have a question, run it past all three personas

Ask it once as each of them before you decide:

1. **As the owner** — if this business were yours, what would you want to open on a Monday morning?
2. **As the contractor** — what do you need to do your job? What would you rather a colleague couldn't see?
3. **As the client** — what would you want to see? What would annoy you if you couldn't?

Most questions answer themselves. Write down the ones that don't — on a real project those are the ones you'd take to whoever owns the decision.

---

## Required features

| Feature | Description |
|---|---|
| **Log in** | All three people can log in, and can log out. Nobody reaches the application without logging in. **How you do it is your choice** — username and password, an emailed code, whatever you can defend. Say why you picked it. |
| **Kanban board** | A view showing tasks in four columns: **To Do · In Progress · Blocked · Completed** |
| **CRUD client** | Create, read, update, delete a client |
| **CRUD project** | Create, read, update, delete a project |
| **CRUD feature** | Create, read, update, delete a feature |
| **CRUD task** | Create, read, update, delete a task |
| **Assign task** | Assign a task to yourself or another user. A task can have no assigned user. |
| **Change task status** | Move a task between To Do, In Progress, Blocked and Completed |
| **Drag and drop** | Change a task's status by dragging it between columns on the board |
| **Story points** | Every task has a story point estimate, in half-point steps from 0.5 to 5. **Half a point is half a day, 1 point is a day, 5 is a full week. Botguide sprints are one week.** |
| **Profile page** | A user has a profile page with their information and settings. |

### Other views — your call

How does someone see clients, projects and features? Tasks live on the board, but where do they see all the projects they're working on?

There's no right answer. Be creative and go with what you think is best.

## Data model

```
client  →  project  →  feature  →  task
```

A task belongs to one feature. A feature belongs to one project. A project belongs to one client.

Feature 1 of project 1 has nothing to do with feature 1 of project 2.

## Seed data

It has to ship with enough data that every screen shows something real — clients, projects, features, and tasks spread across all four columns.

**Seed the three people too.** Someone opening it fresh needs working credentials for the owner, a contractor and a client, or the three logins can't be shown at all. Put them somewhere obvious — a line in your README is fine.

An empty board can't be demonstrated, so seeding it is part of the build.

---

## Tech stack

This one is not your choice. Build it on:

- **Runtime** — Node.js, pnpm, TypeScript, ESLint
- **Framework** — Next.js (App Router, server components and server actions, no separate API backend), React
- **Database** — MySQL, with Drizzle ORM for schema-in-TypeScript and typed queries
- **Styling** — Tailwind CSS

## Deliverable

An application that satisfies the required features, demonstrated on **localhost**. Don't worry about deployment.

## Not in this box

No money — no hours, rates, billing, invoices, cost or ROI. That's a later box.

Also out: importing real data, taking payments, a mobile app, document storage, chat.
