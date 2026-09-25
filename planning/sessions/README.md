# Sessions

Every event the club has run or is planning, newest first. This is the one place for session material: plans, slides, runbooks, recaps, and the code attendees use.

## Fall 2026

| Date | Session | Format | Status | Folder |
|---|---|---|---|---|
| 2026-10-07 | Event 2: AWS 101 workshop | TBD | Planning | [2026-10-07-aws-101](2026-fall/2026-10-07-aws-101/README.md) |
| 2026-09-16 | Event 1: Kickoff | Online | Done | [2026-09-16-kickoff](2026-fall/2026-09-16-kickoff/README.md) |

[aws-official/](aws-official/README.md) holds an alternative version of Event 2 built on AWS's official tutorial, kept apart until the team picks one.

A CI/CD session was proposed for Oct 28 or Nov 18. Its drafts were removed on 2026-09-24 to keep this folder focused; they are in git history (`events/cicd-track/` in commit `df72b74` of this repo, and `sessions/2026-fall/TBD-cicd-on-aws/` in the `info` repo).

## Adding a session

1. Name the folder `YYYY-MM-DD-short-name` inside the term folder (`2026-fall`, `2027-winter`). Use `TBD-short-name` until the date is set.
2. Copy the template: `cp -r _template 2026-fall/2026-10-07-aws-101`
3. Fill in its `README.md`, and add a row to the table above.
4. Draft slide text in `deck.md`. Commit only the final slides, exported as `YYYY-MM-DD-short-name.pptx` into the folder.
5. Fill in `recap.md` within a week of the event, and delete any demo AWS resources.

Status values: Idea, Planning, Awaiting approval, Confirmed, Done, Recapped, Canceled.

Code that attendees clone lives in its own public repo, checked out inside the session folder as `app/` or `site/` (git-ignored here). Answer keys go in a git-ignored `SOLUTION.md`.
