# AGENTS.md: AWS Student Builder Group @ Seneca

Planning folder for a student club: the AWS Student Builder Group at Seneca Polytechnic, Newnham Campus, Toronto. Eight events a year on cloud, AWS, DevOps, system design, and careers. The work is mostly documents, plus the workshop apps under `planning/sessions/`.

**Read [README.md](README.md) first.** Status, open tasks, team, decisions, and links live there and nowhere else. This file only says how to work here. The user of this session is **Datta (davedat.), the club's tech lead**.

## Tone for anything member-facing

Direct, human, no hype: *"You are not selling a product. You are inviting people into something real."* No marketing gloss, no stacked exclamation marks. The club's principles: contribution over attendance, no gatekeeping, ideas from anyone, engineers teaching engineers, build in public. Vision and the eight-event arc: [planning/master-plan.md](planning/master-plan.md).

## Where things live

- Status and tasks: `README.md`. History, with dates: `planning/timeline.md`.
- Sessions: `planning/sessions/<term>/<YYYY-MM-DD-name>/`, copied from `_template/`. A session's code is its own public repo checked out inside as `app/` (git-ignored here); its answer key is a git-ignored `SOLUTION.md`.
- Study notes: `planning/sessions/study-guide/`, with the site repo checked out as `site/` (git-ignored). Lesson 1 is AWS's official PHP tutorial; Lesson 2 is Event 2's workshop.
- `info/` and `org-profile/` are separate public repos (club page and guides; org profile). Commit and push there, never copy private material into them.
- `planning/private.md` holds passwords and meeting links. Git-ignored; this repo is public. Never copy from it.
- `sources/discord-log.md` is the cleaned Discord log (source material only, never current state). `sources/discord-log.raw-backup.md` is the untouched original.
- `planning/master-plan.md` and `planning/sessions/2026-fall/2026-09-16-kickoff/run-of-show.md` carry notes-app frontmatter (`favorited`, `title`, `created`, `modified`). Keep it intact.

## Rules

1. Never delete `sources/discord-log.raw-backup.md`.
2. Keep the top level to `README.md`, `AGENTS.md`, `CLAUDE.md`.
3. Do not infer a task is done. Without a dated message saying so, the status is "no update".
4. Trace claims to dates. When something is decided or done, add it to `planning/timeline.md` and update the README; those two must not drift.
5. Nothing outward-facing without a green light: no posts to LinkedIn, Instagram, Discord, Meetup, or the SSF platform. Draft; a human sends.
6. Dates are in 2026 and the team writes them loosely. Write ISO dates.
7. Verify AWS facts before they reach students (pricing, free plan, signup, console names). AWS replaced the twelve-month free tier with a credits-based Free/Paid plan in July 2025, and the old version is still widely repeated. Use the `aws-knowledge` MCP server; fall back to aws.amazon.com/free.
8. Keep `SOLUTION.md` files and `planning/private.md` out of every commit. Check `git diff --cached --name-only` before committing here.

## Tooling

Reproduce the setup on a new machine, then restart Claude Code:

```bash
claude mcp add --transport http --scope user aws-knowledge https://knowledge-mcp.global.api.aws && npx --yes @tech-leads-club/agent-skills@1.4.10 install --skill aws-advisor security-best-practices mermaid-studio docs-writer create-adr --agent claude-code --global
```

- `aws-knowledge`: AWS's hosted documentation MCP server (no key). Tools: `search_documentation`, `read_documentation`, `list_regions`, `get_regional_availability`, `retrieve_skill`.
- Skills: `aws-advisor`, `security-best-practices`, `mermaid-studio`, `docs-writer`, `create-adr`.
- Don't use the skills installer's interactive menu (v1.4.10 crashes after Esc then Enter in the filter). The command above avoids it.
