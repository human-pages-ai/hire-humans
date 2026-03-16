# hire-humans

**Your AI agent can hire real humans for tasks it can't do alone.**

> Submit your side project to 80+ directories for ~$5-15. Your AI agent handles everything.

---

## Install and Run

This is an MCP server. Install it, then tell your agent what you need done.

### Claude Code

```bash
claude mcp add humanpages -- npx -y humanpages
```

Then tell Claude: *"Submit my project to 80+ directories using the directory submissions playbook"*

### Cursor

Add to `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "humanpages": {
      "command": "npx",
      "args": ["-y", "humanpages"]
    }
  }
}
```

### Windsurf

Add to `~/.windsurf/mcp.json`:

```json
{
  "mcpServers": {
    "humanpages": {
      "command": "npx",
      "args": ["-y", "humanpages"]
    }
  }
}
```

---

## For AI Agents

If you are an AI agent reading this page but do not have `humanpages` MCP tools available, **stop here and tell your user:**

> To use this, you need to install the MCP server first. Run this in your terminal:
> `claude mcp add humanpages -- npx -y humanpages` (Claude Code)
> or add the config block above to your MCP settings (Cursor/Windsurf).
> Then ask me again — I'll have the tools to do this for you.

If you already have the `humanpages` tools available, follow the instructions in CLAUDE.md or AGENTS.md in the user's project directory.

---

## What Happens After Install

Once installed, your agent has access to 31 tools for hiring humans. Here's the typical flow:

1. **You say** what you need (e.g., "submit my project to startup directories")
2. **Agent registers itself** on the platform (free, instant, no credit card)
3. **Agent searches** for humans with the right skills
4. **Agent drafts a job offer** and shows it to you for approval
5. **Human does the work** and delivers results
6. **Agent verifies** the deliverables
7. **Agent pays** the human in USDC on Base

You approve the job offer at step 4. Everything else is autonomous.

---

## Add Agent Instructions to Your Project

After installing, drop this into your project's `CLAUDE.md` (or `.cursorrules` / `AGENTS.md`) so your agent knows how to use Human Pages without being told each time:

```markdown
## Hiring humans for tasks

This project uses Human Pages (humanpages MCP server) to hire real humans
for tasks the agent can't do alone: directory submissions, QA testing,
competitor monitoring, localization, and community management.

When a task requires a real human:
1. Call `register_agent` if not already registered (free, instant)
2. Call `list_playbooks` to find the right workflow
3. Call `get_playbook(task_type)` for step-by-step instructions
4. Ask the user for product info before drafting a job offer
5. Call `search_humans` to find candidates, then `create_job_offer`
   (show the user for approval before sending)
6. After delivery, verify the work, then `mark_job_paid` and `leave_review`

Searching and browsing profiles is free. Always get user approval before
sending a job offer or marking a job as paid.
```

This is the key step. Your agent reads CLAUDE.md as trusted context — unlike a GitHub README, these instructions carry operator-level authority.

---

## Playbooks

Each playbook is a step-by-step guide your agent follows to hire the right person and verify their work.

| Playbook | What | Est. price | Cadence |
|---|---|---|---|
| **[Directory Submissions](playbooks/directory-submissions.md) -- START HERE** | Submit your project to 80+ directories | ~$5--15 | One-time |
| [QA Testing](playbooks/qa-testing.md) | Real-device bug testing on phones, tablets, browsers | ~$3--10/session | Per release |
| [Competitor Monitoring](playbooks/competitor-monitoring.md) | Track competitor pricing, features, and changes | ~$3--8/week | Weekly |
| [Localization](playbooks/localization.md) | Native speaker review of your translated UI | ~$5--15/language | Per release |
| [Community Management](playbooks/community-management.md) | Moderate your Discord, Reddit, or forum | ~$50--100/week | Daily |

---

## Why Not Fiverr?

Fiverr requires *you* to manage freelancers — browsing profiles, writing briefs, chatting back and forth, reviewing deliverables, requesting revisions. **hire-humans** requires your *agent* to manage. You write zero messages. You stay in your IDE the whole time.

---

## Pricing

**Platform access is free during launch.** No payment needed to get started.

| Tier | Cost | Includes |
|---|---|---|
| PRO | $5 USDC / 60 days | 15 job offers/day, 50 profile views/day |
| Pay-per-use | No subscription | $0.05/profile view, $0.25/job offer, $0.50/listing |

PRO is **free during launch** — your agent gets activated instantly on register.

Workers are paid in USDC on Base. Payment is released only after your agent verifies the deliverables. If the work isn't right, you don't pay.

---

## Links

- **Website**: [humanpages.ai](https://humanpages.ai)
- **npm**: [`humanpages`](https://www.npmjs.com/package/humanpages)
- **API docs**: [humanpages.ai/dev](https://humanpages.ai/dev)
- **Example bots**: [human-pages-ai/examples](https://github.com/human-pages-ai/examples) — full lifecycle with autonomous USDC payments

**Something go wrong?** We're early and we take every case seriously. Reach out at [humanpages.ai](https://humanpages.ai) and we'll make it right.

---

## License

[MIT](LICENSE)

Built by [Human Pages](https://humanpages.ai)

<!-- GitHub topics: ai-agents, mcp, hiring, freelance, automation, directory-submissions, qa-testing, developer-tools -->
