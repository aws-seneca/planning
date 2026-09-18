# AWS Student Builder Group at Seneca: operations hub

Last updated 2026-09-16.

This folder holds the planning for running the club. It is a public GitHub repo; credentials and meeting links stay in the git-ignored `private.md`. Member-facing material goes in `info/`.

## Folder layout

```
aws-seneca/
├── README.md                          ← you are here: status, dates, team, decisions, links
├── AGENTS.md, CLAUDE.md               ← briefing for AI coding agents
├── SETUP.md                           ← tooling setup for this folder
├── AWS x Seneca — Master Plan.md      ← vision, culture, eight-event arc (notes-app file, do not move)
├── Event 1 — Kickoff.md               ← full Event 1 run-of-show (notes-app file, do not move)
├── planning/
│   ├── action-items.md                ← open tasks with owner, due date, status
│   └── timeline.md                    ← what was decided and when
├── events/                            ← private working plans, one folder per event or track
│   ├── 2026-10-07-aws-101/
│   │   ├── README.md                  ← Event 2 facts at a glance
│   │   └── workshop-notes.md          ← Event 2 plan of record
│   └── cicd-track/
│       ├── README.md                  ← CI/CD context, deploy targets, two-session version
│       ├── session-spec.md            ← one-session technical spec, out for review
│       └── s3-fallback-proposal.md    ← earlier S3-only version, the cheap fallback
├── sources/
│   ├── discord-log.md                 ← Discord export, cleaned. Source material only
│   └── discord-log.raw-backup.md      ← untouched original paste. Never delete
├── brand/                             ← logo, org avatar, banner from awsseneca.com
├── info/                              ← PUBLIC git repo, github.com/aws-seneca/info
└── org-profile/                       ← PUBLIC git repo, github.com/aws-seneca/.github
```

Where things go:

| You have | Put it in |
|---|---|
| A task, owner, or deadline | `planning/action-items.md` |
| A decision and the date it was made | `planning/timeline.md` |
| A draft plan for an upcoming event | `events/YYYY-MM-DD-short-name/` |
| Final slides, public event details, a recap | `info/sessions/`, then commit and push |
| Logos and images | `brand/` |
| Passwords, meeting links, contact details | `private.md` (git-ignored), never a tracked file |

## Current state: Event 1 is today

Event 1, the kickoff, runs Wednesday September 16, 2026, from 1:00 to 2:00 PM ET, online.

The slides are ready for online delivery. The exec team confirmed this on 2026-09-16. The deck is in [info/sessions/2026-fall/2026-09-16-kickoff/](info/sessions/2026-fall/2026-09-16-kickoff/README.md).

Still unconfirmed: the post-event feedback form, the Instagram launch post, and a rehearsal of the S3 demo over screen share.

Event 2 needs an account strategy. The workshop plan is drafted in [events/2026-10-07-aws-101/workshop-notes.md](events/2026-10-07-aws-101/workshop-notes.md), and writing it surfaced a blocker. AWS now requires a payment method at signup and has replaced the twelve-month free tier with a credits-based free plan. Somebody needs to find a professor with an AWS Academy educator account who will host a Learner Lab classroom, or accept that some attendees cannot make an account. This blocks the pre-event email.

The club now has a GitHub org, [github.com/aws-seneca](https://github.com/aws-seneca), with a public [info](https://github.com/aws-seneca/info) repo. It has issue forms for event ideas and talk offers, which is one answer to the open question about moving task tracking off Discord.

## Key dates

| Event | Date | Format | Topic | Status |
|---|---|---|---|---|
| Event 1, kickoff | Wed Sep 16, 1:00 to 2:00 PM ET | Online | Club intro, AWS explained simply, cert path, live S3 deploy | Published on Meetup and LinkedIn |
| Event 2 | Wed Oct 7 | To be decided | AWS 101, core services workshop | Plan drafted Sep 13, awaiting Daksh's review |
| Event 3 | Wed Oct 28 | To be decided | Proposed: CI/CD part 1, container to production | Two-session track drafted Sep 13, needs Bilal's sign-off |
| Event 4 | Wed Nov 18 | To be decided | Proposed: CI/CD part 2, the pipeline | Same proposal. Would consume both remaining fall slots |

Conflict to watch: SSF Frosh runs events on Sep 15, 16, and 18. A midday online event on Sep 16 competes with Frosh for attendance. The team kept Sep 16.

Weekly team meeting: Wednesdays at 7:00 PM ET on Google Meet. Set through when2meet after Sunday-morning slots kept failing. Room link in `private.md`.

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

The Event 1 slide deck, meeting poll, design tool password and Google Meet rooms are in `private.md`, which git ignores. This folder is public on GitHub.
