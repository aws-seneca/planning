# Proposal. CI/CD to AWS as Event 3

**From davedat. · 2026-09-13 · for Daksh and Bilal**

> **Superseded in part by [events/cicd-track/README.md](README.md).** This document proposed a single session deploying a static site to S3. The scope has since been set to what was actually wanted, commit, build a container image, deploy to production, which is a two-session track using ECS Express Mode. Read `events/cicd-track/README.md` first.
>
> **This document is still the fallback plan.** If the container version comes out too expensive or too tight on prep time, the S3 design below is the version that costs nothing and fits one session. The slot reasoning in the next two sections applies to both.

The idea on the table was to make Event 2 a CI/CD workshop instead of AWS 101. This is a counter-proposal: **do it, but as Event 3 on Oct 28, not Event 2 on Oct 7.**

---

## The conflict nobody has flagged yet

**The master plan already has this event.** Q3, Event 6:

> **DevOps, CI/CD, and monitoring on AWS.** GitHub Actions, Docker, ECR, ECS, CloudWatch, X-Ray. End-to-end deploy walkthrough.

So the question is not whether to run a CI/CD workshop. It is *when*, and whether running it early cannibalizes Event 6 or just moves it. **Bilal needs to sign off on this either way.** it is his roadmap and the Q3 slot was deliberate.

My read: moving it earlier is a straight upgrade. The fall term has four events and two of them (Oct 28, Nov 18) currently have **no topic assigned at all.** Meanwhile the Q3 DevOps slot is months away and the club may well want a hackathon-prep or project-showcase session there instead. Pulling CI/CD forward fills a real gap now and leaves Q3 free.

---

## Why not Event 2

Three weeks out, Event 2 is the wrong slot for this, for reasons that have nothing to do with whether CI/CD is a good topic.

**1. It breaks the on-ramp.** Event 1 is advertised as "zero experience needed," and its own run-of-show includes a show-of-hands option for people who *"showed up with genuinely no idea what this is."* Those people are the target audience. Event 2 is the first technical event and the first thing they do with their own hands. A GitHub Actions pipeline assumes git, a GitHub account, a working repo, the command line, and a mental model of what "deploy" even means. Most of that room does not have those yet. You would lose the exact people Event 1 was designed to recruit.

**2. The debug loop is brutal at scale.** When an EC2 instance does not respond, the cause is visible in the console in about ten seconds and it is almost always the security group. When a GitHub Actions workflow fails, you get a red X, and you expand a log, and you fix the YAML, and you push, and you wait three minutes to find out. With thirty people each failing two or three times, a 90-minute session is gone. This is a real difference in kind, not just difficulty.

**3. Prep time we do not have.** Event 1 has not happened yet. The Event 2 account strategy is unresolved and blocks the pre-event email due Sep 30. A CI/CD workshop needs a template repo, a CloudFormation stack, and a tested end-to-end run on a fresh account, that is a couple of weekends of work, and the same people doing it are running Event 1 next Wednesday.

**But you do not have to wait to show it.** See the last section.

---

## What Event 3 would be

**Push to deploy.** Attendee edits a file, commits, pushes to GitHub. A workflow runs on its own. They refresh a URL and see their change live, with nobody having touched the AWS Console.

That is the moment. Everything else in the session serves it.

### Deploy target: S3 static site, not ECS

The master plan's Event 6 line lists Docker, ECR, and ECS. **Cut all three for this version.** Containers are a second workshop, image builds, registries, task definitions, and service updates are each their own source of failure, and none of them are the lesson. The lesson is *something watches your repo and acts on it without you.*

`aws s3 sync` is one line, has no cold start, no container to debug, and the result is a URL that visibly changes. Save ECS for the Q3 event, which now has room for it.

### Auth: OIDC, with the hard part pre-built

This is the design decision that determines whether the workshop works.

The easy path is generating an IAM access key and pasting it into GitHub Secrets. **Do not do this.** It teaches thirty students that long-lived AWS keys in a CI system are normal, and it puts thirty long-lived keys into thirty student GitHub accounts. Leaked AWS keys are the single most common way a student project becomes a horror story.

The correct path is OIDC: GitHub requests a short-lived token, AWS trusts GitHub's identity provider, and the workflow assumes a role. No stored secrets at all. But hand-building the trust policy, provider registration, the `sub` claim condition scoped to the right repo, is fifteen minutes of advanced IAM per person, and it is the fiddliest part of the whole thing.

**The resolution: the club pre-builds it.** Ship a CloudFormation template that creates the OIDC provider, the role, and the bucket in one click. Attendees launch the stack, paste in their GitHub username and repo name, and get a role ARN out. They then see the trust policy on screen and hear what it does, without having to type it.

They learn the concept. They skip the yak-shave. That is the right trade for a 90-minute room.

### The workflow file

One file, in a template repo they fork, already committed. They should be able to read it end to end.

```yaml
name: Deploy to S3

on:
  push:
    branches: [main]

permissions:
  id-token: write      # lets the job request a GitHub OIDC token
  contents: read       # lets it check out your code

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - uses: aws-actions/configure-aws-credentials@v4
        with:
          role-to-assume: ${{ secrets.AWS_ROLE_ARN }}
          aws-region: us-east-1

      - run: aws s3 sync ./site s3://${{ secrets.BUCKET_NAME }} --delete
```

Notes on this before it goes in front of anyone:

- `id-token: write` is the line that trips everyone. It sounds like write access to something. **It is not.** it only lets the job request an identity token. Say this explicitly; it is the single most misread line in the file.
- Pin the action to its current major version and **check what that is the week of the event.** `@v4` is correct as of this writing; confirm against the [action's repo](https://github.com/aws-actions/configure-aws-credentials) before the deck is built.
- `--delete` makes the bucket mirror the repo. Worth one sentence, because it surprises people the first time.

---

## Session flow, 90 minutes

| Time | Segment | What happens |
|---|---|---|
| 0–10 | Setup check | GitHub account, AWS account. Pair anyone who is short one |
| 10–20 | Why automate at all | The manual deploy, done live and slowly, so the pain is felt before the fix is offered |
| 20–30 | Fork the template repo | Everyone gets the same starting point |
| 30–45 | Launch the CloudFormation stack | Creates the bucket, the OIDC provider, the role. Explain the trust policy while it runs |
| 45–55 | Add the two repo secrets | Role ARN and bucket name. Read the workflow file together, line by line |
| 55–70 | **Push and watch it deploy** | The moment. Everyone edits a heading, commits, watches the Actions tab, refreshes the URL |
| 70–80 | Break it on purpose | Push a bad YAML indent. Read the error. Fix it. This is the most useful ten minutes of the session |
| 80–90 | Where this goes next | Tests in the pipeline, environments, containers on ECS, CloudWatch. Teardown |

### The segment worth protecting

**Break it on purpose.** Every attendee will hit a failed workflow in their own projects within a month. If the only pipeline they have ever seen is one that worked, a red X is terrifying and opaque. If they have broken one deliberately, with a presenter narrating how to read the log, it is just a Tuesday.

Most workshops skip this because it feels like wasting time on failure. It is the part that actually transfers.

### Do the manual deploy first

Segment two matters more than it looks. Do the deploy by hand, on screen, slowly, open the console, select the files, upload, wait. Then ask the room how it would feel doing that eleven more times today.

Automation only lands as a relief if the audience has felt the thing being automated. Leading with the pipeline makes it abstract.

---

## What has to be built beforehand

This is the real cost of the proposal. None of it is hard; all of it takes time.

| Item | Who | Notes |
|---|---|---|
| Template GitHub repo, public, with the workflow committed | Content owner | Fork-and-go. A tiny static site, one HTML file and a heading they will edit |
| CloudFormation template: bucket + OIDC provider + scoped role | Content owner | The one genuinely fiddly piece. Scope the role's trust policy to the repo, and its permissions to that one bucket |
| One-click stack launch URL | Content owner | So nobody types a stack name wrong |
| Troubleshooting one-pager for helpers | Content owner | Same idea as the Event 2 handout |
| Full dry run on a fresh AWS account and a fresh GitHub account | Whoever presents | Non-negotiable. Your own accounts lie to you, they already have the provider registered and the CLI configured |

**Budget three weeks.** Starting after Event 1 lands on Sep 16, that reaches Oct 28 with room. It does not reach Oct 7.

---

## Prerequisites we cannot fix on the day

- **A GitHub account.** Add it to the pre-event email alongside the AWS one.
- **An AWS account.** the same unresolved blocker as Event 2. If the Learner Lab route works out, check that it permits creating IAM OIDC providers; some sandbox environments restrict exactly that. **Worth confirming early, because it would sink this design specifically.**
- **Enough git to commit and push.** Not much, but not zero. If Event 2's audience turns out to be more beginner than expected, consider a fifteen-minute git primer at the top and cut something else.

---

## What to do about Event 2 in the meantime

Do not change the plan. **Change the ending.**

Event 2 currently closes with a map of services and the cert path. Take five minutes of that and run a live CI/CD demo instead, presenter only, nobody follows along:

> "Watch this. I'm changing one line in this file. I'm pushing it. I'm not touching AWS at all." *(switch to the Actions tab, wait, refresh the site)* "That's what we're doing on October 28th."

Zero prep beyond a working pipeline the presenter already has. It costs five minutes, it advertises Event 3 to exactly the people most likely to come, and it ends Event 2 on something more exciting than a slide about certifications.

**That gets the CI/CD moment into October 7 without betting the workshop on it.**

---

## What needs a decision

1. **Bilal:** does CI/CD move from Q3 Event 6 to Event 3 on Oct 28, and what fills Event 6 instead? Hackathon prep and project showcases are both in the master plan already.
2. **Bilal:** if Learner Lab is the account route, can those accounts create IAM OIDC providers? Blocks this design specifically.
3. **Daksh:** who owns building the template repo and the CloudFormation stack, starting Sep 17?
4. **Everyone:** is Event 3 in person or online? Same reasoning as Event 2, a workshop loses the most in translation to a video call.

---

## Sources checked

- Configure AWS Credentials action, https://github.com/aws-actions/configure-aws-credentials
- Configuring OpenID Connect in Amazon Web Services (GitHub Docs), https://docs.github.com/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services
- Use IAM roles to connect GitHub Actions to actions in AWS (AWS Security Blog), https://aws.amazon.com/blogs/security/use-iam-roles-to-connect-github-actions-to-actions-in-aws/

Checked 2026-09-13. Re-check action versions the week of the event.
