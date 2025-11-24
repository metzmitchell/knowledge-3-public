---
type: prompt
tags: ["prompt", "ai"]
---

# Input 1

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

### Situation Snapshot

**Business Facts**

Scroggs has expanded crews and management capacity and is ready to scale beyond its traditional, referral-driven pipeline. Recent marketing efforts via an outside agency provided little visibility into what was working, so leadership still lacks a predictable, measurable way to fill the new capacity. The company’s design-build and “Homes Loved” services already deliver high client satisfaction; what’s missing is an investment-ready marketing engine, and a consistent communications program—press coverage, educational blog content, and authoritative social storytelling—to elevate credibility and make prospective clients feel they’re choosing the most trustworthy builder in Western North Carolina.

**Market Facts**

Western North Carolina remains supply-constrained and price-strong, buoyed by in-migration and a spike in storm-related restoration demand. Local news cycles spotlight rebuilding, affordability, and energy efficiency—topics perfectly aligned with Scroggs’ expertise yet still under-represented by the brand. Competitors cluster at opposite ends: small remodelers who rely solely on referrals and luxury firms with polished storytelling. An upper-middle-market design-build company that pairs a trustworthy family-owned business with authoritative communications can capture white-space authority and demand.

**Audience Facts**

Core buyers are mid- to upper-income homeowners—long-time locals upgrading tired spaces and newcomers seeking a trustworthy builder for major projects. They vet companies online, weigh third-party coverage heavily, and rely on referrals from realtors, architects, trades, and friends. These gatekeepers, in turn, need a builder whose expertise is visible in press quotes, blog guidance, and media-trained staff. Scroggs’ growth, therefore, hinges on a balanced approach: measurable demand generation that fills the new capacity *and* a communication program that makes every lead feel they’re choosing the most credible builder in the region.

### Goals & Focus Metrics - *Scorecards*

Example numbers. To be determined once we know baseline.

| KPI | Baseline† | 6-Mo Target | 12-Mo Target | Why it Matters |
| --- | --- | --- | --- | --- |
| **Qualified Leads / Month** | ~20 | 30 | 40 | Direct measure of demand-gen success. |
| **Pipeline $ Created / Month** | ~$1.2 M | $1.6 M | $2.0 M | Shows marketing’s impact before projects fully close. |
| **Earned Media Mentions / Quarter** | 0–1 | 3 | 5 | Validates Credibility & Trust pillar. |
| **Referral Share of Leads (%)** | 80 % | 75 % | 65 % | Keeps referrals healthy while diversifying sources. |

### Audience & Positioning

**Customer Promise**

We turn big ideas into finished spaces—on the budget you expect and the date we promise—so you enjoy living in your home, not managing the build. Our cost-plus approach with a built-in variance line removes the “surprise invoice” from every project.

**Key Personas & Their Pain Points**

| Persona | What keeps them up at night? |
| --- | --- |
| **Dream Builder** *(relocating family planning a custom home)* | • Fear of hidden costs after committing to land and plans  • Uncertainty about vetting builders from out of state  • Tight timeline for moving kids before the new school year |
| **Legacy Upgrader** *(long-time local focused on large remodel / “Homes Loved”)* | • Living in chaos during a phased remodel  • Sticker shock from scope creep and change-orders  • Anxiety about contractors respecting the character of their home |
| **Storm Restorer** *(homeowner navigating insurance-funded repairs)* | • Confusion over insurance paperwork and allowances  • Pressure to finish fast before temporary housing costs pile up  • Worry that “quick fix” contractors will cut corners |

---

---

**Positioning Statement**

Scroggs is Western North Carolina’s design-build partner for remodels, restorations, and cost-plus custom homes—delivering transparent budgets, fixed completion commitments, and craftsmanship homeowners proudly show off for decades.

### Strategic Pillars

These are preliminary themes based on what we know today; we’ll validate or adjust them as we move forward.

| Pillar | Focus | Early Rationale |
| --- | --- | --- |
| **Authority & Communication** | Consistent **press coverage, “news-you-can-use” content, and social storytelling** that make Scroggs the region’s trusted advisor. | Credibility shortens sales cycles and makes every paid/organic click more persuasive. |
| **Predictable Demand Generation** | Grow **net-new, trackable traffic** (SEO, paid search, local listings) to balance today’s referral dependence. | New crew capacity needs a controllable pipeline—referrals alone won’t fill the gap. |
| **Referral Flywheel** | Systemize past client and partner touch-points (realtors, architects, insurers) to keep referrals growing even as other channels scale. | Referrals are high-quality and low-cost; a formal program preserves this edge while we diversify. |
| **Website Conversion & Tracking** | Turn *existing* and future visitors into inquiries via clearer CTAs, lead magnets, and end-to-end analytics. | The site already gets traffic but converts inconsistently; quick CRO wins accelerate ROI. |

### Launch Plan

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

**Tentative 90 Day Roadmap**

| Workstream | Month 1 | Month 2 | Month 3 |
| --- | --- | --- | --- |
| **Discovery & Baselines** | 🚀 Launch workshops & data pull |  |  |
| **Website CRO** | 🚀 Implement new CTAs | 📈 Review conversion lift | Other opportunities, like lead magnet |
| **Paid Search Pilot** |  | 🚀 Campaign launch | 📈 Scale / prune based on CPL |
| **Press & Media** | 🚀 Conduct mini media-training for key people | 🚀 Land media coverage |  |
| **Content Hub Posts** | 🚀 Post 1 & 2 live | 🚀 Establish posting cadence and workflow | 📈 Track and update content strategy |
| **Referral Flywheel** | 🚀 Refine referral programs | 🚀 Launch outreach + update partner list | 📈 iterate |

# Business Plan

### 3-YEAR PICTURE™

**Future Date:** 12/31/2028

**Revenue:** $15 million

**Profit:** $1.5 million EBITDA (10%)

**Measurables:**

- Homes improved: 50
- New homes: 10

**What does it look like?**

- 35 RPRS
- Fully developed marketing strategy
- Core processes simplified, documented, and followed by all
- Satellite office/location
- Vendor/professional partnerships
- Spec test complete
- Better spending controls
- Warehouse purchased/rented
- HQ expanded
- Expansion plan ready for implementation

---

### CORE FOCUS

**Purpose / Cause / Passion:** Help people fall in love with their home

**Niche:** End-to-end construction solutions

---

### 10-YEAR TARGET

**$40 million in annual revenue and multiple locations**

---

### MARKETING STRATEGY

**Target Market / "The List":**

Homeowners, retirees, and transplants looking to buy, build, or remodel around Asheville, who want a collaborative building experience.

**3 Uniques™:**

1. Your vision realized
2. Expectations set, expectations met
3. All under 1 roof

**Proven Process:**

**Our 7 Step Design-Build Process**

→ Plan

→ Reach Out

→ Uncover

→ Design

→ Pre-Construction

→ Build

→ Finish

---

## TRACTION

### 1-YEAR PLAN

**Future Date:** 12/31/2025

**Revenue:** $10 million

**Profit:** $500k EBITDA (5%)

**Measurables:**

- Homes improved: 45
- New homes: 3

**Goals for the Year:**

1. Complete capital budgeting covering next 3 years
2. All production team members complete 100% of training modules
3. Transition budgeting from top down to bottom up
4. Full EOS rollout
5. Identify 3 potential satellite offices
6. Define go-forward relationship with external marketing partners
7. *(Blank)*

---

### ROCKS – Q3 2025

**Future Date:** 7/15/2025

**Revenue:** $4.5 million

**Profit:** $100k EBITDA

**Measurables:**

- Homes improved: 28
- New homes: 2