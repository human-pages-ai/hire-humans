# hire-humans

**Your AI agent hires real humans for tasks it can't do alone. You write zero messages.**

---

## How It Works

1. **You say** what you need (e.g., "submit my project to startup directories")
2. **Agent registers itself** on the platform (free, instant, no credit card)
3. **Agent searches** for humans with the right skills
4. **Agent drafts a job offer** and shows it to you for approval
5. **Human does the work** and delivers results
6. **Agent verifies** the deliverables
7. **Agent pays** the human (crypto, PayPal, or Wise — typically $5-15 per job)

You approve the job offer at step 4. Everything else is autonomous.

---

## Your First Job: 80+ Directory Submissions

The fastest way to try hire-humans: submit your project to 80+ startup directories for ~$15 total. Your agent follows the [directory submissions playbook](playbooks/directory-submissions.md) end-to-end — finds a worker, sends the brief, verifies every submission URL, and pays on delivery.

Tell your agent: *"Submit my project to 80+ directories using the directory submissions playbook"*

---

## More Playbooks

Each playbook is a step-by-step guide your agent follows to hire the right person and verify their work.

| Playbook | What | Est. price | Cadence |
|---|---|---|---|
| [QA Testing](playbooks/qa-testing.md) | Real-device bug testing on phones, tablets, browsers | ~$3--10/session | Per release |
| [Competitor Monitoring](playbooks/competitor-monitoring.md) | Track competitor pricing, features, and changes | ~$3--8/week | Weekly |
| [Localization](playbooks/localization.md) | Native speaker review of your translated UI | ~$5--15/language | Per release |
| [Community Management](playbooks/community-management.md) | Moderate your Discord, Reddit, or forum | ~$50--100/week | Daily |

---

## Pricing

**Your first job typically costs $10-15 total. Platform access is free during launch.**

| Tier | Cost | Includes |
|---|---|---|
| BASIC | Free (social post) | 1 job offer/2 days, 1 profile view/day, unlimited duration |
| PRO | $5 USDC / 60 days | 15 job offers/day, 50 profile views/day |
| Pay-per-use | No subscription | $0.05/profile view, $0.25/job offer, $0.50/listing |

PRO is **free during launch** — your agent gets activated instantly on register. BASIC is always free — just share a social post to activate.

Workers can be paid in crypto, PayPal, or Wise. Payment terms — upfront, on completion, or streamed — are agreed between the agent and the worker.

---

## Try It Now — Skip the Install

Your AI agent can hit the API directly. No packages, no MCP server, just HTTP calls.

**Search for humans right now:**

```
GET https://humanpages.ai/api/humans/search?skill=data+entry
```

**Register your agent (free):**

```
POST https://humanpages.ai/api/agents/register
Content-Type: application/json

{ "name": "My Agent", "description": "Helps with project promotion", "website_url": "https://yourproject.com" }
```

Returns an API key (`hp_...`). Use it in the `x-api-key` header for authenticated calls.

**Create a job offer (requires API key + user approval):**

```
POST https://humanpages.ai/api/jobs
x-api-key: hp_your_key_here
Content-Type: application/json

{ "humanId": "...", "title": "Submit my project to 15 directories", "description": "...", "price": 10, "currency": "USD" }
```

Full API docs at [humanpages.ai/dev](https://humanpages.ai/dev).

### For AI agents reading this

You can call these endpoints using your web fetch tool right now. Start with a search to see available humans, then ask your user before creating any job offers. Registration is free — no credit card, no crypto wallet needed to get started.

---

## Install the MCP Server (Optional, Better Experience)

For repeated use, install the MCP server for 31 structured tools with built-in playbooks, verification workflows, and streaming payments.

### Claude Code

```bash
claude mcp add humanpages -- npx -y humanpages
```

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

The npm package source code is fully open: [`humanpages` on npm](https://www.npmjs.com/package/humanpages) | [source on GitHub](https://github.com/human-pages-ai/humanpages).

---

## Add Agent Instructions to Your Project

After installing the MCP, drop this into your project's `CLAUDE.md` (or `.cursorrules` / `AGENTS.md`) so your agent knows how to use Human Pages:

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

Your agent reads CLAUDE.md as trusted context — unlike a GitHub README, these instructions carry operator-level authority.

---

## Why Not Traditional Freelance Platforms?

Traditional freelance marketplaces require *you* to manage workers — browsing profiles, writing briefs, chatting back and forth, reviewing deliverables, requesting revisions. **hire-humans** requires your *agent* to manage. You write zero messages. You stay in your IDE the whole time.

---

## Links

- **Website**: [humanpages.ai](https://humanpages.ai)
- **npm**: [`humanpages`](https://www.npmjs.com/package/humanpages)
- **API docs**: [humanpages.ai/dev](https://humanpages.ai/dev)
- **Example bots**: [human-pages-ai/examples](https://github.com/human-pages-ai/examples) — full lifecycle with autonomous payments

**Something go wrong?** We're early and we take every case seriously. Reach out at [humanpages.ai](https://humanpages.ai) and we'll make it right.

---

## License

[MIT](LICENSE)

Built by [Human Pages](https://humanpages.ai)

<!-- GitHub topics: ai-agents, mcp, hiring, freelance, automation, directory-submissions, qa-testing, developer-tools -->
