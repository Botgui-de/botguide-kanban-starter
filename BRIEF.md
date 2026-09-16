# MBI Portal — The Brief

**Read this, then write `.projects/0001-get-started/ask.md` in your own words.**

This is the brief, not the plan. It tells you what the thing is and who it
serves. Turning it into a plan is your job — that is `prd.md`, and it is most
of what you are being judged on. Do not copy this document into either file.

---

## What it is

One place for MegaBot Industries to organise the software it builds for its clients, and to show a client what they're getting for their money.

There is one client to begin with, and one client user: that client's CEO.

## Who uses it

| | Why they open it | What they see | What they must never see |
|---|---|---|---|
| **The owner** | Run the work, prepare the client's monthly view | Everything | — |
| **A contractor** | See the work, update assignments, report hours | All MBI work, plus their own hours and their own rate | Another contractor's hours or pay; client rates, bills, spend, ROI |
| **The client CEO** | Understand what's being built and what it's worth | Their own work lanes, spend per application, projected ROI | Other clients; contractor hours, pay or rates; our internal finances |

**Everyone at MBI is a contractor.** There are no employees, and the product should not model them.

## The screens — nine

Sign In · Owner Home · Work Board · People & Rates · My Hours · Monthly Billing · Application Value · Client Home · Client Detail

## The one story that matters

1. The owner creates the month's work, sizes it, assigns contractors.
2. Contractors update their tasks and log the hours they expect to be paid for.
3. The owner reviews those hours and enters the client-billable hours, which may differ. Pay and billing rates are whatever was in effect on the work date.
4. The owner enters the month's total client invoice.
5. Project value = billable hours × client rate. Cost allocated = invoice total × project value ÷ total project value.
6. Project costs roll up by application, across months, to give application spend.
7. The owner enters a low and high expected benefit. Projected ROI = (expected benefit − application spend) ÷ application spend.
8. The client CEO signs in and sees their work lanes, spend and projected ROI.

### Three corrections to that arithmetic

| | |
|---|---|
| **Label the ROI cutoff** | ROI divides a forward-looking benefit by spend-to-date, so the number falls every month as costs accumulate. Show *"based on spend through &lt;date&gt;"*. One line of text; it prevents a bad client conversation. |
| **Store whole cents** | Proportional allocation won't sum to the invoice exactly. Integers, remainder to the last project by stable ID. On a screen whose only job is telling a client what they spent, "these don't quite add up" is a credibility problem. |
| **Contractors see their own pay** | Their own rate and their own earned amount, on **approved hours only**. Never pending, never anyone else's. They negotiated the rate; hiding it is strange, and they're the first users of this system. |

## Scope

**Tier A — the spine.** The nine screens. Three roles enforced server-side. Effective-dated pay and billing rates that survive a rate change. One monthly invoice allocated across projects. Application spend accumulated across months. A projected ROI range. Deployed to DigitalOcean with dev, staging and production.

**Tier B — the backlog.** Comments on tasks. Responsive, loading, empty and denied states. Multi-client isolation hardening. A record of changes and denials. Weekly submission deadlines and late flags. Pay batches. Rate exceptions. Closed-month corrections. Benefit publishing and versioning.

**Senior-owned, never assigned to a trainee.** The authorisation boundary. Data-model invariants. Money math. Timezone logic — the Monday-noon Mountain boundary is a daylight-saving trap that looks small.

## Technical decisions

| | | Why |
|---|---|---|
| **Database** | **Postgres** | Settles ADR-0004 versus the CMS2 deploy plan in favour of Postgres for new products. MySQL on DigitalOcean has no connection pooling and caps at 75 connections per GiB. Managed Postgres supports pgvector, which the RAG work needs, and PostGIS for ZIG. Migrating the existing MySQL estate stays a separate decision. |
| **Auth** | **Better Auth, emailed one-time codes. No passwords.** | ADR-0004 rejected the Better Auth adapter *in combination with a bespoke transaction wrapper* whose writes survived a failed operation. That wrapper is being deleted, so the objection goes with it. Passwords cost roughly triple once forgot-password is included, and add stored secrets plus a reset-link takeover surface. |
| **Email** | Mailpit locally; SMTP on 587 for staging; a transactional provider before the client gets a login | DigitalOcean blocks port 25. |
| **Hosting** | App Platform, Managed Postgres, autodeploy on push per branch | Custom domains via grey CNAME to `ondigitalocean.app` with DO-issued certificates. **Never A-record to App Platform ingress IPs** — that's Cloudflare Error 1000. Proven in production. |
| **Stack** | **Open, pending the build challenge** | See below. |

### The stack question is deliberately open

The three challenge entrants each pick their own stack, justify it, and say how they'd deploy it. We set the standard on 28 September from three real builds rather than from argument.

**Current lean:** React + Vite + a TypeScript API, Drizzle, Postgres, Better Auth, App Platform. Two deployables rather than one. The case against Next.js isn't quality — it's that the server/client component split is the single thing AI gets wrong most often, and we have a beginner on the team. Open to being wrong; that's what the challenge is for.

## Seed data

- Real names and emails for the team — they need to log in, and their own onboarding exercises the invite flow.
- **Fictional rates and dollar amounts in dev and staging.** Real contractor pay and real client invoice totals go in only after the security pass closes.
- **No client login until after that security review.** Placeholder executive in dev.

The arithmetic doesn't care whether the numbers are real.

## Explicitly out

Importing historical data from CMS2, Time Tracker, GitHub or BOS · replacing accounting, payroll or AP/AR · executing payments or invoicing · internal margin or loaded labour cost · claiming realised ROI, as opposed to a projected range · public signup or password login · document storage · client chat · a mobile app.

## Why this document is short

An earlier attempt at these requirements ran to twelve numbered requirements
and produced fourteen source files and thirteen tests **of its own process**
in five days. Nothing shipped. That is the failure mode this brief exists to
avoid, and it is the reason you get a page rather than a specification.

The gaps in here are not oversights. Finding them, naming them, and deciding
what to do about them is the exercise.

## Open

- Stack, until 28 September.
- Whether the winning challenge codebase becomes the foundation, after we verify it runs on our infrastructure.
- Whether the existing MySQL estate migrates to Postgres, and when.
