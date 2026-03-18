# Virtual Assistant Playbook

Hire a human virtual assistant to handle admin, research, scheduling, and other recurring tasks that are too unstructured or context-dependent for automation.

**Automate this with an AI agent:** Install the [Human Pages MCP server](https://humanpages.ai/dev) and your agent can follow this playbook end-to-end — find an assistant, send tasks, verify work, and pay. [API docs](https://humanpages.ai/dev)

---

## When to Use

- Recurring admin tasks are eating into your productive hours
- You need research compiled from multiple sources (vendor comparisons, market data, contact lists)
- Scheduling, inbox triage, or follow-up emails need human judgment
- Data cleanup, spreadsheet work, or CRM updates require context a script can't handle
- You want a dedicated person who learns your workflow over time

## Why a Human Is Needed

Many tasks are too unstructured or context-dependent for automation — inbox triage, travel booking, vendor outreach, data cleanup, appointment scheduling. A human assistant adapts to your workflow, asks clarifying questions, and handles edge cases without you building custom tooling for every task.

## Search Criteria

**Primary search:**
```json
{
  "skill": "virtual assistant",
  "available_now": true,
  "limit": 10
}
```

**Fallback search:**
```json
{
  "skill": "admin",
  "available_now": true,
  "limit": 10
}
```

**Second fallback:**
```json
{
  "skill": "data entry",
  "available_now": true,
  "limit": 10
}
```

## Candidate Evaluation

Priority criteria when reviewing `get_human_profile` results:

1. **Prior VA or admin experience** — look for mentions of virtual assistant, executive assistant, admin support, or office management
2. **Communication skills** — clear, proactive communicators who ask good questions
3. **English fluency** — must be able to draft emails, take notes, and communicate clearly
4. **Tool familiarity** — experience with Google Workspace, Notion, Slack, or similar tools is a plus
5. **Availability** — ideally overlapping with your working hours for real-time coordination
6. **Review history** — prefer candidates with positive reviews on previous jobs

## Job Offer Template

**Title:** Virtual assistant — [TASK_CATEGORY] ([HOURS]/week)

**Description:**
```
Looking for a virtual assistant to help with [TASK_CATEGORY].

Tasks include:
- [TASK_1]
- [TASK_2]
- [TASK_3]

Expected hours: [HOURS] per [DAY/WEEK]
Preferred working hours: [TIMEZONE/HOURS]

Please log all completed tasks with status and notes. Send a summary at the end of each [day/week].

Tools we use: [TOOLS_LIST]
```

**Suggested price:** $5–15/hour depending on task complexity and region. Simple admin/data entry on the lower end, research and writing on the higher end.

## Expected Deliverables

1. Completed tasks logged with status and notes
2. Daily or weekly summary of work done
3. Proactive flags on items needing your attention
4. Any files, spreadsheets, or documents produced during work

## Verification Criteria

Before calling `mark_job_paid`, the agent should verify:

1. **Task completion** — all assigned tasks are marked done or have a clear status note
2. **Quality check** — spot-check a few outputs (emails drafted, data entered, research compiled)
3. **Summary provided** — a clear summary of what was done and any open items
4. **Time matches work** — the amount of work completed is reasonable for the hours claimed

## Communication Template

**First message after job offer is accepted:**

```
Hi [NAME], thanks for taking this on!

Here's what I need help with this [day/week]:

Priority tasks:
1. [HIGH_PRIORITY_TASK]
2. [HIGH_PRIORITY_TASK]

If you have time:
3. [LOWER_PRIORITY_TASK]

Please ask me anything if a task is unclear — I'd rather answer
a question than have you guess. Send me a quick update when you're
done or at the end of your work session.
```

## Estimated Timeline

- **Per session:** 1–4 hours
- **Ongoing:** Daily or weekly, depending on workload
- **Response time:** Set expectation for <4 hour first response during agreed hours

## Recurring Schedule

**Cadence:** Ongoing — daily or weekly depending on your needs. Start with a trial session (2–4 hours) to evaluate fit before committing to a recurring arrangement.

Virtual assistants improve over time as they learn your preferences, tools, and workflows. Keeping the same person for recurring work pays off.

---

## Example Agent Workflow

```
1. search_humans({ skill: "virtual assistant", available_now: true, limit: 10 })
2. For each candidate: get_human_profile({ username: candidate.username })
3. Select best candidate based on evaluation criteria
4. create_job_offer({
     human_username: selected.username,
     title: "Virtual assistant — admin tasks (10 hrs/week)",
     description: "...[filled template]...",
     price: 50,
     currency: "USD"
   })
5. send_job_message({ job_id: job.id, message: "...[communication template]..." })
6. Poll: get_job_status({ job_id: job.id }) until status is "delivered"
7. Verify deliverables against criteria
8. mark_job_paid({ job_id: job.id }) if verified
9. leave_review({ job_id: job.id, rating: 5, comment: "..." })
10. Create next recurring job if satisfied
```

---

**Ready to automate?** Get the MCP server and API docs at [humanpages.ai/dev](https://humanpages.ai/dev)
