---
type: prompt
tags: ["prompt", "ai"]
---

# Prompt

**Overview**

Contained in this file are the prompt and three clearly headed sections:

1. **GA4_Metrics** – month-by-month figures for the past six months (sessions, users, engaged sessions, conversions, revenue).
2. **Sales Export** – raw exported CRM rows (lead status, projected revenue, created date, close date, salesperson, source).
3. Marketing Strategies – Early observations, suspected gaps, and strategic talking points.

**Prompt:**

**Objective**

Create an **interactive, scrollable website-style KPI report** for marketing leadership that:

- Visualizes the hard numbers first, then layers on narrative.
- Uses callout boxes or side-panel annotations for qualitative insight and data-quality warnings.

**Required visual elements (in priority order)**

1. **GA4 Trend Lines** – one multi-line chart showing Sessions, Users, and Engaged Sessions by month.
2. **Conversion & Revenue Bars** – side-by-side bars for Conversions and Revenue by month.
3. **Lead Funnel** – funnel or stacked bar (New Lead → Qualified → Proposal → Closed-Won) calculated from Sales_Pipeline.
4. **Top Lead Sources** – horizontal bar of the five largest sources by total estimated revenue.
5. **Closing Rate Gauge** – single KPI card or dial (% Closed-Won vs. total leads).
6. Any other visual elements and styling you think could add to this

**Narrative & Layout**

- Begin with a short executive summary block (100-150 words) pulling key wins and red flags.
- Place each chart in its own full-width section with a one-sentence caption that ties back to strategy or launch plan.
- Insert “Insight” callout boxes beside the relevant chart using text from the *Insights* section.
- Any missing or unreliable data should trigger a small gray “Data Gap” badge next to the metric label.

**Styling constraints**

- Clean sans-serif fonts, minimal color palette (#485e3d for primary, gray for neutral, #f5f2e8 instead of white).
- All interactive elements should use on-hover tooltips – no complex filters needed.
- Mobile-responsive.

**Handling messy data**

- Ignore rows with missing dates or revenue values in Sales_Pipeline when computing rates.
- If funnel stages are spelled inconsistently, map close variants to the four standard stages above.

**Output**

Deliver the finished report as a manus website

**End of prompt**

# Sales Export

Scroggs Opportunities — Data Quality & Trend Report

*Source file: **Leads.xlsx** (237 rows, exported 26 Jun 2025). All percentages are of the total 237 rows.*

---

## 1. Record-count snapshot

| Metric | Count |
| --- | --- |
| Total rows | **237** |
| Unique emails | **212** |
| Duplicate emails | **25** (see section 7) |
| Rows with “Sold” status | **62  (26.2 %)** |
| Rows with revenue figures (Min > 0) | **163  (68.8 %)** |

---

## 2. Funnel inventory

```
Lead Status,Count,Percent
No Opportunity,71,30.0
Sold,62,26.2
Lost,29,12.2
In Progress,28,11.8
Pending,25,10.5
On Hold,20,8.4
Open,2,0.8

```

**Key signals**

- Very few fresh “Open” leads (< 1 %) suggest the top of funnel is thin.
- “No Opportunity” plus “On Hold” rows total **38.4 %**; these should be reviewed or re-qualified.

---

## 3. Age and confidence

| Status | Avg Age (days) | Median Age | Avg Confidence |
| --- | --- | --- | --- |
| Lost | **264** | 274 | 0.335 |
| No Opportunity | 215 | 215 | 0.299 |
| On Hold | 209 | 183 | 0.447 |
| Sold | 208 | 206 | **0.785** |
| Pending | 108 | 106 | 0.524 |
| In Progress | 84 | 77 | 0.393 |
| Open | 28 | 28 | 0.000 |

**Take-away** – Confidence above **0.70** is strongly associated with wins. “Lost” deals sit the longest before closure.

---

## 4. Revenue picture (USD)

| Scope | Sum Min | Sum Max | Median Min | Rows (> 0) |
| --- | --- | --- | --- | --- |
| All rows | 24 725 678 | 30 246 946 | 50 000 | 163 |
| Sold only (62 rows) | **7 488 176** | **9 004 926** | 60 000 | 54 |
| In-Progress only | 6 386 620 | 7 865 500 | 145 000 | 28 |

*74 rows list “0” revenue. Fixing those will sharpen forecasts.*

---

## 5. Project-type mix (top 10)

```
Project Type,Count,Percent
INSURANCE REMODEL/REPAIR,45,19.0
RESTORATION,27,11.4
REMODEL,26,11.0
New Construction,18,7.6
ADDITION,8,3.4
ADDITION/REMODEL,6,2.5
REMODEL SINGLE BATHROOM,6,2.5
REMODEL - BASEMENT,5,2.1
NEW HOME CONSTRUCTION 500K,4,1.7
OTHER,3,1.3

```

Insurance and restoration work drive nearly **30 %** of all inquiries, while new-builds are < 8 %.

---

## 6. Lead source coverage (top 10)

```
Source,Count,Percent
Referral,18,7.6
Employee Referral,8,3.4
Google,7,3.0
PRIOR CLIENT,6,2.5
TRADESMAN,6,2.5
PAST LEAD,5,2.1
Truck Advertisement,5,2.1
CURRENT CLIENT,5,2.1
Other,3,1.3
Site Signs/Job Location,3,1.3

```

**160 rows (67.5 %) have no source**. Channel ROI cannot be measured until this is fixed.

---

## 7. Data-quality gaps (top 15 columns)

```
Column,Missing,Percent
Most Recent Click,232,97.9
# of Links Clicked,231,97.5
Tags,231,97.5
Has Opportunity Been Contacted?,230,97.0
Next Scheduled Activity (All),215,90.7
Projected Sales Date,187,78.9
Sold Date,175,73.8
Related Job,174,73.4
Source,160,67.5
Proposal Last Viewed,148,62.4
Proposal Status...,119,50.2
Notes,119,50.2
Cell Phone,87,36.7
Project Type,80,33.8
Phone,77,32.5

```

### Priority fixes

1. **Source** – make required at creation.
2. **Contacted?** – binary pick-list to monitor speed to first touch.
3. **Next Scheduled Activity** – force an activity before a stage can be saved.
4. **Revenue Min / Max** – default “Min = Max” only when fixed bid; disallow zero.
5. **Phone** – validation rule plus bulk append from email signatures where possible.

---

## 8. Duplicate email highlights

```
Email,Occurrences
karlaledoux@tampabay.rr.com,4
owensby.kelly@gmail.com,3
dianaops@hotmail.com,3
kanschutz@live.com,3
archie324@hotmail.com,3
... (20 more)

```

Run a deduplication merge so activity history stays in one record per contact.

---

## 9. Monthly lead intake (last 12 months)

```
Month,Lead Count
2024-07,17
2024-08,13
2024-09,6
2024-10,42
2024-11,34
2024-12,30
2025-01,20
2025-02,21
2025-03,18
2025-04,17
2025-05,9
2025-06,10

```

Spike in Oct 2024 appears to reflect storm-related insurance work; volumes have steadied at ~15 per month since.

---

## 10. What is working well

- **Created Date, Lead Status, Confidence** – 100 % filled, giving reliable timelines and probability scoring.
- **Age calculation** – 234 of 237 rows parse cleanly.
- **Revenue for active and sold deals** – 69 % coverage allows directional forecasting.

---

## 11. Unknowns that limit insight

- True marketing attribution because **two-thirds of “Source” is blank**.
- Funnel health beyond 6 months because **aging rules are not enforced**.
- Email engagement because **97 % of # Links Clicked is empty**.
- Proposal progression – half the rows lack any proposal status or view timestamp.

---

# Google Analytics:

## Scroggs Construction Services: 6-Month Traffic Analysis Report

**Reporting Period: January 26, 2025 - June 26, 2025**

## Executive Summary

This report provides a comprehensive analysis of website traffic and user engagement for Scrags Construction Services over the past six months. The analysis reveals consistent traffic patterns with notable seasonal variations, strong performance of key service pages, and opportunities for improving conversion rates and mobile user engagement.

## Traffic Overview

### Monthly Traffic Trends

| Month | Total Users | New Users | Sessions | Page Views | Avg. Session Duration |
| --- | --- | --- | --- | --- | --- |
| January | 109 | 94 | 142 | 273 | 2:40 min |
| February | 367 | 325 | 523 | 1,233 | 2:38 min |
| March | 395 | 370 | 626 | 1,163 | 3:00 min |
| April | 853 | 819 | 1,070 | 1,831 | 2:12 min |
| May | 806 | 763 | 981 | 1,571 | 2:04 min |
| June* | 283 | 255 | 383 | 679 | 2:46 min |
- Note: June data is partial (through June 26, 2025)

### Key Insights:

- **Traffic Spike**: April and May 2025 showed significantly higher traffic (more than double the users and sessions compared to Q1), likely corresponding to the spring home improvement season.
- **Strong Engagement**: Average session duration remains consistent at around 2-3 minutes across all months, indicating good content engagement.
- **New Visitor Acquisition**: Approximately 90% of all users during this period were new visitors, showing effective audience expansion.

## Device & Geographic Analysis

### Device Category Distribution

| Device | Users | Sessions | Page Views | Avg. Session Duration | Bounce Rate |
| --- | --- | --- | --- | --- | --- |
| Desktop | 1,330 | 1,873 | 3,756 | 3:10 min | 48.1% |
| Mobile | 1,391 | 1,755 | 2,863 | 1:25 min | 51.8% |
| Tablet | 92 | 97 | 131 | 0:39 min | 61.7% |

### Geographic Distribution

The vast majority of traffic is from the United States, with minimal international visitors.

### Key Insights:

- **Mobile/Desktop Split**: Nearly equal distribution between mobile and desktop users, but desktop users show significantly higher engagement (3:10 min vs 1:25 min session duration).
- **Mobile Experience Gap**: The shorter session duration and higher bounce rate for mobile users suggests potential user experience issues on mobile devices.
- **Tablet Opportunity**: The lowest engagement metrics are on tablet devices, which may indicate a need for optimization on these devices.

## Content Performance

### Top Performing Pages

| Page Path | Sessions | Page Views |
| --- | --- | --- |
| Homepage (/) | 2,121 | 2,545 |
| /services/custom-homes/ | 858 | 973 |
| /about/team/ | 617 | 678 |
| /contact/ | 402 | 427 |
| /services/home-remodels/ | 305 | 347 |
| /portfolio/ | 301 | 392 |
| /careers/ | 273 | 307 |
| /about/ | 260 | 280 |
| Open Concept Blog Post | 127 | 131 |
| /services/restoration/ | 122 | 129 |

### Top Landing Pages

| Landing Page | Sessions | Bounce Rate | Avg. Session Duration |
| --- | --- | --- | --- |
| Homepage (/) | 1,968 | 37.96% | 3:20 min |
| /services/custom-homes | 706 | 67.28% | 0:45 min |
| /about/team | 249 | 48.99% | 3:24 min |
| (not set) | 209 | 100% | 0:00 min |
| /services/home-remodels | 160 | 75% | 0:58 min |
| /contact | 120 | 69.17% | 2:06 min |
| Open Concept Blog Post | 119 | 53.78% | 1:14 min |
| /careers | 105 | 64.76% | 2:04 min |
| /about | 86 | 52.33% | 2:19 min |
| Kitchen Remodel Landing Page | 86 | 66.28% | 0:43 min |

### Key Insights:

- **High Homepage Engagement**: The homepage has the lowest bounce rate (37.96%) and strong session duration (3:20 min), suggesting effective design and content.
- **Service Page Opportunity**: The high bounce rates on service pages (/services/custom-homes, /services/home-remodels) indicate potential for improved content or calls-to-action.
- **Team Page Success**: The /about/team page shows strong engagement metrics, indicating potential interest in the company's personnel and expertise.
- **Technical Issue**: The "(not set)" landing page with 100% bounce rate suggests a technical issue that should be investigated.

## Conversion Analysis

The conversion tracking data indicates no recorded conversion events during the reporting period. This suggests:

1. Conversion tracking may not be properly implemented
2. Goals and conversion events may need to be defined in Google Analytics
3. The website may lack clear conversion points or effective calls-to-action

---

This report provides a foundation for data-driven decision making and ongoing website optimization. Regular monitoring of these metrics is recommended to track progress and identify new trends.

# Marketing Strategies

| Priority (plan) | What the data says now | Strategic move | Quick metric to watch |
| --- | --- | --- | --- |
| **1. Conversion-rate optimisation (CRO)** | • Contact page lands 120 sessions in May yet bounces 69 % (GA).<br>• Service pages bounce 66-75 %.<br>• CRM closes 62 of 237 lifetime leads (26 %) but top-of-funnel is only \~15 leads/month. | *Fix what is visible first.*<br>• Compress mobile page-load by 1 s; a 2 % lift in conversions is typical (Impact study). ([impact.com](https://impact.com/marketing-intelligence/mobile-seo-in-2025/?utm_source=chatgpt.com))<br>• Add a cost-range PDF or “5-minute budget calculator” CTA to every high-bounce service page to target a 40 % bounce rate.<br>• Turn every site form into a GA4 event and tie it to the “Has Opportunity Been Contacted?” field in CRM. | • Form-submission CVR (goal: ≥3 %, the search-ad benchmark for construction). ([localiq.com](https://localiq.com/blog/home-services-search-advertising-benchmarks/?utm_source=chatgpt.com)) |
| **2. Google Ads pilot** | • Traffic doubled in Apr-May without paid spend, proving search demand.<br>• Average CPC for home-improvement Google Ads in 2025 runs **\$1.63-\$5.26**. ([agencyanalytics.com](https://agencyanalytics.com/blog/google-ads-cost?utm_source=chatgpt.com), [wordstream.com](https://www.wordstream.com/blog/google-ads-cost?utm_source=chatgpt.com)) | • Capture 25 extra qualified leads/month (to hit the plan’s 40 QL).<br>At a 7.3 % search-ad CVR and \$5.26 CPC, budget **≈ \$1.8 k/mo** for 340 clicks. ([localiq.com](https://localiq.com/blog/home-services-search-advertising-benchmarks/?utm_source=chatgpt.com), [wordstream.com](https://www.wordstream.com/blog/google-ads-cost?utm_source=chatgpt.com)) | • Cost-per-lead versus the CRM average revenue per sold job (**≈ \$120 k**). |
| **3. Blog & resource publishing** | • Two blog posts in top-10 entrances, but each under 1 min view time.<br>• Content creation claims only 10 % of average construction marketing budgets. ([webfx.com](https://www.webfx.com/industries/home-repair/construction/statistics/?utm_source=chatgpt.com)) | • Shift from generic blogs to “Neighborhood guide” and “Storm-repair checklist” formats—top 2025 builder trends. ([newhomestar.com](https://www.newhomestar.com/blog/home-builder-marketing-agency?utm_source=chatgpt.com))<br>• Repurpose every post into short-form video; video is the highest-growth format for builders in 2025. ([dotmarketingsd.com](https://dotmarketingsd.com/marketing-trends-in-the-construction-industry-for-2025/?utm_source=chatgpt.com)) | • Organic sessions that land on new guides (goal: 500/month by Q4). |
| **4. News & press wins (Parks PR)** | • 0 media mentions logged; Source field blank on 67 % of rows. | • Pitch “Storm-season readiness” in July while restoration makes up 30 % of pipeline demand.<br>• Tag every press-driven lead as “Earned Media” in CRM to prove ROI. | • Earned-media leads per quarter (goal: 3 in Q3, 5 in Q4). |
| **5. Data hygiene (CRM + GA)** | • 5 of 15 key columns are >60 % blank (Source, Activity, Revenue).<br>• GA shows 0 conversions events. | **CRM** – make Source, Phone, Revenue Min mandatory; auto-populate Next Activity before saving.<br>**GA** – rebuild GA4 with: <br>  • Form-submit and phone-click events<br>  • UTM hidden fields that write directly into CRM Source<br>  • Monthly integrity audit run by Rowan | • “Unknown Source” rows (target <20 % by October).<br>• GA4 events firing rate (goal: 100 %). |

---

### How this supports the three strategic pillars

1. **Credibility & Trust**
Press placements + educational guides position Scroggs as the storm-recovery and fixed-budget authority. Blog/video cadence also feeds social proof.
2. **Predictable Demand Generation**
CRO plus paid-search math shows that a repeatable ad budget of about \$2 k can fill the 25-lead gap between current intake and the 6-month goal.
3. **Referral Flywheel**
Better tracking lets you prove ROI on partner and past-client referrals, then automate quarterly check-ins once Source data is clean.

---

### Two broader 2025 trends to lean on

- AI-guided content personalisation is now mainstream; 71 % of CMOs are investing eight-figure budgets in AI tools to optimise creative and media. ([businessinsider.com](https://www.businessinsider.com/marketing-leaders-ai-strategies-cmo-insider-breakfast-cannes-lions-2025-6?utm_source=chatgpt.com))
**Action**: Let Rowan’s AI engine produce variant headlines and meta-descriptions for each service page based on GA engagement signals.
- Mobile-first indexing punishes slow pages, and even a one-second speed gain lifts conversions by 2 %. ([impact.com](https://impact.com/marketing-intelligence/mobile-seo-in-2025/?utm_source=chatgpt.com))
**Action**: bundle image compression and lazy-loading into the upcoming CRO sprint.

---

# Marketing Plan:

### Executive Snapshot

**North-Star Goal**

Fill every crew calendar with profitable work (*Homes Loved* remodels/restorations, $750 k–$1.5 m new homes) and prepare for market expansion—so Scroggs keeps a healthy backlog and clients experience “no-surprise” budgets.

**Three Strategic Pillars**

1. **Credibility & Trust** – position Scroggs as Western NC’s go-to expert through media coverage, educational “news-you-can-use” content, and social proof.
2. **Predictable Demand Generation** – boost digital visibility and capture intent traffic to balance referrals with net-new leads.
3. **Referral Flywheel** – formalize past client and partner touch-points so referrals remain the largest, lowest-cost source of signed work

**Headline Metrics – placeholders (set after discovery)**

- Qualified Leads per Month: **TBD**
- Signed Contract Value per Month: **TBD**
- Jobs Won from Referrals (%): **TBD**

Launch Plan:

**Communications**

- Enhance social media feeds with quality content, while pursuing ways to get
followers who are part of Scroggs’ key audiences.
- Establish Scroggs as an expert on remodels and new builds with the area news
media by talking about storm recovery and the building industry in general. This work will leverage Nick’s role as this year’s president of the Builders Association of the Blue Ridge Mountains.
- Create content on the website that provides “news you can use” for people considering a remodel or new build.
- Write and distribute news releases when appropriate for significant news about the company.
- Media train top Scroggs leaders and external-facing Scroggs employees.

**Marketing**

- Create or enhance tracking systems so we can effectively measure our marketing efforts.
- Promote referral program.
- Enhance company website to be more sales-driven, by optimizing UX and creating ways for users to easily ask questions and start a conversation. Also, improve presentation by focusing on the best photos and writing more impactful copy.

- Create a plan for digital advertising for company consideration that would start with a small spend, then increase that as we show results. This should tie to defining search terms for SEO and SEM where we want to clearly stand out.
- [Own the Neighborhood Campaign](https://www.notion.so/Own-the-Neighborhood-Campaign-207a968141c880bbb040fd33c717a2a9?pvs=21) : primarily focused on mailers to areas with high density of jobs.