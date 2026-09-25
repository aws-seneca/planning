# AGENTS.md. AWS Student Builder Group @ Seneca

**Read this file first. It is self-contained.** Everything an agent needs to work on this project is here: what the club is, who is on the team, what has happened, what is broken, what is next, and where every link lives. The other files in this folder are source material and detail; you do not need them to be useful, but they are cross-referenced throughout.

Snapshot date: **2026-09-13**, folder reorganized and Event 1 status updated **2026-09-16**. If today's date is significantly later, the "current state" section is stale, check the dates on the files and ask the user what changed.

---

## 1. What this project is

This is **not a software repository.** It is a planning folder for a student club: the AWS Student Builder Group (SBG) at Seneca Polytechnic, Newnham Campus, Toronto. There is no code, no build, no tests. The work is documents: event run-of-shows, schedules, task tracking, marketing copy.

The club runs eight events a year covering cloud, AWS, DevOps, system design, and career prep. Year one is in progress. Event 1 is imminent.

### Vision, in the founder's words

AWS x Seneca is a club for engineers to talk about everything that touches cloud. DevOps, system design, job prep, AWS and Amazon connections. In two years, students should leave Seneca with systems-thinking baked in, skills beyond what the curriculum provides, and industry connections that follow them into their careers. **The club should outlive its founders.** That continuity is explicitly part of the mission.

### Culture principles

- Contribution over attendance. Showing up matters less than giving something.
- No gatekeeping. Curiosity is the only credential.
- Ideas from anyone.
- Engineers teaching engineers, the best sessions come from people who just figured something out.
- Build in public.

### Year one goals

75+ genuinely engaged members; rising excitement across the year; at least one attendee from outside Seneca drawn purely by event quality; members who contribute between meetings; a leadership pipeline so the club survives the founding team.

### Tone rule for anything member-facing

Direct, human, no hype. The run-of-show says it plainly: *"You are not selling a product. You are inviting people into something real."* Match that register in any copy you write, event descriptions, social posts, Discord announcements. Avoid marketing gloss, exclamation stacking, and corporate enthusiasm.

---

## 2. Files in this folder

| File | What it is | When to open it |
|---|---|---|
| `AGENTS.md` | **This file.** Complete briefing | Always, first |
| `README.md` | Human-facing dashboard for the exec team | When the user wants the team-readable version |
| `info/` | **Separate public git repo**, `github.com/aws-seneca/info`: who the club is, club rules, and student-pack guides. Session material (slides, recaps) moved out of it into `planning/sessions/` on 2026-09-24, so there is one place to track sessions. Never copy anything private from this planning folder into it | When changing the public club page or guides |
| `org-profile/` | Separate public git repo `aws-seneca/.github`. `profile/README.md` is the GitHub org landing page | When changing how the org presents itself |
| `planning/sessions/aws-official/site/` | Git-ignored here. Separate public repo `aws-seneca/aws-101-official-tutorial` (renamed from `aws-101-workshop` on 2026-09-23), Pages at `aws-seneca.github.io/aws-101-official-tutorial/`. Companion site that follows AWS's official EC2 and RDS tutorial | When reviewing that tutorial or its companion site |
| `planning/sessions/2026-fall/2026-10-07-aws-101/app/` | Git-ignored here. Public repo `aws-seneca/aws-101-workshop`: the Express + React sign-up app attendees clone onto EC2. Sign-ups save to a local JSON file until attendees set up RDS (Secrets Manager-managed password, "Connect to an EC2 compute resource") and attach an IAM role; the app then finds RDS by itself. Attendee steps: `app/WORKSHOP.md` | When working on the Event 2 app or challenge |
| `planning/sessions/2026-fall/2026-10-07-aws-101/SOLUTION.md` | **Private answer key, git-ignored.** This planning repo is public, so it must never be committed or pasted into a public repo. Replaces the old local solution folder (moved to the Trash 2026-09-24; the private GitHub repo `aws-seneca/aws-101-workshop-solution` still exists) | When checking attendee answers |
| `planning/action-items.md` | Task table: owner, due, status, source date | When working on what's outstanding |
| `planning/timeline.md` | Deduplicated chronological log, Jul 3 – Sep 10 | When you need to know when or why something was decided |
| `planning/sessions/2026-fall/2026-10-07-aws-101/workshop-notes.md` | **Event 2 plan of record.** full drafted workshop plan | When working on Event 2 |
| `planning/sessions/aws-official/workshop-runbook.md` | Draft alternative based on AWS's official EC2 and RDS tutorial; do not assume the team selected it | When comparing workshop versions |
| `planning/sessions/2026-fall/2026-10-07-aws-101/workshop-runbook-2026-09-18.md` | Second runbook draft that appeared at the folder root on Sep 18 (moved here Sep 24). Author not recorded | When comparing workshop versions |
| `planning/sessions/2026-fall/2026-10-07-aws-101/README.md` | Event 2 facts at a glance | For date, format, and owners only |
| `planning/master-plan.md` | Vision, culture, curriculum, 8-event annual arc | For strategic context |
| `planning/sessions/2026-fall/2026-09-16-kickoff/run-of-show.md` | Full 15-slide run-of-show with speaker notes, ~36 KB | Before touching Event 1 delivery |
| `sources/discord-log.md` | Discord log, cleaned and deduplicated | Only to verify a claim. Never cite it as current state |
| `sources/discord-log.raw-backup.md` | The untouched original paste | Only if you suspect the cleaned version lost something |
| `planning/setup.md` | Tooling installed for this project and the one command that reproduces it | When setting up a new machine, or when an AWS fact needs verifying |

### Two files have notes-app frontmatter

`planning/master-plan.md` and `planning/sessions/2026-fall/2026-09-16-kickoff/run-of-show.md` carry YAML frontmatter (`favorited`, `pinned`, `title`, `created`, `modified`) from a notes application export. They were moved and renamed from the folder root (`AWS x Seneca — Master Plan.md`, `Event 1 — Kickoff.md`) at the user's request on 2026-09-24. Keep the frontmatter intact; if the user's notes sync breaks, that move is the cause.

### `sources/discord-log.md` is the Discord log, now cleaned

The original paste spanned several channels (`#announcement`, `#general`, `#marketing`, and an unidentified slides thread), repeated roughly four blocks verbatim, jumped backwards in time, mixed two date formats (`2026-09-04, 22:45` and `9/8/26, 17:55`), and embedded stray file-attachment frontmatter mid-conversation.

`sources/discord-log.md` is now the cleaned version: grouped by channel, chronological within each channel, ISO dates, duplicates and link-preview boilerplate removed. **No message text was edited.** The untouched original is preserved at `sources/discord-log.raw-backup.md`.

**Do not delete `sources/discord-log.raw-backup.md`.** it is the only pristine source, and every derived file was rebuilt from it by hand.

---

## 3. The team

Roles marked *(inferred)* are nowhere stated in the source, they are read off who does what in the channel. Flag them as unconfirmed if the user asks about roles.

| Person | Role | What they actually do |
|---|---|---|
| **Bilal** | President / lead | Runs meetings, SSF and Meetup filings, drafts and approves events, AWS credits, Amazon and partner outreach. Decision-maker on everything |
| **Daksh** | Event Coordinator *(inferred)* | Registered SSF officer. Slides. Now leading Event 2 |
| **Hatim** | Event Coordinator *(inferred)* | Registered SSF officer. Slides |
| **Sneha** | Slides / content *(inferred)* | Built the first Event 1 deck |
| **Maritza** | Marketing | SSF rules and policy, post review, Frosh logistics |
| **Mohit** | Marketing | Writes and schedules LinkedIn and Instagram posts |
| **cynthia** | Marketing | Tagged on marketing work, little channel activity |
| **davedat.** | Member / Event 2 content | **This is the user of this session.** Drafting the Event 2 workshop plan for Daksh. Notes delivered 2026-09-13, awaiting review |

**Bilal, Daksh, and Hatim are the three registered SSF officers**, only they can publish events on the SSF platform.

Marketing is short-handed. Bilal's request for referrals has been open since 2026-08-22.

### Team dynamics worth knowing

Everyone is a student juggling classes and work, so scheduling is hard. Sunday-morning slots didn't work for enough people, and the weekly meeting moved to **Wednesday 7:00 PM ET**. Not everyone makes every meeting, so write decisions down in the channel rather than assuming everyone heard them.

The team often finishes work without posting that it's done. **When tracking status, "no update in channel" is the honest answer, do not infer completion.**

---

## 4. Current state as of 2026-09-13

### Update 2026-09-16: Event 1 is today, slides confirmed

The user confirmed with the exec team on 2026-09-16 that the Event 1 deck is ready for online delivery. The in-person run-of-show problem described in earlier versions of this file is resolved. The final deck lives in `planning/sessions/2026-fall/2026-09-16-kickoff/`.

Still unconfirmed: the post-event feedback form, the Instagram launch post, a screen-share rehearsal of the S3 demo, and whether the AWS credits were distributed. The Sep 9 weekly meeting has no recap posted.

The club has a GitHub org, `aws-seneca`, created 2026-09-16: public repos `info` (club info, session folders, issue forms, CI check) and `.github` (org landing page), plus an `exec` team that owns reviews. The user, davedat. (GitHub `Davedat-110105`), is the only member so far.

### Fall 2026 schedule

| Event | Date | Format | Topic | Status |
|---|---|---|---|---|
| Event 1, Kickoff | Wed, Sep 16 · 1:00–2:00 PM ET | **Online** | Club intro, AWS explained simply, cert path, live S3 deploy | Published on Meetup and LinkedIn |
| Event 2 | Wed, Oct 7 | TBD | AWS 101, core services workshop | Plan drafted Sep 13, awaiting Daksh review |
| Event 3 | Wed, Oct 28 | To be decided | Proposed: CI/CD part 1, container to production | Two-session track drafted Sep 13, needs Bilal's sign-off |
| Event 4 | Wed, Nov 18 | TBD | **Proposed:** CI/CD part 2, the pipeline | Same proposal. Would consume both remaining fall slots |

**Weekly team meeting:** Wednesdays 7:00 PM ET on Google Meet.

---

## 5. Decisions on record

**Event 1 goes online, same date.** Decided 2026-09-03, announced 2026-09-08. SSF introduced a rule that club events cannot be held within the first three weeks of the term. Two options: keep Sep 16 and run online, or push back two weeks. The team kept the date and moved online, because a two-week slip would compress the rest of the fall lineup and complicate back-to-back SSF filings plus Amazon speaker outreach.

The team weighed two concerns: whether the SSF rule also covers online events, and that a midday online event competes with Frosh, which runs events on **Sep 15, 16, and 18**. The reading adopted was that the rule covers physical Seneca spaces, and first-event attendance is usually modest anyway. **The date did not move.** If attendance is low, Frosh overlap is the likely reason.

**Meetup is the canonical RSVP link.** Mohit's first LinkedIn draft used a Google Calendar link (`calendar.app.google/A6gff2G6xL3Qzqse8`). Bilal corrected it on Sep 8: use Meetup. Treat the calendar link as superseded.

**Events are published in two places.** Meetup for public RSVPs, the SSF platform for official approval. Bilal drafted and approved Event 1 himself and intends to hand the process to the event coordinators from Event 2 onward.

**Weekly meetings moved off Sunday mornings** to Wednesday 7:00 PM ET, set via when2meet on Sep 1.

**Food plan, now moot for Event 1.** SSF is relaxed about catering; the plan was pizza via Uber Eats. Relevant again whenever an in-person event happens.

---

## 6. Open items

Full detail with source dates is in `planning/action-items.md`. The short version:

**Blocking Event 1:** adapt the run-of-show for online *(unassigned)*; final slide review *(Sneha, Hatim, Daksh)*; create the feedback form *(unassigned)*; post the Instagram content *(Mohit, Maritza)*; rehearse the S3 demo over screen share *(Bilal)*.

**In flight:** Event 2 workshop plan drafted by davedat. on 2026-09-13, awaiting Daksh's review, see `planning/sessions/2026-fall/2026-10-07-aws-101/workshop-notes.md`; distribute AWS credits *(Bilal)*; recruit marketing help *(Bilal)*; SSF approval walkthrough for coordinators *(Bilal, overdue since Aug 28)*; Amazon speaker outreach *(Bilal)*.

**Blocking Event 2:** how attendees get AWS accounts. AWS requires a payment method at signup and has replaced the twelve-month free tier with a credits-based Free plan ($100 at signup, up to $200 total, account closes at six months or when credits run out). Someone needs to find a professor with an AWS Academy educator account who will host a Learner Lab classroom, or accept that part of the room cannot make an account. This blocks the pre-event email, due around Sep 30.

**Needs a decision:** which Meetup group URL is canonical; a replacement for the on-campus marketing video shoot that assumed an in-person Event 1; Frosh tabling on Sep 15/16/18 *(Bilal and Hatim both working, nobody volunteered, defaulting to no)*; content owners for Events 3 and 4; Event 2 format, in person or online; whether tracking moves off Discord. Daksh and davedat. both named the problem on 2026-09-13, the first time anyone said it out loud.

**Parked ideas:** repost `@awsdevelopers` content; post between events rather than only around them; secure the Helix space for an in-person event.

---

## 7. Event 1 run-of-show, in brief

Full version in `planning/sessions/2026-fall/2026-09-16-kickoff/run-of-show.md`. Summarized so you can reason about it without opening a 36 KB file.

60 minutes, ~15 slides, six phases:

| Phase | Slides | Time | Content |
|---|---|---|---|
| Welcome & Housekeeping | 1–3 | 0–8 min | Settle the room, state the shape of the hour, flag the feedback form and Discord ask upfront |
| The Pitch | 4–6 | 8–18 min | Who's in the room, why this club differs from typical clubs, the vision statement |
| What AWS Is | 7–10 | 18–30 min | Cloud demystified, why companies use it, the five services you'll hear everywhere, what the skills get you |
| The Club | 11–13 | 30–43 min | The year arc, what you walk away with, culture |
| Live Demo | 14 | 43–58 min | S3 static site deploy, end to end, live |
| Close | 15 | 58–60 min | Discord join, next event, open floor |

Design choices in the doc that are deliberate and should be preserved through any rewrite:

- **Housekeeping is stated upfront, not sprung at the end.** Telling people early that you will ask them to join Discord removes friction when the ask lands.
- **The vision statement appears as one line on the slide and is delivered verbally in full.** Putting it all on screen turns delivery into recitation; the room reads ahead and stops listening.
- **Slide 7 explains what the cloud is in the plainest possible terms** and the doc explicitly warns against skipping it for feeling too simple.
- **The demo is the payoff.** Fifteen minutes of the hour. It is what makes the club feel real rather than announced.
- **The third show-of-hands option, "no idea what this is, just curious", is the most important one.** It signals early that curiosity is welcome.

The event promises: AWS explained simply, the AWS Certified Cloud Practitioner path introduced, the year's lineup previewed (workshops, system design, career panel, hackathon), and a live S3 deploy. No prior experience required.

---

## 8. The eight-event annual arc

From the master plan. Q1 Foundation: (1) Kickoff, (2) AWS 101 core services workshop. Q2 Go Deeper: (3) Cloud career panel with Rezzy, hybrid, 2–3 guests from AWS partners, GDG contacts, or Seneca alumni; (4) System design × AWS. Q3 Build: (5) AWS Student Community Day with York U AWS, keynotes, workshop, networking, hackathon, career panel; (6) DevOps, CI/CD and monitoring on AWS. Q4 Ship: (7) Mini hackathon, the flagship event, prioritize AWS credits here; (8) Year wrap and leadership transition.

Between the main events, the plan calls for monthly online community sessions: single-service deep dives, "how does X actually work" conceptual walkthroughs, and member project showcases.

**Certifications are a running thread, not an event.** Introduce the Cloud Practitioner path at AWS 101, revisit it at the career panel, track progress as a group goal.

Note the fall schedule (Sep 16, Oct 7, Oct 28, Nov 18) maps four events into one term, compressing the master plan's Q1–Q2 arc. The stated Event 2 topic matches master-plan Event 2. Events 3 and 4 have no confirmed topics.

**There is a live proposal to pull CI/CD forward** from master-plan Event 6 (Q3 DevOps) into the empty fall slots, its drafts were removed from the folder on 2026-09-24 and are in git history: `events/cicd-track/` in commit `df72b74`. It is scoped as **two sessions**, not one: containers to production first, the pipeline second. That would consume both Oct 28 and Nov 18. It needs Bilal's sign-off, since the Q3 placement was his roadmap decision and this takes the rest of the term.

The container track is not free tier, but it is cheap. App Runner is the recommended target because it auto-deploys on an ECR push, needs no load balancer, and can be paused. Roughly three to four dollars for a room of thirty over a 90-minute session, which still needs confirming with the Pricing Calculator. ECS Express Mode is the step up and adds a load balancer. `s3-fallback-proposal.md` (in git history, `events/cicd-track/` at `df72b74`) holds the S3 fallback that costs nothing and fits one session.

---

## 9. Links and resources

**Public**
- Meetup group: https://www.meetup.com/aws-sbg-at-seneca-polytechnic/
- Meetup group, Newnham listing: https://www.meetup.com/aws-sbg-at-seneca-polytechnic-newnham-campus/
- Event 1 RSVP: https://www.meetup.com/aws-sbg-at-seneca-polytechnic-newnham-campus/events/316473809
- LinkedIn page: https://www.linkedin.com/company/aws-student-builder-seneca-poly/
- Linktree: https://linktr.ee/awsseneca

Both Meetup group URLs appear in the source and nobody has said which is canonical. Posts are splitting traffic between them.

**Internal**
- SSF club signup: https://clubs.ssfinc.ca/SBG/club_signup
- SSF event templates: https://clubs.ssfinc.ca/events_list?show=templates

**Private links and the shared credential** (Event 1 slide deck, meeting poll, design tool password, Google Meet rooms) live in `planning/private.md`. It is git-ignored, because this folder is a public GitHub repo. Never copy its contents into any tracked file.

---

## 10. Working rules for agents

1. **Never delete `sources/discord-log.raw-backup.md`.** It is the pristine source for everything else here. `sources/discord-log.md` is a cleaned derivative and can be regenerated from it.
2. **Keep the folder root to `README.md`, `AGENTS.md`, `CLAUDE.md`.** Everything for a session lives in `planning/sessions/<term>/<YYYY-MM-DD-name>/`, including that session's app repos and git-ignored `SOLUTION.md`. Planning and strategy live in `planning/`.
3. **Do not infer that a task is done.** The team communicates in Discord and often does not close the loop. If there is no dated message confirming completion, the status is "no update in channel."
4. **Trace claims to dates.** Every status line in `planning/action-items.md` and `planning/timeline.md` carries a source date. Preserve that discipline when you add rows.
5. **Keep derived files in sync.** If you learn something new, it belongs in `planning/timeline.md` (what happened, when), `planning/action-items.md` (what is outstanding), and here (current state). Do not let the three drift apart.
6. **Match the tone.** Member-facing copy is direct and human, no hype. See section 1.
7. **Nothing outward-facing without a green light.** Do not post to LinkedIn, Instagram, Discord, Meetup, or the SSF platform. Draft; let a human send.
8. **Dates in this project are in 2026** and the team writes them ambiguously. Normalize to ISO when you write anything new.
9. **Verify AWS facts before they reach students.** AWS changed the free tier from the twelve-month model to a credits-based Free/Paid plan split, and the old version is still what most people repeat. Anything about pricing, free tier, or signup that will be said to a room gets checked first, the `aws-knowledge` MCP server is installed for exactly this, and `aws.amazon.com/free` is the fallback. See `planning/setup.md`.
10. **Put files where the README layout says.** Everything for a session (plans, slides, recaps, code) goes in `planning/sessions/<term>/<YYYY-MM-DD-name>/`, tasks and strategy in `planning/`. `info/` keeps only the public club page and guides (its own git repo). Never copy private material into `info/` or `org-profile/`.
