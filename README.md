# AWS Student Builder Group at Seneca: operations hub

Last updated 2026-09-24. **This page is the single source for status, tasks, team, and links.** The repo is public: passwords and meeting links live only in the git-ignored `planning/private.md`.

## Where things are

```
README.md                  ← you are here
AGENTS.md, CLAUDE.md       ← rules and tooling for AI agents working in this folder
planning/
  master-plan.md           ← vision, culture, the eight-event arc
  timeline.md              ← what was decided and done, and when
  private.md               ← passwords, meeting links (git-ignored)
  sessions/
    _template/             ← copy to start a new session
    2026-fall/
      2026-09-16-kickoff/  ← Event 1: deck, slides, recap, run-of-show
      2026-10-07-aws-101/  ← Event 2: README (the plan), SOLUTION.md (git-ignored), app/ (repo aws-101-workshop),
                              site/ (repo aws-101-official-tutorial: the AWS 101 Study Guide)
    aws-official/          ← Event 2 alternative plan on AWS's official PHP tutorial (not chosen)
info/, org-profile/        ← separate public repos: club page and guides, org profile (git-ignored here)
brand/                     ← logos and banner
sources/                   ← Discord log, cleaned and raw (git-ignored)
```

| You have | Put it in |
|---|---|
| A task, owner, or deadline | [Open tasks](#open-tasks) below |
| Something that was decided or done, with its date | `planning/timeline.md` |
| Anything for a session: plan, slides, runbook, recap, code | `planning/sessions/<term>/<YYYY-MM-DD-name>/`, copied from `_template/` |
| An answer key attendees must not see early | `SOLUTION.md` in that session folder (git-ignored) |
| Passwords, meeting links, contact details | `planning/private.md`, never a tracked file |

## Now

**Event 1**, the kickoff, ran online on Sep 16. Deck and recap: [planning/sessions/2026-fall/2026-09-16-kickoff/](planning/sessions/2026-fall/2026-09-16-kickoff/README.md).

**Event 2**, the AWS 101 workshop, is on **Oct 7**. The plan is [planning/sessions/2026-fall/2026-10-07-aws-101/README.md](planning/sessions/2026-fall/2026-10-07-aws-101/README.md). Attendees deploy the club's sign-up app (Next.js) to their own EC2 instance, then move its data to RDS by adding one `DATABASE_URL` line, no code. The app is on `main` of `aws-seneca/aws-101-workshop` but **has not been run on real AWS yet**. Blockers: how attendees get AWS accounts, and whether it is in person or online.

## Sessions

| Date | Session | Format | Status |
|---|---|---|---|
| 2026-09-16 | [Event 1: Kickoff](planning/sessions/2026-fall/2026-09-16-kickoff/README.md) | Online | Done |
| 2026-10-07 | [Event 2: AWS 101 workshop](planning/sessions/2026-fall/2026-10-07-aws-101/README.md) | TBD | Planning |
| 2026-10-28 | Event 3 | TBD | No topic yet |
| 2026-11-18 | Event 4 | TBD | No topic yet |

To add a session: copy `planning/sessions/_template/` to `planning/sessions/<term>/<YYYY-MM-DD-short-name>/` (use `TBD-short-name` until the date is set), fill in its `README.md`, and add a row here. Commit only final slides, exported as `YYYY-MM-DD-short-name.pptx`. Fill in `recap.md` within a week and delete demo AWS resources.

## Open tasks

Statuses are as of the date in the Source column. "No update" means nobody said it was done, not that it wasn't.

| Task | Owner | Due | Status | Source |
|---|---|---|---|---|
| **Event 2:** decide how attendees get AWS accounts (a professor hosting an AWS Academy Learner Lab classroom, or the fallback) | Bilal | Was Sep 19 | Open. Blocks the pre-event email | 2026-09-13 |
| **Event 2:** decide format, in person or online | Bilal, Daksh | Week of Sep 22 | Open | 2026-09-13 |
| **Event 2:** confirm the no-code challenge (Bilal said attendees "do the code side") | Bilal | Before slides | Open | 2026-09-24 |
| **Event 2:** review and approve the plan | Daksh | Was week of Sep 15 | No update | 2026-09-13 |
| **Event 2:** dry run on a fresh AWS account, capturing screenshots | Datta | Oct 5 | Not started | 2026-09-24 |
| **Event 2:** build the slides | Unassigned | Sep 29 | Blocked on approval | 2026-09-13 |
| **Event 2:** pre-event email and marketing posts | Unassigned | Sep 30 | Not started | 2026-09-13 |
| Distribute AWS credits to the team | Bilal | Not set | No update since "I'll send them over" | 2026-08-16 |
| Recruit more marketing help | Bilal | Ongoing | Open since Aug 22 | 2026-08-22 |
| Walk event coordinators through SSF approval and Meetup creation | Bilal | Was Aug 28 | No update | 2026-09-04 |
| Reach out to Amazon for speakers | Bilal | Not set | Not started | 2026-09-04 |
| Assign content owners for Events 3 and 4 | Bilal | Not set | Open | 2026-09-13 |
| Event 1 follow-ups: feedback form, Instagram launch post | Unassigned; Mohit, Maritza | Were before Sep 16 | No update | Run-of-show; 2026-09-08 |

**Needs a decision:** which Meetup group URL is canonical (two circulate and split traffic); a replacement for the on-campus recap videos planned for Event 1.

**Parked:** a two-session CI/CD track (containers to production, then the pipeline) for Oct 28 and Nov 18, with its pricing, cleanup-script, Learner Lab, and dry-run tasks; drafts in git history at `events/cicd-track/` in commit `df72b74`. Moving task tracking off Discord. Posting between events and reposting @awsdevelopers. Booking the Helix space for an in-person event.

## Team

| Person | Role | What they do |
|---|---|---|
| Bilal | President | Runs meetings, SSF and Meetup filings, approves events, AWS credits, partner outreach |
| Datta (davedat.) | Tech lead | Event 2 plan and app, the GitHub org |
| Daksh | Event coordinator (inferred) | SSF officer, slides, leads Event 2 |
| Hatim | Event coordinator (inferred) | SSF officer, slides |
| Sneha | Slides and content (inferred) | Built the first Event 1 deck |
| Maritza | Marketing | SSF rules and policy, post review |
| Mohit | Marketing | Writes and schedules LinkedIn and Instagram posts |
| Cynthia | Marketing | Tagged on marketing work |

"Inferred" roles are read off who does what in Discord; confirm them. Only Bilal, Daksh, and Hatim (the registered SSF officers) can publish events on the SSF platform. Weekly meeting: Wednesdays 7:00 PM ET on Google Meet (link in `planning/private.md`).

## Decisions on record

- **Event 1 went online, same date** (decided Sep 3, announced Sep 8): SSF bans club events in the first three weeks of term; moving two weeks would have squeezed the fall lineup.
- **Meetup is the RSVP link** (Sep 8). The Google Calendar link in an early draft is superseded.
- **Events are published twice**: Meetup for public RSVPs, the SSF platform for approval. Bilal plans to hand this to the event coordinators from Event 2.
- **Weekly meeting is Wednesday 7:00 PM ET** (Sep 1), after Sunday mornings failed.
- **Event 2 is the club's own app on EC2 plus RDS** (Bilal, Sep 23), rebuilt as a no-code challenge on Sep 24, pending his confirmation.
- **Sessions live in `planning/sessions/`** (Sep 24), not in the `info` repo, so there is one place to track them.

## Links

- Meetup: https://www.meetup.com/aws-sbg-at-seneca-polytechnic/ and the Newnham listing https://www.meetup.com/aws-sbg-at-seneca-polytechnic-newnham-campus/
- LinkedIn: https://www.linkedin.com/company/aws-student-builder-seneca-poly/
- Linktree: https://linktr.ee/awsseneca
- GitHub org: https://github.com/aws-seneca (repos `info`, `.github`, `planning`, `aws-101-workshop`, `aws-101-official-tutorial`)
- AWS 101 Study Guide: https://aws-seneca.github.io/aws-101-official-tutorial/
- SSF club signup: https://clubs.ssfinc.ca/SBG/club_signup
- SSF event templates: https://clubs.ssfinc.ca/events_list?show=templates
