# 📊 MODULE 4: RFQ TRACKING DASHBOARD (ENHANCED)

## OVERVIEW

Real-time visibility into all RFQs, pipeline status, conversion funnels, and team performance. Built in Looker Studio (free, auto-updating) for executive dashboards and daily operations.

**Core Goal:** One-screen view of business health → identify bottlenecks → track KPIs → celebrate wins

---

## 🎯 DASHBOARD ARCHITECTURE

### Dashboard 1: Executive Summary (Real-Time at a Glance)

**Metrics Displayed:**

```
┌─────────────────────────────────────────────────────────────┐
│                    RFQ-HUB EXECUTIVE DASHBOARD              │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│ 📊 KPI CARDS (Top Row)                                      │
│ ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐   │
│ │ RFQs     │  │ Quotes   │  │ Deals    │  │ Revenue  │   │
│ │ This     │  │ Sent     │  │ Closed   │  │ This     │   │
│ │ Month    │  │ (Pending)│  │ MTD      │  │ Month    │   │
│ │ 47       │  │ 12       │  │ 8        │  │ $456K    │   │
│ └──────────┘  └──────────┘  └──────────┘  └──────────┘   │
│                                                             │
│ 📈 PIPELINE FUNNEL (Center)                                │
│ ┌────────────────────────────────────────────────────────┐ │
│ │ RFQs Received: 47                                      │ │
│ │ ├─ Quotes Sent: 38 (81%)                              │ │
│ │    ├─ Negotiating: 12 (31% of quoted)                 │ │
│ │    ├─ Won: 8 (21% of quoted)                          │ │
│ │    └─ Lost: 18 (47% of quoted)                        │ │
│ │                                                         │ │
│ │ Pipeline Value: $234K (open opportunities)             │ │
│ │ Close Rate This Month: 21% (target: 25%)               │ │
│ └────────────────────────────────────────────────────────┘ │
│                                                             │
│ 💰 REVENUE BREAKDOWN (Bottom Left)                         │
│ ┌─────────────────────────────────────────────────────┐  │
│ │ By Category:                                        │  │
│ │ PPE: $125K (27%)        IT: $95K (21%)              │  │
│ │ Power: $156K (34%)      Security: $80K (18%)        │  │
│ │ Total MTD: $456K                                    │  │
│ └─────────────────────────────────────────────────────┘  │
│                                                             │
│ 👥 TEAM PERFORMANCE (Bottom Right)                         │
│ ┌────────────────────────────────────────────────────┐   │
│ │ Top Performers (RFQs Generated)                    │   │
│ │ 1. John: 15 RFQs | 7 closed | $125K                 │   │
│ │ 2. Sarah: 12 RFQs | 4 closed | $85K                 │   │
│ │ 3. Mike: 10 RFQs | 2 closed | $45K                  │   │
│ │ Avg Team: 11.7 RFQs | 3.7 closed | $85K            │   │
│ └────────────────────────────────────────────────────┘   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**Data Sources:**
- RFQ count: Google Sheets "RFQ Pipeline" sheet (auto-update)
- Revenue: Google Sheets "Deals" sheet (auto-calculate)
- Team metrics: Google Sheets "Team Performance" tracker

---

### Dashboard 2: Pipeline Details (Dig Deeper)

**Metrics:**

```
┌──────────────────────────────────────────────────────────────┐
│              RFQ PIPELINE DETAILS DASHBOARD                  │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│ STATUS BREAKDOWN (Donut Chart)                               │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ New (Unquoted): 9 (19%)       [Blue segment - 19%]     │ │
│ │ Quoted (Pending): 12 (26%)    [Yellow segment - 26%]   │ │
│ │ Negotiating: 14 (30%)         [Orange segment - 30%]   │ │
│ │ Won: 8 (17%)                  [Green segment - 17%]    │ │
│ │ Lost: 4 (8%)                  [Red segment - 8%]       │ │
│ └─────────────────────────────────────────────────────────┘ │
│                                                              │
│ DAYS IN PIPELINE (Horizontal Bar)                            │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ Status               Avg Days  Min  Max  # of Deals     │ │
│ │ New → Quoted            2     1    5     9             │ │
│ │ Quoted → Negotiating    5     2    12    12            │ │
│ │ Negotiating → Won       7     3    21    8             │ │
│ │ Total Cycle Time        14    5    38    8             │ │
│ │                                                         │ │
│ │ [Goal: Keep <21 days]                                  │ │
│ └─────────────────────────────────────────────────────────┘ │
│                                                              │
│ BY URGENCY LEVEL (Table)                                     │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ Urgency     RFQs  Quoted  Won  Close Rate  Avg Value  │ │
│ │ ASAP (<24h)  8     8      4    50%         $32,500    │ │
│ │ This week    18    15     6    40%         $28,000    │ │
│ │ This month   15    12     3    25%         $15,000    │ │
│ │ 60+ days     6     3      0    0%          $8,000     │ │
│ │                                                        │ │
│ │ Key: Urgent deals close faster! (50% vs 25%)         │ │
│ └─────────────────────────────────────────────────────────┘ │
│                                                              │
│ VALUE AT RISK (Open Quotes Not Closed - Table)             │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ Company         Category     Amount   Days Quoted  Action │ │
│ │ Guyana Energy   PPE          $25K     8 days      Follow  │ │
│ │ Constructor Inc Tools        $15K     5 days      Urgent  │ │
│ │ Gov Agency      IT           $45K     12 days     ALERT   │ │
│ │ Total at Risk: $85K                                      │ │
│ └─────────────────────────────────────────────────────────┘ │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

---

### Dashboard 3: Category Performance

**Metrics:**

```
┌──────────────────────────────────────────────────────────────┐
│            CATEGORY PERFORMANCE DASHBOARD                    │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│ CATEGORY BREAKDOWN (Comparison Chart)                        │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │                                                         │ │
│ │  PPE      IT      Power   Security  Tools    Marine    │ │
│ │  ▓▓▓▓     ▓▓▓▓    ▓▓▓▓▓   ▓▓▓      ▓▓       ▓         │ │
│ │  $125K    $95K    $156K   $80K     $12K     $5K       │ │
│ │  (27%)    (21%)   (34%)   (18%)    (3%)     (1%)      │ │
│ │                                                         │ │
│ │  RFQs: 12  RFQs: 10  RFQs: 15  RFQs: 8  RFQs: 2 RFQs: 0 │ │
│ │  Close: 10  Close: 7  Close: 8  Close: 2  Close: 0 Close: 0 │ │
│ │  83% rate  70% rate  53% rate  25% rate   0% rate  0% rate   │ │
│ └─────────────────────────────────────────────────────────┘ │
│                                                              │
│ KEY INSIGHTS                                                 │
│ ├─ 💪 Strongest Category: Power (34% of revenue, $156K)     │
│ ├─ 📈 Best Close Rate: PPE (83% win rate)                   │
│ ├─ ⚠️  Weakest Performance: Marine (0% revenue)             │
│ ├─ 🎯 Opportunity: Focus on Power + PPE bundles            │
│ └─ 💡 Strategic: Cross-sell IT to Power deals              │
│                                                              │
│ CATEGORY TRENDS (Line Chart - Last 12 Months)              │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ Revenue   $160K ├─  Power (trending up) ▲              │ │
│ │           $120K ├─ PPE (stable) ━                       │ │
│ │           $80K  ├─ IT (trending up) ▲                  │ │
│ │           $40K  ├─ Security (stable) ━                 │ │
│ │           $0K   ├─────────────────────────────────     │ │
│ │                 Jan Feb Mar Apr May  ...Dec           │ │
│ └─────────────────────────────────────────────────────────┘ │
│                                                              │
│ SUPPLIER PERFORMANCE (By Category)                           │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ Category   Primary Supplier      Quote Time  Lead Time │ │
│ │ PPE        Local PPE Dist.       <30 min     1-2 days  │ │
│ │ IT         Distributor XYZ       <60 min     2-3 days  │ │
│ │ Power      Power Solutions Inc   45-60 min   3-5 days  │ │
│ │ Security   Security Installers   <120 min    5-7 days  │ │
│ └─────────────────────────────────────────────────────────┘ │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

---

### Dashboard 4: Team Leaderboard & Performance

**Metrics:**

```
┌──────────────────────────────────────────────────────────────┐
│                  TEAM PERFORMANCE DASHBOARD                  │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│ MONTHLY LEADERBOARD (Primary Metrics)                        │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ Rank │ Name  │ RFQs │ Quoted │ Won │ Close % │ Revenue   │ │
│ │──────┼───────┼──────┼────────┼─────┼─────────┼─────────│ │
│ │ 🥇 1 │ John  │  15  │  13    │  7  │  54%    │ $125K    │ │
│ │ 🥈 2 │ Sarah │  12  │  11    │  4  │  36%    │  $85K    │ │
│ │ 🥉 3 │ Mike  │  10  │   8    │  2  │  25%    │  $45K    │ │
│ │ 4    │ Lisa  │   8  │   7    │  2  │  29%    │  $38K    │ │
│ │ 5    │ David │   6  │   5    │  1  │  20%    │  $18K    │ │
│ │──────┼───────┼──────┼────────┼─────┼─────────┼─────────│ │
│ │TEAM  │ TOTAL │  51  │  44    │ 16  │  36%    │ $311K    │ │
│ │TARGET│ GOAL  │  80  │  70    │ 25  │  36%    │ $500K    │ │
│ │      │ %     │ 64%  │  63%   │ 64% │ ON PACE │  62%    │ │
│ └─────────────────────────────────────────────────────────┘ │
│                                                              │
│ INDIVIDUAL DASHBOARDS (Example: John)                        │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ John's May Performance                                  │ │
│ │                                                         │ │
│ │ Daily Targets vs Actual                                │ │
│ │ ├─ RFQs Generated: 15 / 20 target (75%) ⚠️            │ │
│ │ ├─ Calls Made: 8 / 10 target (80%)                    │ │
│ │ ├─ Site Visits: 3 / 3 target (100%) ✅               │ │
│ │ ├─ Deals Closed: 7 / 5 target (140%) 🎉              │ │
│ │ └─ Revenue Generated: $125K / $100K (125%) 🚀         │ │
│ │                                                         │ │
│ │ Week-by-Week Trend                                     │ │
│ │ Week 1: 2 RFQs | Week 2: 3 | Week 3: 5 | Week 4: 5   │ │
│ │ (Trending up mid-month - Good!)                        │ │
│ │                                                         │ │
│ │ Bonus Tracking                                          │ │
│ │ ├─ Base quota bonus: 140% × $500 = $700               │ │
│ │ ├─ Cross-sell bonus: 3 deals × $50 = $150             │ │
│ │ ├─ Quality bonus: <2% lost deals = +$100              │ │
│ │ └─ Total bonus this month: $950 ✅                    │ │
│ └─────────────────────────────────────────────────────────┘ │
│                                                              │
│ TEAM HEALTH INDICATORS                                       │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ Indicator              Status  Trend  Action            │ │
│ │ Avg RFQs/Person/Day    7.3     ▲      Good             │ │
│ │ Quote Turn Time        2.1 hrs  ▼      Excellent       │ │
│ │ Close Rate             36%      ▲      On target        │ │
│ │ Customer Satisfaction  4.6/5    ▲      Excellent       │ │
│ │ Attrition              0%       ▲      Stable           │ │
│ │ Burnout Risk           Low      ▼      Healthy          │ │
│ └─────────────────────────────────────────────────────────┘ │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

---

## 🛠️ BUILDING THE DASHBOARD (Looker Studio Steps)

### Step 1: Connect Data Sources

**In Looker Studio:**
```
1. Create new report
2. Add data source #1: "RFQ Pipeline" (Google Sheet)
   ├─ Sheet: "RFQ_Pipeline_Master"
   ├─ Range: All data
   └─ Auto-refresh: Every 1 hour

3. Add data source #2: "Sales Performance" (Google Sheet)
   ├─ Sheet: "Team_Performance"
   ├─ Range: All data
   └─ Auto-refresh: Every 1 hour

4. Add data source #3: "Deals" (Google Sheet)
   ├─ Sheet: "Closed_Deals"
   ├─ Range: All data
   └─ Auto-refresh: Every 1 hour
```

---

### Step 2: Create Scorecards (KPI Cards)

**Example Scorecard: RFQs This Month**

```
Element: Scorecard
Data Source: RFQ Pipeline
Metric: COUNT of RFQ ID (where Date >= Start of Month)
Label: "RFQs This Month"
Big Number: [Autocomputed from data]
Comparison: Previous month (calculate ▲ or ▼)
Formatting: 
├─ Green if > target (Target: 80)
├─ Yellow if 60-80
└─ Red if < 60
```

---

### Step 3: Create Pipeline Funnel

**Element: Funnel Chart**

```
Data Source: RFQ Pipeline
Dimension: Status (New, Quoted, Negotiating, Won, Lost)
Metric: COUNT of RFQ ID
Sort: By order (New → Won)

Result: Visual showing progression through sales funnel
```

---

### Step 4: Create Revenue Charts

**Element: Pie Chart (By Category)**

```
Data Source: Deals (Closed Only)
Dimension: Category
Metric: SUM of Deal Value
Formatting: Show percentage + absolute value
Colors: By category (Blue=PPE, Green=IT, etc.)
```

---

### Step 5: Create Team Leaderboard

**Element: Table**

```
Data Source: Team Performance
Rows: Sales Person Name
Columns:
├─ RFQs Generated (COUNT)
├─ Deals Closed (COUNT where Status = "Won")
├─ Close Rate (Calculated: Closed/Quoted)
├─ Revenue (SUM of Deal Values)
└─ Bonus (Calculated: Revenue × Bonus %)

Sorting: By Revenue (Descending)
Formatting: Color-code cells (Green=Good, Red=Below target)
```

---

### Step 6: Create Trend Lines

**Element: Time Series Chart**

```
Data Source: RFQ Pipeline + Deals
Dimension: Date (Group by: Week)
Metrics:
├─ RFQs Received (line 1 - blue)
├─ Quotes Sent (line 2 - yellow)
├─ Deals Closed (line 3 - green)
└─ Revenue (line 4 - gold)

This shows business momentum over time
```

---

## 📱 DASHBOARD REFRESH SCHEDULE

### Real-Time (Every 1 Hour)
```
✓ Looker Studio auto-refresh
✓ Email alerts for major changes
✓ Slack notifications for wins/losses
```

### Daily (9 AM)
```
✓ Review overnight submissions
✓ Check urgent follow-ups
✓ Update team targets
✓ Send daily standup report
```

### Weekly (Monday 9 AM)
```
✓ Full pipeline review
✓ Forecast vs actuals
✓ Category performance review
✓ Team leaderboard update
✓ Send to leadership
```

### Monthly (1st of Month)
```
✓ Full dashboard audit
✓ Data validation
✓ Historical comparison
✓ Strategic review
✓ Bonus calculation
```

---

## 📧 AUTOMATED REPORTING

### Daily Slack Report (9 AM)

```
Channel: #rfq-hub-daily

🚀 RFQ-Hub Daily Standup - [Date]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
TODAY'S NUMBERS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 RFQs Received: 4 (vs 3 target) ✅
💰 Quotes Sent: 3 (vs 2 target) ✅
🎉 Deals Closed: 1 ($28,500)
📈 Revenue Today: $28,500

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
MONTH-TO-DATE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 RFQs: 47 / 80 target (59%)
💰 Revenue: $311K / $500K target (62%)
🎯 Close Rate: 36% (Target: 35%) ✅

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
TOP PERFORMER
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🥇 John: 15 RFQs, 7 deals, $125K

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
ALERTS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
⚠️ Quote from Guyana Energy (PPE, $25K) 
   pending 8 days - FOLLOW UP TODAY
```

---

### Weekly Email Report (Friday 5 PM)

```
Subject: 📊 RFQ-Hub Weekly Report [Week Ending Date]

FROM:     dashboard@rfqhub.gy
TO:       [Leadership + Sales Team]

(Includes all dashboard screenshots + trend analysis)
```

---

### Monthly Board Report (1st of Month)

```
Subject: 💼 RFQ-Hub Monthly Performance Review - [Month]

EXECUTIVE SUMMARY
├─ RFQs: 47 (vs 80 target = 59% pace)
├─ Revenue: $311K (vs $500K target = 62% pace)
├─ Close Rate: 36% (on target)
└─ Pipeline Health: $234K (good for next month)

DASHBOARD LINK: [Looker Studio Dashboard Link]
(Interactive - click cells to see details)

RECOMMENDATION: [Brief strategic note]
```

---

## ✅ IMPLEMENTATION CHECKLIST

```
Week 1: Setup
☐ Create Google Sheet master datasets
☐ Set up data formulas + auto-calculations
☐ Create Looker Studio account
☐ Connect Google Sheets as data sources
☐ Build scorecard cards (RFQs, Quotes, Deals, Revenue)

Week 2: Dashboards
☐ Create Executive Summary dashboard
☐ Create Pipeline Details dashboard
☐ Create Category Performance dashboard
☐ Create Team Leaderboard dashboard
☐ Test with dummy data

Week 3: Automation
☐ Set up daily Slack reports (via Zapier)
☐ Set up weekly email reports
☐ Configure Looker Studio auto-refresh
☐ Create alert rules (high-value quotes, stalled deals)
☐ Train team on dashboard reading

Week 4: Optimization
☐ Share dashboards with leadership
☐ Gather feedback on visualizations
☐ Adjust metrics based on feedback
☐ Begin using for daily decisions
☐ Celebrate first data-driven wins!
```

---

**NEXT STEP:** Move to Module 5 - Response Engine (Multi-Supplier Model)

