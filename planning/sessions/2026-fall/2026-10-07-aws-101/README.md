# Event 2. AWS 101: Core Services Workshop

**The plan of record is [workshop-notes.md](workshop-notes.md).** This page holds only the facts at a glance.

## Two versions of the workshop

| Folder | Version | Status |
|---|---|---|
| This folder: [app/](app/README.md) and `SOLUTION.md` (git-ignored) | Attendees deploy the club's own sign-up app to EC2, then connect it to RDS through console settings and an IAM role, no code ([app/WORKSHOP.md](app/WORKSHOP.md)). Based on **Bilal's stated direction**; the no-code change needs his confirmation | App built 2026-09-24, not yet run on EC2 |
| [planning/sessions/aws-official/](../../aws-official/README.md) | Attendees follow AWS's official EC2 and RDS tutorial (PHP sample page), with a companion site | Runbook v2 drafted 2026-09-18, for review |

Shared by both: [workshop-notes.md](workshop-notes.md), the Sep 13 plan, and [workshop-runbook-2026-09-18.md](workshop-runbook-2026-09-18.md), the original seven-phase runbook both versions grew from.

| | |
|---|---|
| **Date** | Wednesday, October 7, 2026 |
| **Format** | **TBD.** In person is possible, the SSF three-week rule that forced Event 1 online does not apply by October |
| **Type** | Technical workshop, hands-on |
| **Status** | Plan drafted 2026-09-13, awaiting Daksh's review |
| **Expanded runbook** | [aws-official/workshop-runbook.md](../../aws-official/workshop-runbook.md), drafted 2026-09-18, draft for review. Merges the root-level runbook with these notes |
| **Proposed length** | 90 minutes, not the 60 used for Event 1 |

## Who is on it

| Person | Role |
|---|---|
| Daksh | Lead. Asked on 2026-09-10 to structure the workshop; reviews and approves the plan |
| davedat. | Drafted the workshop plan |
| Sneha | Contributor |
| Bilal | Approval, SSF filing, Meetup listing, AWS account strategy |

## What the master plan calls for

From the [master plan](../../../master-plan.md):

> EC2, S3, IAM, RDS, VPC, security groups, intro to serverless and cert path. Everyone leaves with something running.

**Everyone leaves with something running** is the phrase that matters. Event 1 demos a deploy; Event 2 is where attendees do it themselves.

Certifications are a running thread, not a standalone event. This is where the AWS Certified Cloud Practitioner path gets introduced properly.

## The blocker

How attendees get AWS accounts. AWS requires a payment method at signup and has replaced the twelve-month free tier with a credits-based Free plan. Unresolved, and it blocks the pre-event email. Full detail in the notes.
