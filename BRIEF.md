# MBI Portal — The Brief

**Read this, then write `.projects/0001-get-started/ask.md` in your own words.**

This is the brief, not the plan. Turning it into a plan is your job — that is
`prd.md`, and it is most of what you are being judged on. Do not copy this
document into either file.

It is deliberately short. **The gaps are the exercise.**

---

## The ask, in the owner's words

> I'd like to have a portal where I can log in and the owner of MBI, or the
> client, can log in. As the MBI owner, I can create a client and contractor
> for MBI, create a project, a task, story points, and assign it to a
> contractor at MBI. The client can log in, and he can view his projects in progress, next
> up, and backlog, and see spend and ROI per application.
>
> You'll be using data from what you already know about the projects and the
> time spent on the projects, and then, based on the total billing for the
> month, apply that dollar amount as cost to that project.
>
> I will have all role privileges, so I can approve everything during the
> project.
>
> MBI stands for MegaBot Industries.

That is the whole request. It is about 130 words and it is genuinely all you
are getting — not because we are being coy, but because that is what a real
request looks like when it arrives.

**MBI is a software development company.** It builds software for clients.

> **Everyone who does the work at MBI is a contractor. There are no employees,
> and there is no plan for any.** Do not model an employee, do not call anyone
> an employee, and do not build anything that assumes payroll. This is not a
> naming preference — it is how the business is actually structured, and
> getting it wrong produces the wrong data model.

---

## The three people

Everything hard about this job lives in the difference between these three.

### The owner

Runs the business. Creates the work, sizes it, assigns it, approves
everything, and prepares what the client sees each month. Sees everything,
always.

### The client

Pays the invoices. Wants to know what is being built, how it is going, and
whether it was worth the money. Sees their own work and their own spend.

### The contractors

Do the work. Update their tasks, report the hours they expect to be paid for.
They can see each other's work, so they can help each other out.

---

## When you have a question, sit in all three chairs

This is the most useful thing in this document.

Before you ask us anything — and before you let the bot decide for you — take
the question and ask it three times:

1. **As the owner.** If this business were yours, what would you want to log
   into on a Monday morning? What would make you trust the numbers enough to
   put them in front of a client?
2. **As the client.** You are paying the invoices. What would you want to see?
   What would make you feel well spent, or badly spent? What would you be
   annoyed to find you could not see?
3. **As a contractor.** You are doing the work and getting paid for it. What
   do you need to see to do your job? What would you consider none of your
   business — and what would you be uncomfortable about a colleague seeing?

Most questions answer themselves once you have done that, because you already
know what you would want. The ones that survive are the good ones, and those
are the ones we want to hear.

**Questions go to ryan@botgui.de and cody@botgui.de. Asking counts in your
favour.**

---

## What is desirable

Wants, not solutions. How you deliver these is your call, and the reasoning is
what gets read.

- Create a client. Create a project. Create features and tasks underneath it.
- Size the work — story points, t-shirt sizes, hours, whatever you can defend.
- Assign work to a person, and let them update it as it moves.
- Contractors record the hours they expect to be paid for.
- The owner approves things. Approval should mean something.
- A month's total client billing becomes cost attributed to projects.
- Project cost rolls up so you can see what an application has cost.
- The client sees progress, spend, and some sense of whether it was worth it.
- Nobody sees what they should not see. **This is the hard part**, and it is
  worth more than any screen.

## Not in this box

Do not spend your two weeks on: importing real historical data · replacing
accounting, payroll or invoicing · taking payments · a mobile app · document
storage · chat.

**Your stack is your choice** — framework, database, styling, testing, all of
it. Say why you picked it. That reasoning counts.

---

## Why this document is short

An earlier attempt at these requirements ran to twelve numbered requirements
and produced fourteen source files and thirteen tests **of its own process**
in five days. Nothing shipped.

The gaps in here are not oversights. Finding them, naming them, and deciding
what to do about them is the exercise.
