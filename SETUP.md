# Tooling Setup

What is installed for working on this project, why, and the one command that reproduces it on another machine.

Everything here is already installed on this machine as of 2026-09-13.

---

## The one command

```bash
claude mcp add --transport http --scope user aws-knowledge https://knowledge-mcp.global.api.aws && npx --yes @tech-leads-club/agent-skills@1.4.10 install --skill aws-advisor security-best-practices mermaid-studio docs-writer create-adr --agent claude-code --global
```

Restart Claude Code afterwards so the MCP tools register.

---

## What it installs

### AWS Knowledge MCP server

Hosted by AWS at `https://knowledge-mcp.global.api.aws`. No authentication, no API key, rate-limited. Nothing runs locally.

Five tools: `search_documentation`, `read_documentation`, `list_regions`, `get_regional_availability`, `retrieve_skill`.

**Why it matters for this project specifically:** the Event 2 notes needed the current AWS free-tier terms, and the answer had changed. AWS replaced the twelve-month free tier with a credits-based Free/Paid plan split. That kind of fact goes stale silently and gets repeated to a room of students. This server answers from live AWS documentation instead of from memory.

Added at user scope, so it is available in every project, not just this folder.

### Five skills, installed globally for Claude Code

| Skill | Why it is here |
|---|---|
| `aws-advisor` | AWS architecture and security guidance, documentation-backed. Pairs directly with the MCP server above, it is built to use exactly those tools |
| `security-best-practices` | The CI/CD workshop design hinges on OIDC instead of long-lived IAM keys. That is the part worth getting reviewed properly |
| `mermaid-studio` | Both workshops need diagrams. Event 2 builds a region → VPC → subnet → instance → security group picture live; Event 3 needs a pipeline diagram. Supports AWS architecture diagrams with real service icons |
| `docs-writer` | This whole folder is documentation. Keeps structure and tone consistent as more events get added |
| `create-adr` | Decisions here keep getting lost in Discord, Daksh and davedat. both said so on 2026-09-13. ADRs are the standing fix: one short record per decision, with the reasoning, so nobody re-litigates the online-vs-in-person call in November |

Skills land in `~/.claude/skills/`. Global install means they work in every project.

---

## Removing things

```bash
npx @tech-leads-club/agent-skills remove --skill <name> --agent claude-code --global
claude mcp remove aws-knowledge --scope user
```

---

## Known bug in the skills installer

**Do not use the interactive TUI. It crashes.**

Version 1.4.10, which is the latest, throws on this sequence: open the filter with `/`, scroll down, select skills, press `Esc`, press `Enter`.

```
TypeError: Cannot read properties of undefined (reading 'type')
```

The Enter handler reads `we[w]`, the row at the cursor index, with no guard:

```js
qi=()=>{ let y=we[w]; if(y.type==="header"){...}
```

The Esc handler clears the filter but never resets the cursor:

```js
Ki=()=>{ if(R){ K(!1), h(""), k("list"); return } ... }
```

Compare the filter's own onChange, which does `h(y),A(0),B(0)`, it resets both the cursor and the scroll. Esc resets neither. So when the filter closes, the list collapses back to a handful of category headers while the cursor is still parked at a high index, and the next Enter reads past the end of the array.

**Workarounds:** press Enter while the filter box is still open, or skip the TUI entirely. Any flag routes to the non-interactive path, which is what the one command above uses.

Worth reporting at https://github.com/tech-leads-club/agent-skills, the fix is adding `A(0),B(0)` to the Esc handler.

---

## Valid values, for reference

**Agents:** `claude-code`, `cursor`, `codex`, `windsurf`, `opencode`, `amp`

**Listing skills without the TUI.** the registry caches locally:

```bash
python3 -c "import json;d=json.load(open('$HOME/.cache/agent-skills/registry.json'))['registry']['skills'];[print(f\"{s['name']:<38}{s.get('category','')}\") for s in (d if isinstance(d,list) else d.values())]"
```

92 skills available at time of writing.
