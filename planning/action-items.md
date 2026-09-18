# Action Items

Status as of 2026-09-13, rows 1 and 2 updated 2026-09-16. Every row traces to a dated message in the Discord export; the Source column gives that date. "No update in channel" means exactly that, the task may be done, but nobody said so.

## Blocking Event 1 (Sep 16)

| # | Task | Owner | Due | Status | Source |
|---|---|---|---|---|---|
| 3 | Create the post-event feedback form promised to attendees | **Unassigned** | Before Sep 16 | No evidence it exists | Slide 3 of the run-of-show |
| 4 | Post the Instagram launch content | Mohit, Maritza | ASAP | Drafted Sep 8, handed to Maritza. No posting confirmation | 2026-09-08 |
| 5 | Rehearse the S3 static-site demo end to end over screen share | Bilal | Before Sep 16 | No update in channel. The run-of-show requires a full dry run; screen sharing changes the flow | Run-of-show, Before the Event |

## In flight

| # | Task | Owner | Due | Status | Source |
|---|---|---|---|---|---|
| 6 | Draft the Event 2 workshop plan as notes (not slides) | davedat. | Not set, "take ur time," but Oct 7 makes the week of Sep 15 the real deadline | **Drafted 2026-09-13.** Awaiting Daksh review, see `events/2026-10-07-aws-101/workshop-notes.md` | 2026-09-10 18:03 (asked), 2026-09-13 11:23 (scope confirmed as notes) |
| 6b | Review the Event 2 workshop notes and approve or redirect | Daksh | Week of Sep 15 | Not started | 2026-09-13 |
| 6c | Resolve how attendees get AWS accounts, find a professor with an AWS Academy educator account who will host a Learner Lab classroom | Bilal | Sep 19 | Not raised yet. Blocks the pre-event email and the workshop's whole opening | 2026-09-13 (identified while drafting notes) |
| 6d | Decide Event 2 format, in person or online | Bilal, Daksh | Week of Sep 22 | Open. The SSF three-week rule no longer applies by October, so in person is possible | 2026-09-13 |
| 6e | Build the Event 2 slide deck from the approved plan | Unassigned | Sep 29 | Blocked on 6b. Daksh: "Presentation can be done later, once it's approved" | 2026-09-13 11:23 |
| 6f | Decide whether CI/CD moves from master-plan Event 6 (Q3) into the fall, and whether it takes **both** Oct 28 and Nov 18 | Bilal | Week of Sep 22 | Proposed 2026-09-13, see `events/cicd-track/README.md`. Scoped as two sessions. Events 3 and 4 currently have no topic at all | 2026-09-13 |
| 6i | Price the chosen deploy target with the AWS Pricing Calculator and put a real number on a slide | Unassigned | Before the event is published | Not started. App Runner is estimated at roughly three to four dollars for a room of thirty per session, which needs confirming | 2026-09-13 |
| 6j | Write a cleanup script that sweeps leftover App Runner services and ECR images from student accounts | Unassigned | Before the first CI/CD session | Not started. Assume some attendees leave without tearing down | 2026-09-13 |
| 6g | Confirm whether AWS Academy Learner Lab accounts can create IAM OIDC providers, ECR repositories, and App Runner services | Bilal | With 6c | Not started. Would sink the CI/CD workshop design specifically | 2026-09-13 |
| 6h | Build the CI/CD template repository and CloudFormation stack | Unassigned | Start Sep 17 if approved | Spec written 2026-09-13, see `events/cicd-track/session-spec.md`. Nothing has been run yet | 2026-09-13 |
| 6k | Get technical review on the CI/CD session spec, in particular whether the S3 target swap is sound and whether 25 to 40 minutes of delivery is realistic | A tech lead outside the club | Before build starts | Sent 2026-09-13 | 2026-09-13 |
| 6l | Dry run the whole CI/CD flow on a fresh AWS account and a fresh GitHub account, timing every step | Whoever presents | Before the event is published | Not started. The spec is untested and the 25 to 40 minute claim is an estimate | 2026-09-13 |
| 7 | Distribute AWS credits to the team | Bilal | Not set | Announced Aug 16 as "I'll send them over." No confirmation | 2026-08-16 |
| 8 | Recruit more marketing help | Bilal | Ongoing | Open ask since Aug 22 | 2026-08-22 |
| 9 | Walk the event coordinators through the SSF event approval and Meetup creation process | Bilal | Aug 28 | Past due date. No update in channel | 2026-09-04 (task list), due date stated as Aug 28 |
| 10 | Reach out to Amazon for speakers for a later event | Bilal | Not set | Mentioned as a dependency on the event schedule; not started | 2026-09-04 |

## Needs a decision

| # | Item | Who decides | Notes |
|---|---|---|---|
| 11 | Resolve which Meetup group URL is canonical | Bilal | Two group URLs are circulating; posts are splitting traffic between them |
| 12 | Replace the plan to film marketing recap videos on campus during Event 1 | Marketing + Bilal | The plan assumed an in-person event. Needs a new format or a new date |
| 13 | Frosh tabling on Sep 15/16/18 | Team | Bilal and Hatim both working. Nobody volunteered. Defaulting to "no" unless someone steps up |
| 14 | Assign content owners for Event 3 (Oct 28) and Event 4 (Nov 18) | Bilal | Nothing scheduled yet; Event 2 is three weeks out. A CI/CD proposal now exists for the Event 3 slot |

## Ideas parked

| Item | Raised by | Date |
|---|---|---|
| Move task tracking off Discord onto a board or shared doc. The `aws-seneca/info` GitHub repo now has issue forms and labels that could serve | Daksh, davedat. | 2026-09-13 |
| Repost @awsdevelopers content on the club's Instagram and LinkedIn | Bilal | 2026-09-04 |
| Post on Instagram and LinkedIn between events, not only around events | Bilal | 2026-09-04 |
| Secure the Helix space for an in-person event | Bilal | 2026-09-04 |

## Completed

| Task | Owner | Completed |
|---|---|---|
| SSF officer confirmation form | Daksh, Hatim, Bilal | Aug 6–7 |
| Create the LinkedIn company page and add the team as admins | Bilal | Aug 6 |
| Create the Meetup group | Bilal | By Aug 16 |
| Club launch post on LinkedIn with the team as collaborators | Bilal | Aug 19 |
| Event 1 launch post on LinkedIn | Mohit | Sep 8, 5:15 PM |
| Discord #announcement post for Event 1 | Mohit | Sep 8 |
| File Event 1 for SSF approval | Bilal | Aug 22 |
| Set a weekly meeting slot everyone can make | Bilal | Sep 1 (Wednesdays, 7:00 PM ET) |
| Reach out to Sneha and davedat. to start Event 2 | Daksh | Sep 10 |
| Adapt the Event 1 deck and speaker notes for online delivery | Exec team | Sep 16, confirmed by davedat. with the team |
| Final review pass on the Event 1 slide deck | Exec team | Sep 16, confirmed by davedat. with the team |
| Create the `aws-seneca` GitHub org, public `info` repo, and org profile | davedat. | Sep 16 |
