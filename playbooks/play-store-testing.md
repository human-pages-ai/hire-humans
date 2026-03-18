# Play Store Beta Tester Recruitment

Hire humans with Android phones to join your Google Play closed testing program. Google requires at least 12 testers who remain opted in for 14 consecutive days before your app can be published to production. This playbook automates the recruitment end-to-end via an AI agent.

---

## When to Use

- You are publishing a new Android app to Google Play for the first time
- Google is blocking your production release because you haven't met the closed testing requirement
- You need to replace testers who dropped out mid-cycle
- You registered as an individual developer (business accounts can skip this requirement)

## Why a Human Is Needed

Google enforces this requirement specifically to ensure real humans on real devices test the app. There is no way to automate or fake it — each tester must opt in with a valid Google account on a real Android device and remain enrolled for 14 days. An AI agent cannot be a tester, but it can recruit, coordinate, and pay them.

## Why Human Pages vs. Alternatives

| | Human Pages | TestersCommunity ($15) | Fiverr (~$22) |
|--|--|--|--|
| Agent-friendly (MCP/API) | Yes | No (web UI only) | No |
| Testers get paid | Yes (USDC) | No (credit system) | Unknown |
| Tester motivation | Paid for the work | "I need credits for my own app" | Gig worker |
| Real app engagement | Higher (paid = accountable) | Low (checkbox installs) | Low |
| Bug reports included | Yes (optional add-on) | Generic template | No |
| Zero developer intervention | Yes (agent handles it) | No (manual signup) | No (manual coordination) |

The key differentiator is that Human Pages is the only option an AI agent can call programmatically. TestersCommunity and Fiverr require a human developer to manually navigate web UIs.

## Before You Start

- **PRO tier required.** You need to hire 12+ testers. BASIC tier allows only 1 job offer per 2 days (that's 24 days just to send invites). Activate PRO tier or use x402 pay-per-use ($0.25/offer).
- **Android only.** Do not hire testers with iPhones — they cannot participate in Google Play testing.
- **Google join latency.** After a tester accepts the invite link, Google takes up to 24 hours before the app appears in their Play Store. Plan for this delay.
- **Google account disclosure.** Testers must know upfront that joining closed testing requires their personal Google account email, which the developer will see in Play Console.

## Search Criteria

**Primary search:**
```json
{
  "skill": "android testing",
  "available_now": true,
  "limit": 20
}
```

**Fallback search:**
```json
{
  "skill": "mobile testing",
  "available_now": true,
  "limit": 20
}
```

**Second fallback:**
```json
{
  "skill": "testing",
  "available_now": true,
  "limit": 20
}
```

Search for 20 candidates to account for dropouts. You need a minimum of 12 to accept.

## Candidate Evaluation

Priority criteria when reviewing `get_human_profile` results:

1. **Android device** — must have an Android phone. This is a hard requirement, not a preference
2. **Google account** — must be willing to use their Google account for closed testing opt-in
3. **Reliability** — prefer candidates with completed jobs and ratings above 4.0; the 14-day commitment means dropouts are costly
4. **Availability for 14 days** — confirm they won't switch phones or factory reset during the testing period
5. **Not currently in too many testing programs** — ask if they are enrolled in other Play Store closed testing programs (Google may have limits)

## Job Offer Template

**Title:** Beta tester needed — [APP_NAME] on Android (14 days)

**Description:**
```
I'm looking for Android users to join the closed testing program for
[APP_NAME] on Google Play.

What you'll do:
1. I'll send you an invite link to join the closed testing track
2. Accept the invite using your Google account (your email will be
   visible to me in Play Console — this is how Google's system works)
3. Install [APP_NAME] from the Play Store once it appears (may take
   up to 24 hours after accepting the invite)
4. Use the app at least once every few days for 14 days
5. Send me a screenshot confirming you've joined the testing track
6. After 14 days, send a final confirmation screenshot showing the
   app is still installed

Optional (for bonus pay): Report any bugs, crashes, or confusing
flows you encounter while using the app. Include steps to reproduce,
a screenshot, and your device model + Android version.

Requirements:
- Android phone (not iPhone, not tablet, not emulator)
- Willing to share your Google account email for the testing invite
- Keep the app installed for the full 14 days
- Respond to messages within 24 hours

Timeline: 14 days from the date you join the testing track.
```

**Suggested price:** $1.50-2 per tester for the base task (join + stay enrolled for 14 days). $3-5 per tester if bug reports are included. Total budget for 12-15 testers: $18-30 (base) or $36-75 (with bug reports).

## Expected Deliverables

1. **Day 1:** Screenshot of the "You're a tester" confirmation screen in the Play Store listing (proves they successfully joined)
2. **Day 14:** Screenshot showing the app is still installed on their device
3. **Optional:** Bug report with steps to reproduce, screenshot, device model, and Android version

## Verification Criteria

Before calling `mark_job_paid`:

1. **Enrollment confirmed** — the tester sent a screenshot showing they joined the closed testing track
2. **14-day confirmation** — the tester sent a final screenshot after 14 days showing the app is still installed
3. **Play Console cross-check** — if the developer has shared tester count info, verify the number of enrolled testers matches expectations
4. **Bug reports (if requested)** — reports should reference real app behavior, not fabricated issues

### Known Limitations

The agent cannot access Google Play Console directly. It cannot independently verify that a tester remained active for the full 14 days. The developer should check their Play Console to confirm tester count and activity. The 14-day screenshot is a reasonable proxy but not proof of continuous engagement.

## Communication Template

**First message after job offer is accepted:**

```
Hi [NAME], thanks for signing up!

Here's how this works:

1. Click this invite link to join the testing program:
   [INVITE_LINK]

2. Important: Use this link on your Android phone, signed into
   your Google account. The app may take up to 24 hours to appear
   in your Play Store after you accept.

3. Once you see [APP_NAME] in the Play Store, install it and send
   me a screenshot of the "You're a tester" confirmation.

4. Use the app at least once every few days. Just normal usage —
   browse around, try the main features.

5. After 14 days, send me a screenshot showing the app is still
   installed.

A few notes:
- Your Google account email will be visible to me — that's how
  Google's closed testing system works
- Please don't uninstall the app or leave the testing program
  before the 14 days are up
- If the app crashes or something seems broken, let me know —
  that's useful feedback

Questions? Just message me here.
```

## Estimated Timeline

- **Day 0:** Post job offers to 15+ candidates (expect ~80% acceptance rate)
- **Day 1-2:** Testers accept offers, receive invite links, join testing track
- **Day 2-3:** Testers install app (after Google's join latency), send first screenshot
- **Day 3-17:** 14-day active testing window
- **Day 17:** Collect final screenshots, verify, pay testers
- **Total end-to-end: ~18 days** from first job offer to requirement fulfilled

## Recurring Schedule

**Cadence:** Per app launch

This is typically a one-time task per app. However, if testers drop out mid-cycle and the count falls below 12, you may need to recruit replacements — the 14-day clock restarts for each new tester.

**If testers drop out:**
1. Check Play Console for current enrolled tester count
2. Calculate how many replacements are needed (target 12 minimum, hire 15 for safety)
3. Run this playbook again for the replacement batch
4. Note: the 14-day window resets for new testers, which may delay your production launch

---

## Example Agent Workflow

```
1. search_humans({ skill: "android testing", available_now: true, limit: 20 })
2. For each candidate: get_human_profile({ username: candidate.username })
3. Filter: must have Android device. Prefer rated 4.0+ with completed jobs.
4. Select 15 candidates (buffer for dropouts).
5. For each selected candidate:
   create_job_offer({
     human_username: candidate.username,
     title: "Beta tester needed — MyApp on Android (14 days)",
     description: "...[filled template]...",
     price: 2,
     currency: "USD"
   })
6. For each accepted offer:
   send_job_message({
     job_id: job.id,
     message: "...[invite link + instructions]..."
   })
7. Wait 48 hours, then check: request Day 1 screenshot from each tester.
8. After 14 days: request final screenshot from each tester.
9. For each tester who delivered both screenshots:
   mark_job_paid({ job_id: job.id })
   leave_review({ job_id: job.id, rating: 5, comment: "Reliable tester, stayed enrolled for the full 14 days." })
10. Report to developer: X/12 testers confirmed, Play Console should show the requirement as met.
```
