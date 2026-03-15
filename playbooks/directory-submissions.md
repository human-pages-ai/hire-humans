# Directory Submissions Playbook

Hire a human to submit your product to startup directories, SaaS listings, and backlink sites. This is the highest-leverage task for early-stage growth: broad directory presence drives SEO, referral traffic, and credibility.

---

## When to Use

- A new product or major version has launched
- Monthly maintenance submissions are due (new directories appear constantly)
- SEO audit reveals low domain authority or few backlinks
- A competitor appears in directories where you are absent

## Why a Human Is Needed

Most directories require manual form submissions with CAPTCHAs, email confirmations, unique descriptions per site, and sometimes account creation. Many reject automated submissions. A human can also adapt descriptions to each directory's tone and requirements, select the right categories, and handle follow-up verification emails.

## Prerequisites — Gather From User First

Before searching for a human, ask the user to provide:

- **Product name** and **URL**
- **Tagline** (one line, under 100 chars)
- **Short description** (1-2 sentences for sites with character limits)
- **Long description** (1-2 paragraphs for sites with room)
- **Category** (e.g., Productivity, Developer Tools, AI, SaaS)
- **Logo URL** (direct link to a square logo image)
- **Screenshot URLs** (1-3 screenshots of the product)
- **Founder/maker name** and **email** (many directories require this)
- **Social links** (Twitter/X handle at minimum)
- **Pricing info** (free, freemium, paid — with prices if applicable)

Do not guess or fill in placeholders. The human submitting to directories needs accurate info.

## Search Criteria

**Primary search:**
```json
{
  "skill": "data entry",
  "available_now": true,
  "limit": 10
}
```

**Fallback search:**
```json
{
  "skill": "marketing",
  "available_now": true,
  "limit": 10
}
```

**Second fallback:**
```json
{
  "skill": "SEO",
  "available_now": true,
  "limit": 10
}
```

## Candidate Evaluation

Priority criteria when reviewing `get_human_profile` results:

1. **Prior directory/data-entry experience** — look for mentions of form filling, submissions, or listings in their bio or skills
2. **Attention to detail** — profiles that mention QA, proofreading, or accuracy
3. **English fluency** — descriptions must read naturally on English-language directories
4. **Availability** — must be available within 48 hours
5. **Review history** — prefer candidates with positive reviews on previous jobs

## Job Offer Template

**Title:** Submit [PRODUCT_NAME] to [N] startup/SaaS directories

**Description:**
```
Submit [PRODUCT_NAME] ([PRODUCT_URL]) to [N] directories from the provided list.

For each submission:
1. Create an account if required
2. Fill in all fields accurately using the product info below
3. Select the most relevant category
4. Confirm any verification emails
5. Record the submission URL or screenshot as proof

Product info:
- Name: [PRODUCT_NAME]
- URL: [PRODUCT_URL]
- Tagline: [TAGLINE]
- Description (short): [SHORT_DESCRIPTION]
- Description (long): [LONG_DESCRIPTION]
- Category: [CATEGORY]
- Logo URL: [LOGO_URL]
- Screenshot URLs: [SCREENSHOT_URLS]
- Founder/maker name: [FOUNDER_NAME]
- Founder email: [FOUNDER_EMAIL]
- Twitter/X: [TWITTER_HANDLE]
- Pricing: [PRICING_INFO]

Deliver a spreadsheet or markdown table with columns:
| Directory | URL submitted | Status | Notes |

Mark each as: submitted, pending approval, requires paid plan, or failed (with reason).
```

**Suggested price:**
- **Default: one job for 15-20 directories at $5-15.** Workers in global markets handle this efficiently.
- For a full 80+ directory sweep, create 4-5 sequential jobs of 15-20 directories each. Start with the Launch Platforms category, then move down the list.
- Do not create a single job for all 80+ directories — it's too much to verify at once.

## Expected Deliverables

1. Markdown table or spreadsheet with every directory attempted, the submitted URL, and status
2. Screenshot proof for any directory that does not provide a public listing URL immediately
3. List of directories that require a paid plan (so you can decide whether to upgrade)
4. List of directories that were down or no longer accepting submissions
5. Any login credentials created (delivered securely via job message, not in the public deliverable)

### Example Deliverable

A completed batch should look like this:

| # | Directory | URL Submitted | Status | Notes |
|---|-----------|--------------|--------|-------|
| 1 | ProductHunt | https://producthunt.com/posts/focustimer | Submitted | Scheduled for launch 20 Mar |
| 2 | BetaList | https://betalist.com/startups/focustimer | Pending approval | Review takes 3-5 days |
| 3 | Uneed | https://uneed.best/tool/focustimer | Live | Approved instantly |
| 4 | SaaSHub | https://saashub.com/focustimer | Live | Listed under Productivity |
| 5 | AlternativeTo | https://alternativeto.net/software/focustimer | Live | Listed as alternative to Forest, Be Focused |
| 6 | BetaList | — | Requires paid plan | $39 for featured listing, skipped |
| 7 | MicroLaunch | — | Failed | Site at capacity, retry next month |
| 8 | Fazier | https://fazier.com/launches/focustimer | Pending approval | Submitted, awaiting review |

## Verification Criteria

Before calling `mark_job_paid`, the agent should verify (not the user):

1. **Spot-check at least 3 URLs** — use web fetch to visit the submitted URLs and confirm the product listing exists or is pending review. If web fetch is unavailable, ask the user to check.
2. **Count check** — the number of confirmed submissions should match or exceed the agreed batch size
3. **Quality check** — descriptions should be accurate, not copy-pasted boilerplate with errors
4. **No duplicates** — each directory should appear only once in the deliverable
5. **Failed submissions explained** — any failures should have a clear reason

## Communication Template

**First message after job offer is accepted:**

```
Hi [NAME], thanks for taking this on!

I've attached the product info and directory list below. Please start
with the Launch Platforms category and work down. For each submission,
note the URL and status in a table.

A few tips:
- Use the short description for sites with character limits
- Use the long description where there's room
- If a site asks for a category not in my list, pick the closest match
  and note what you chose
- If a site requires payment, skip it and mark it "requires paid plan"

Let me know if you have any questions before you start. I'm happy to
clarify anything.
```

## Estimated Timeline

- **Per batch of 5 directories:** 1-3 hours
- **Full 80+ directory sweep:** 2-4 days (recommend splitting across 2-3 jobs)
- **Turnaround expectation:** Set deadline to 48 hours per batch

## Recurring Schedule

**Cadence:** Monthly

**Monthly maintenance task:**
- Re-check 10 previously submitted directories for listing status (some remove inactive listings)
- Submit to any new directories discovered that month
- Update descriptions if the product tagline or pricing has changed
- Report any directories that have gone offline

---

## Directory List

The following directories are organized by category. Assign batches from this list when creating jobs. Not every directory will be relevant to every product — skip those that clearly do not fit and note them as "not applicable" in the deliverable.

### Launch Platforms

Sites designed for launching and announcing new products. These often have upvote mechanics and time-sensitive visibility windows.

| # | Directory | URL | Notes |
|---|-----------|-----|-------|
| 1 | Product Hunt | https://www.producthunt.com | Schedule launch day carefully; one shot |
| 2 | BetaList | https://betalist.com | Best for pre-launch/beta products |
| 3 | Uneed | https://www.uneed.best | Indie-friendly, fast approval |
| 4 | Fazier | https://fazier.com | Startup launch platform |
| 5 | MicroLaunch | https://microlaunch.net | For micro-SaaS and side projects |
| 6 | TinyLaunch | https://tinylaunch.com | Small product launches |
| 7 | Hacker News (Show HN) | https://news.ycombinator.com | Post as "Show HN: [product]"; best on weekday mornings ET |
| 8 | SideProjectors | https://www.sideprojectors.com | Side project marketplace/directory |
| 9 | LaunchIgniter | https://launchigniter.com | Launch announcement platform |
| 10 | PeerPush | https://peerpush.co | Peer-driven product launches |
| 11 | LaunchIt | https://launchit.today | Simple launch directory |
| 12 | LaunchYourApp | https://launchyourapp.com | App launch directory |
| 13 | indie.deals | https://indie.deals | Indie maker deals and launches |
| 14 | DesiFounder | https://desifounder.com | South Asian founder community |
| 15 | StartupLab | https://startuplab.io | Startup resources and launches |
| 16 | FirstoContact | https://firstocontact.com | First contact for new products |
| 17 | Launching Next | https://www.launchingnext.com | Upcoming startup launches |
| 18 | PitchWall | https://pitchwall.co | Startup pitch directory |
| 19 | Startup Buffer | https://startupbuffer.com | Startup promotion platform |
| 20 | StartupBase | https://startupbase.io | Startup database |
| 21 | Startup Tracker | https://startuptracker.io | Track and discover startups |
| 22 | Killer Startups | https://killerstartups.com | Startup reviews and listings |
| 23 | Startup Ranking | https://www.startupranking.com | Ranked startup directory |
| 24 | Launched! | https://launched.io | Post-launch showcase |
| 25 | 10words | https://10words.io | Describe your startup in 10 words |
| 26 | rankinpublic.xyz | https://rankinpublic.xyz | Public startup ranking |
| 27 | launchboard.dev | https://launchboard.dev | Developer-focused launch board |
| 28 | trylaunch.ai | https://trylaunch.ai | AI-focused launch platform |
| 29 | selected.site | https://selected.site | Curated site directory |

### SaaS / Product Directories

General-purpose directories for software products. Good for long-term SEO and discovery.

| # | Directory | URL | Notes |
|---|-----------|-----|-------|
| 30 | AlternativeTo | https://alternativeto.net | List as alternative to known competitors |
| 31 | SaaSHub | https://www.saashub.com | SaaS comparison and discovery |
| 32 | OpenAlternative | https://openalternative.co | Open-source alternative listings |
| 33 | Toolfolio | https://toolfolio.io | Tool and SaaS directory |
| 34 | LibHunt | https://www.libhunt.com | Library and tool discovery |
| 35 | SaaS Genius | https://www.saasgenius.com | SaaS reviews and comparisons |
| 36 | G2 | https://www.g2.com | Major review platform; may require verification |
| 37 | DevHunt | https://devhunt.org | Developer tool launches |
| 38 | Capterra | https://www.capterra.com | Enterprise software directory; may require paid listing |
| 39 | There is an AI for That | https://theresanaiforthat.com | AI tool directory (AI products only) |
| 40 | Tool Finder | https://toolfinder.co | Curated tool recommendations |
| 41 | StackShare | https://stackshare.io | Tech stack sharing; good for dev tools |
| 42 | YourStory | https://yourstory.com | Indian startup media and listings |
| 43 | Startup Stash | https://startupstash.com | Curated startup resources |
| 44 | Taaft | https://taaft.com | AI tool directory |

### Profile / Backlink Sites

Sites where you create a company or project profile. Valuable primarily for backlinks and brand presence.

| # | Directory | URL | Notes |
|---|-----------|-----|-------|
| 46 | Crunchbase | https://www.crunchbase.com | Create a free organization profile |
| 47 | About.me | https://about.me | Personal/company profile page |
| 48 | HackerNoon | https://hackernoon.com | Publish a story or create a company profile |
| 49 | Devpost | https://devpost.com | Good for hackathon-born projects |
| 50 | SourceForge | https://sourceforge.net | Open-source project hosting and discovery |
| 51 | Strikingly | https://www.strikingly.com | Create a simple landing page with backlink |
| 52 | Site123 | https://www.site123.com | Free site builder with directory listing |

### AI Agent Directories

Specialized directories for AI agents, autonomous tools, and x402/crypto-native services.

| # | Directory | URL | Notes |
|---|-----------|-----|-------|
| 53 | navtools.ai | https://navtools.ai | AI tool navigation directory |
| 54 | x402.eco | https://x402.eco | x402 protocol ecosystem directory |
| 55 | hermesx402.com | https://hermesx402.com | Hermes x402 agent directory |
| 56 | nullpath.com | https://nullpath.com | AI agent listings |
| 57 | aiagentstore.ai | https://aiagentstore.ai | AI agent marketplace |

### Additional High-Value Directories

Supplementary directories worth submitting to for broader coverage.

| # | Directory | URL | Notes |
|---|-----------|-----|-------|
| 58 | Indie Hackers | https://www.indiehackers.com | Community + product listing |
| 59 | BetaPage | https://betapage.co | Beta product directory |
| 60 | GetApp | https://www.getapp.com | Gartner-owned software directory |
| 61 | Software Suggest | https://www.softwaresuggest.com | Software recommendation engine |
| 62 | Slant | https://www.slant.co | "What is the best..." comparison site |
| 63 | Product Hunt Ship | https://www.producthunt.com/ship | Pre-launch landing page on PH |
| 64 | F6S | https://www.f6s.com | Startup deals, accelerators, and profiles |
| 65 | AngelList / Wellfound | https://wellfound.com | Startup profiles and hiring |
| 66 | Clutch | https://clutch.co | B2B service directory |
| 67 | TrustPilot | https://www.trustpilot.com | Create a business profile for reviews |
| 68 | AppSumo Marketplace | https://appsumo.com | Lifetime deal marketplace (if applicable) |
| 69 | Pitchbook | https://pitchbook.com | Financial data; create a free profile |
| 70 | TechCrunch Submit | https://techcrunch.com/submit | Submit for coverage consideration |
| 71 | Robin Good Tools | https://tools.robingood.com | Curated tool directory |
| 72 | NocodeList | https://nocodelist.co | No-code tool directory (if applicable) |
| 73 | MakerPad | https://www.makerpad.co | No-code community and tools |
| 74 | Remote Tools | https://www.remotetools.club | Remote work tool directory |
| 75 | Futurepedia | https://www.futurepedia.io | AI tool directory |
| 76 | AI Valley | https://aivalley.ai | AI tool discovery |
| 77 | TopAI.tools | https://topai.tools | Ranked AI tools |
| 78 | AI Tools Directory | https://aitoolsdirectory.com | General AI tools listing |
| 79 | SaaSWorthy | https://www.saasworthy.com | SaaS reviews and awards |
| 80 | Crozdesk | https://crozdesk.com | Software discovery platform |
| 81 | GoodFirms | https://www.goodfirms.co | Software reviews and listings |
| 82 | Gartner Peer Insights | https://www.gartner.com/reviews | Enterprise reviews (for established products) |
| 83 | All Top Startups | https://alltopstartups.com | Startup news and directory |
| 84 | EU Startups | https://www.eu-startups.com | European startup directory |
| 85 | BetaBound | https://www.betabound.com | Beta testing community and listings |

---

## Example Agent Workflow

```
1. search_humans({ skill: "data entry", available_now: true, limit: 10 })
2. For each candidate: get_human_profile({ username: candidate.username })
3. Select best candidate based on evaluation criteria
4. create_job_offer({
     human_username: selected.username,
     title: "Submit ProductName to 5 startup directories (Batch 1: Launch Platforms)",
     description: "...[filled template]...",
     price: 10,
     currency: "USD"
   })
5. send_job_message({ job_id: job.id, message: "...[communication template]..." })
6. Poll: get_job_status({ job_id: job.id }) until status is "delivered"
7. Verify deliverables against criteria
8. mark_job_paid({ job_id: job.id }) if verified
9. leave_review({ job_id: job.id, rating: 5, comment: "..." })
10. Schedule next batch or monthly maintenance
```
