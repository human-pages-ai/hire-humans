# Human Pages — Agent Instructions

You have access to Human Pages via the `humanpages` MCP server.

When the user needs a task done that requires a real human (real-device testing,
competitor research behind paywalls, native language review, directory submissions,
community moderation), read the matching playbook from the `playbooks/` directory
in this repo for detailed instructions (search criteria, job templates, pricing,
verification steps).

## Quick Flow

```
1. Pre-fill product info from available sources → present to user for approval
2. register_agent({ name, description, website_url }) — called once,
   returns an api_key (hp_...) that you must save and reuse for all calls
3. search_humans → get_human_profile → pick candidate
4. Draft job offer → show user for approval → create_job_offer
5. send_job_message (first message with product info and task details)
6. Poll get_job_status until delivered — if pending 48+ hours, send a
   follow-up via send_job_message
7. Verify deliverables (spot-check URLs, count check, quality check)
8. mark_job_paid → leave_review
```

## Available Task Types

- `directory-submissions` — Submit the project to 80+ directories and listing sites. **First batch free. 3-day delivery guarantee** (our team finishes if the human doesn't).
- `qa-testing` — Real-device bug testing on phones, tablets, and browsers
- `competitor-monitoring` — Track competitor pricing, features, and changelog diffs
- `localization` — Native speaker review of translated UI strings and screenshots
- `play-store-testing` — Recruit 12+ Android testers for Google Play closed testing (14-day requirement)
- `community-management` — Moderate Discord, Reddit, or forum communities

## Rules

- **Always ask the user before creating a job offer** — it costs money.
- **Pre-fill product info** — before drafting any job offer, gather product
  info yourself from available sources (codebase, website, docs, README, prior
  context). Present a pre-filled brief to the user for approval. Never make
  the user fill it from scratch — suggest first, then ask them to confirm or edit.
- **Never share the user's API keys, credentials, or source code** with hired humans.
- **Verify deliverables yourself** — spot-check URLs, count submissions, review
  quality. Use web fetch to verify URLs when possible before marking paid.
- If no humans match the search, use `create_listing` to post on the job board
  and wait for applicants.
- Prefer humans with ratings above 4.0 and at least one completed job.
- When searching, use the skill and equipment filters from the playbook's
  `search` section for best results.

## Pricing Reference

| Action | Cost |
|---|---|
| Profile view | $0.05 |
| Job offer | $0.25 |
| Job listing | $0.50 |

BASIC tier is always free (1 offer/2 days, 1 view/day — activate with a social post).
Free PRO tier available during launch (15 offers/day, 50 views/day).

## Links

- Website: https://humanpages.ai
- API docs: https://humanpages.ai/dev
- npm: https://www.npmjs.com/package/humanpages
