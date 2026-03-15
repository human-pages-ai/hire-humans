# hire-humans

**Your AI agent can hire real humans for tasks it can't do alone.**

> 80+ directories your side project should be listed on. Your AI agent can submit to all of them.

---

## Why not Fiverr?

Fiverr requires *you* to manage freelancers. You browse profiles, write briefs, go back and forth in chat, review deliverables, and request revisions. **hire-humans** requires your *agent* to manage. You write zero messages. Your AI agent reads a playbook, finds the right human, sends a structured job offer, verifies the deliverables, and marks the job paid. You stay in your IDE the whole time.

---

## Quick Start

### Claude Code

```bash
claude mcp add humanpages -- npx -y humanpages
```

### Cursor

Add to your `.cursor/mcp.json`:

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

Add to your `~/.windsurf/mcp.json`:

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

## Playbooks

| Playbook | What | Est. price | Cadence |
|---|---|---|---|
| **[Directory Submissions](playbooks/directory-submissions.md) ★ START HERE** | Submit your project to 80+ directories | ~$5--15 | One-time |
| [QA Testing](playbooks/qa-testing.md) | Real-device bug testing on phones, tablets, browsers | ~$15--40/session | Per release |
| [Competitor Monitoring](playbooks/competitor-monitoring.md) | Track competitor pricing, features, and changes | ~$10--25/week | Weekly |
| [Localization](playbooks/localization.md) | Native speaker review of your translated UI | ~$15--30/language | Per release |
| [Community Management](playbooks/community-management.md) | Moderate your Discord, Reddit, or forum | ~$50--100/week | Daily |

Prices are estimates — actual cost depends on the human you hire and your market. Your first directory submission job is on us if it doesn't work out.

Each playbook is a standalone Markdown file your agent can read and follow step by step.

---

## How It Works

```
1. Agent reads playbook     — picks the right workflow for the task
2. search_humans            — finds humans with matching skills & equipment
3. get_human_profile        — reviews a candidate's profile and ratings
4. create_job_offer         — sends a structured offer (you approve first)
5. Human does the work      — delivers results via the platform
6. Agent verifies           — checks deliverables against the playbook criteria
7. mark_job_paid            — releases payment
8. leave_review             — rates the human for future searches
```

Your agent handles steps 1--3 and 5--8 autonomously. It pauses at step 4 to ask for your approval before spending money.

---

## Pricing & Payments

You pay humans directly using their preferred method (PayPal, Venmo, USDC, bank transfer, etc.). Human Pages tracks the job lifecycle -- you only call `mark_job_paid` after your agent verifies the deliverables. If the work isn't right, you don't pay. See [API docs](https://humanpages.ai/dev) for the full payment flow.

**Platform access:**

| Tier | Cost | Includes |
|---|---|---|
| PRO | $5 USDC / 60 days | 15 job offers/day, 50 profile views/day |
| Pay-per-use | No subscription | $0.05/profile view, $0.25/job offer, $0.50/listing |

PRO is **free during launch** -- no payment needed to get started.

**Something go wrong?** We're early and we take every case seriously. Reach out at [humanpages.ai](https://humanpages.ai) and we'll make it right.

---

## Links

- **Website**: [humanpages.ai](https://humanpages.ai)
- **npm package**: [`humanpages`](https://www.npmjs.com/package/humanpages)
- **API docs**: [humanpages.ai/dev](https://humanpages.ai/dev)

---

## License

[MIT](LICENSE)

Built by [Human Pages](https://humanpages.ai)

<!-- GitHub topics: ai-agents, mcp, hiring, freelance, automation, directory-submissions, qa-testing, developer-tools -->
