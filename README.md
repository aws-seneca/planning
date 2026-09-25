# AWS Student Builder Group at Seneca: operations hub

Last updated 2026-09-24.

This folder holds the planning for running the club. It is a public GitHub repo; credentials and meeting links stay in the git-ignored `planning/private.md`. Member-facing material goes in `info/`.

## Folder layout

```
aws-seneca/
├── README.md                    ← you are here: status, dates, team, decisions, links
├── AGENTS.md, CLAUDE.md         ← briefing for AI coding agents
├── planning/                    ← internal: the team's working files
│   ├── master-plan.md           ← vision, culture, eight-event arc
│   ├── action-items.md          ← open tasks with owner, due date, status
│   ├── timeline.md              ← what was decided and when
│   ├── setup.md                 ← tooling for this folder
│   ├── private.md               ← passwords and meeting links. Git-ignored
│   └── sessions/
│       ├── README.md            ← index of every session, and how to add one
│       ├── _template/           ← copy this to start a new session
│       ├── 2026-fall/
│       │   ├── 2026-09-16-kickoff/
│       │   │   ├── README.md, deck.md, recap.md   ← Event 1 details, slide text, recap
│       │   │   ├── 2026-09-16-kickoff.pptx        ← final slides
│       │   │   └── run-of-show.md                 ← full run-of-show with speaker notes
│       │   └── 2026-10-07-aws-101/                ← Event 2, the club's own app (Bilal's direction)
│       │       ├── README.md                      ← the Event 2 plan: run of show, accounts, email, dates
│       │       ├── SOLUTION.md                    ← challenge answer key. Git-ignored, never pushed
│       │       └── app/                           ← the sign-up app. PUBLIC repo aws-seneca/aws-101-workshop
│       └── aws-official/        ← Event 2 alternative, built on AWS's official EC2 and RDS tutorial
│           ├── README.md
│           ├── workshop-runbook.md                ← runbook v2
│           └── site/                              ← companion site. PUBLIC repo aws-seneca/aws-101-official-tutorial
├── info/                        ← PUBLIC git repo, github.com/aws-seneca/info: who we are, club rules, student-pack guides
├── org-profile/                 ← PUBLIC git repo, github.com/aws-seneca/.github
├── brand/                       ← logo, org avatar, banner from awsseneca.com
└── sources/                     ← Discord log, cleaned and raw. Git-ignored
```

Where things go:

| You have | Put it in |
|---|---|
| A task, owner, or deadline | `planning/action-items.md` |
| A decision and the date it was made | `planning/timeline.md` |
| Anything for a session: plan, slides, runbook, recap, code | `planning/sessions/<term>/<YYYY-MM-DD-name>/` (copy `planning/sessions/_template/`) |
| An answer key or anything attendees must not see early | `SOLUTION.md` in that session folder (git-ignored) |
| Logos and images | `brand/` |
| Passwords, meeting links, contact details | `planning/private.md` (git-ignored), never a tracked file |

Only `README.md`, `AGENTS.md`, and `CLAUDE.md` live at the top level.

## Current state: Event 2 is on October 7

Event 1, the kickoff, ran online on Wednesday September 16. The deck is in [planning/sessions/2026-fall/2026-09-16-kickoff/](planning/sessions/2026-fall/2026-09-16-kickoff/README.md).

Event 2 is the AWS 101 workshop, planned in [planning/sessions/2026-fall/2026-10-07-aws-101/README.md](planning/sessions/2026-fall/2026-10-07-aws-101/README.md). Following Bilal's direction, attendees clone the club's sign-up app (a Next.js waitlist page and organizer table), run it on their own EC2 instance, then move its data from a local JSON file to RDS PostgreSQL by adding one `DATABASE_URL` line, with no code changes. This differs from Bilal's Sep 23 wording that attendees "do the code side"; confirm with him. The app was rebuilt on 2026-09-24 and has not yet been run on real AWS.

Still open for Event 2:

- **Accounts.** AWS now requires a payment method at signup and has replaced the twelve-month free tier with a credits-based free plan. Somebody needs to find a professor with an AWS Academy educator account who will host a Learner Lab classroom, or accept that some attendees cannot make an account. This blocks the pre-event email.
- **Format.** In person or online is not decided.
- **Runbook.** [workshop-runbook.md](planning/sessions/aws-official/workshop-runbook.md) still describes AWS's PHP sample page instead of the Express app. A step-by-step attendee tutorial is still to be written.

The club now has a GitHub org, [github.com/aws-seneca](https://github.com/aws-seneca), with a public [info](https://github.com/aws-seneca/info) repo. It has issue forms for event ideas and talk offers, which is one answer to the open question about moving task tracking off Discord.

## Key dates

| Event | Date | Format | Topic | Status |
|---|---|---|---|---|
| Event 1, kickoff | Wed Sep 16, 1:00 to 2:00 PM ET | Online | Club intro, AWS explained simply, cert path, live S3 deploy | Done |
| Event 2 | Wed Oct 7 | To be decided | AWS 101, core services workshop | Plan drafted Sep 13; workshop app built Sep 24 |
| Event 3 | Wed Oct 28 | To be decided | Proposed: CI/CD part 1, container to production | Two-session track drafted Sep 13, needs Bilal's sign-off |
| Event 4 | Wed Nov 18 | To be decided | Proposed: CI/CD part 2, the pipeline | Same proposal. Would consume both remaining fall slots |

Conflict to watch: SSF Frosh runs events on Sep 15, 16, and 18. A midday online event on Sep 16 competes with Frosh for attendance. The team kept Sep 16.

Weekly team meeting: Wednesdays at 7:00 PM ET on Google Meet. Set through when2meet after Sunday-morning slots kept failing. Room link in `planning/private.md`.

## Team and roles

Roles marked "inferred" are not stated anywhere in the channel. They are read off who does what. Confirm and correct them.

| Person | Role | What they do in the channel |
|---|---|---|
| Bilal | President and lead | Runs meetings, handles SSF and Meetup filings, drafts and approves events, handles AWS credits and partner outreach |
| Daksh | Event coordinator (inferred) | Registered SSF officer, slides, now leading Event 2 |
| Hatim | Event coordinator (inferred) | Registered SSF officer, slides |
| Sneha | Slides and content (inferred) | Built the first slide deck draft |
| Maritza | Marketing | SSF rules and policy, Instagram and LinkedIn review, Frosh logistics |
| Mohit | Marketing | Writes and schedules the LinkedIn and Instagram posts |
| cynthia | Marketing | Tagged on marketing work, little channel activity |
| davedat. | Member and Event 2 content | Drafting the Event 2 workshop plan for Daksh |

Bilal, Daksh, and Hatim are the three registered SSF officers. Only they can publish events on the SSF side.

Marketing is short-handed. Bilal asked for referrals on 2026-08-22 and that ask is still open.

## Decisions on record

Event 1 goes online on the same date. Decided 2026-09-03, announced 2026-09-08. SSF introduced a rule that club events cannot run within the first three weeks of the term. The team chose to keep Sep 16 and move online, because a two-week slip would compress the rest of the fall lineup and complicate back-to-back event filings and Amazon speaker outreach.

Meetup is the canonical RSVP link. Mohit's first LinkedIn draft used a Google Calendar invite link, `calendar.app.google/A6gff2G6xL3Qzqse8`. Bilal corrected this on 2026-09-08. Treat the calendar link as superseded.

Events publish in two places. Meetup handles public RSVPs and the SSF platform handles official approval. Bilal drafted and approved Event 1 himself and intends to hand the process to the event coordinators from Event 2 onward.

Weekly meetings moved off Sunday mornings. Sunday-morning slots didn't suit enough people, so on 2026-09-01 the slot moved to Wednesday evening.

The food plan is moot for Event 1. SSF is relaxed about catering and the plan was pizza through Uber Eats. This matters again whenever an in-person event happens.

## Open questions

- Does anyone table at Frosh? Bilal and Hatim are both working and nobody else volunteered.
- Marketing recap videos were going to be filmed on campus during Event 1. With the event online, this needs a replacement or a new date.
- Were the AWS credits distributed? Bilal said on 2026-08-16 that he would send them and nothing has confirmed it since.
- Who owns content for Events 3 and 4?
- Should task tracking move off Discord? Daksh and davedat. both raised on Sep 13 that assignments get lost in ordinary conversation. Worth ten minutes at the next weekly meeting.

## Links and resources

Public:

- Meetup group, https://www.meetup.com/aws-sbg-at-seneca-polytechnic/
- Meetup group, Newnham Campus listing, https://www.meetup.com/aws-sbg-at-seneca-polytechnic-newnham-campus/
- Event 1 RSVP, https://www.meetup.com/aws-sbg-at-seneca-polytechnic-newnham-campus/events/316473809
- LinkedIn page, https://www.linkedin.com/company/aws-student-builder-seneca-poly/
- Linktree, https://linktr.ee/awsseneca

Both Meetup group URLs appear in the channel and nobody has said which is the real one. Worth resolving so posts stop splitting traffic.

Internal tools:

- SSF club signup, https://clubs.ssfinc.ca/SBG/club_signup
- SSF event templates, https://clubs.ssfinc.ca/events_list?show=templates

The Event 1 slide deck, meeting poll, design tool password and Google Meet rooms are in `planning/private.md`, which git ignores. This folder is public on GitHub.
