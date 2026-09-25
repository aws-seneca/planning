# Event 2. AWS 101: Core Services Workshop

The plan for Event 2, in one place. Attendee steps are in [app/WORKSHOP.md](app/WORKSHOP.md); the facilitator answer key is `SOLUTION.md` (git-ignored, this repo is public).

| | |
|---|---|
| **Date** | Wednesday, October 7, 2026 |
| **Length** | 90 minutes (a hands-on workshop for beginners needs the catch-up time; if it must shrink, cut scope, not time) |
| **Format** | **TBD.** In person is possible; the SSF three-week rule that forced Event 1 online no longer applies |
| **Lead** | Daksh, who approves the plan. Bilal: approval, SSF filing, Meetup listing, account strategy. davedat.: plan and app. Sneha: contributor |
| **App** | [app/](app/README.md), public repo `aws-seneca/aws-101-workshop`. Next.js waitlist page and organizer table |
| **Status** | App rebuilt 2026-09-24, tested locally, **not yet run on real AWS**. No-code challenge needs Bilal's confirmation |

## The plan in one sentence

Every attendee deploys the club's sign-up app to their own EC2 instance, sees that data kept on the server is fragile, moves it to Amazon RDS by changing one line of configuration, then tears everything down so nobody gets a bill.

It follows Bilal's direction (Sep 23): a small app cloned from the org, no CI/CD, database as the challenge. On 2026-09-24 the challenge became cloud-only: attendees change no code. The master plan's line for Event 2 is "Everyone leaves with something running."

An alternative version built on AWS's official EC2 and RDS tutorial is kept separately in [aws-official/](../../aws-official/README.md).

## Run of show

| Time | Segment | Notes |
|---|---|---|
| 0 to 10 | Welcome, what we build today | One diagram: browser, server, database. Why a database belongs outside the server |
| 10 to 35 | **Part 1: app on EC2** | Launch a t3.small, install, build, open it. Explain security groups while `npm install` runs |
| 35 to 55 | **Part 2: create RDS** | "Connect to an EC2 compute resource". While it creates (5 to 10 min): what RDS manages for you, backups, Multi-AZ |
| 55 to 70 | **Part 3: one line in `.env`** | Label flips to RDS PostgreSQL; `rm signups.json` proves the data lives elsewhere |
| 70 to 80 | **Teardown** | Delete the database, terminate the instance. **Never cut this** |
| 80 to 90 | Close | Cloud Practitioner path, what Event 3 is, where to ask questions (Discord) |

If time runs short, cut in this order: the Multi-AZ and backups talk, the cert-path close (move it to Discord). Never cut the hands-on or the teardown.

## Accounts: the blocker, still open

An AWS account needs a payment method at signup (a $1 verification charge; a debit card works; on the free plan nothing is billed unless the student upgrades). Some students will not have one or will not use it.

| Option | Works? | Problem |
|---|---|---|
| Everyone makes a personal account beforehand | Best: they keep it and its credits | Card required; some will not do it in advance |
| AWS Academy Learner Lab | No card, pre-budgeted | Needs a professor with an Academy educator account to host a classroom |
| Locked-down IAM users in the club account | No friction on the day | Real money risk: permission boundaries, a budget alarm, and cleanup needed |
| Club AWS credits | No | Credits apply to an account that already exists |

Recommendation: personal accounts via the pre-event email, with Learner Lab or locked-down IAM users as the fallback. Anyone still without an account pairs with someone who has one. Bilal needs to find the professor for the Learner Lab option.

New accounts can use `t3.small` on the free plan; confirm the instance type and the RDS free-tier option in the dry run.

## Pre-event email (by Sep 30)

- Create your AWS account now, with a step-by-step link. Card required, debit works, $1 verification charge, nothing billed on the free plan unless you upgrade. Choose the **free plan**
- Bring a laptop, not a tablet or phone
- Sign in to the AWS Console before you arrive
- Reply if you get stuck or cannot make an account
- Takes about ten minutes, so do it now

Remind again in Discord 48 hours before and on the day.

## Before the day

- [ ] Dry run of [app/WORKSHOP.md](app/WORKSHOP.md) on a **fresh** AWS account (an account with things already set up hides first-timer problems)
- [ ] Presenter laptop: Console signed in, one instance and database already running to demo from
- [ ] Two or three helpers briefed to float during Parts 1 to 3
- [ ] `SOLUTION.md` shared with helpers directly, not in a public channel
- [ ] Room: arrive 30 minutes early, projector tested, food out before people arrive

## After the event (within 24 hours)

- Discord: recap, how many people got to RDS, the Event 3 date
- Social: a real photo from the hands-on part. "X people deployed to AWS tonight."
- Exec debrief: where people got stuck most, whether Part 2's wait time worked, what to change in WORKSHOP.md
- Check that every demo resource on the presenter account is deleted

## Dates to Oct 7

| What | When | Status |
|---|---|---|
| Account strategy | Was due Sep 19 | Open |
| Format locked, SSF filing submitted | Week of Sep 22 | Unconfirmed |
| Meetup listing published | Sep 26 | |
| Slides built | Sep 29 | |
| Pre-event email and marketing posts | Sep 30 | |
| Dry run on a fresh account | Oct 5 | |

## Open questions

1. In person or online? Drives room booking, helpers, and the SSF filing deadline.
2. How do attendees get accounts? Needs Bilal's Learner Lab answer before the pre-event email.
3. Does Bilal agree to the no-code challenge (he said attendees "do the code side")?
4. Who presents, who floats? Two or three helpers minimum.
5. Expected headcount? Event 1 attendance is the best signal.

The Sep 13 planning notes and the Sep 18 seven-phase runbook that this page replaces are in git history (`workshop-notes.md`, `workshop-runbook-2026-09-18.md`).
