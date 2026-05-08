# 📊 MODULE 1: MULTI-CATEGORY CONTACT DATABASE SYSTEM

## OVERVIEW

The foundation of the entire RFQ system. A structured, segmented contact database that enables rapid prospecting, relationship tracking, and revenue analysis across multiple customer verticals and product categories.

**Core Goal:** Turn scattered contacts into a systematized, actionable pipeline that drives 20+ daily WhatsApp outreaches with precision targeting.

---

## 🏢 INDUSTRY VERTICAL SEGMENTATION (GUYANA FOCUS)

### 1. Oil & Gas Sector
**Why Priority #1:**
- Largest contract sizes ($50K-$500K+ per deal)
- High recurring needs (safety, power, equipment)
- Long-term partnerships (sticky revenue)
- Operates year-round

**Sub-Categories:**
- Exploration companies
- Drilling contractors
- Logistics/supply
- Maintenance services
- Safety & compliance

**Contact Titles:**
- Procurement Manager
- Site Manager
- HSE Officer (Health, Safety, Environment)
- Logistics Coordinator
- Compliance Officer

**Product Needs:**
- PPE (high volume, safety-critical)
- Industrial tools
- Power systems (critical for operations)
- Safety monitoring
- Marine supplies (for offshore)

---

### 2. Construction & Engineering

**Why Priority #2:**
- High volume (many active projects)
- Predictable seasonal patterns
- Multiple departments per company
- Cross-sell opportunity (PPE + tools + power)

**Sub-Categories:**
- Civil contractors
- Electrical contractors
- Plumbing/HVAC
- Project developers
- Equipment rental firms

**Contact Titles:**
- Project Manager
- Site Supervisor
- Procurement Officer
- Safety Officer
- Equipment Manager

**Product Needs:**
- PPE (helmets, harnesses, safety)
- Tools & equipment
- Power systems (site generators)
- Security (site monitoring)
- IT (site management)

---

### 3. Government & Public Sector

**Why Priority #3:**
- Recurring high-volume orders
- Budget cycles (predictable timing)
- Multiple touchpoints (different agencies)
- Contract opportunities (bid on frameworks)

**Sub-Categories:**
- Health facilities (hospitals, clinics)
- Schools & universities
- Government departments
- Water Authority (GWWC)
- Utilities (PowerUp, etc.)

**Contact Titles:**
- Procurement Manager
- Budget Officer
- Department Head
- Facilities Manager
- IT Manager

**Product Needs:**
- PPE (hospitals, utilities)
- IT hardware (schools, gov offices)
- Power systems (critical infrastructure)
- Security (government buildings)
- Office equipment

---

### 4. Corporate Offices & Services

**Why Priority #4:**
- Steady recurring demand
- Professional buyers (easy to work with)
- Multi-category needs (IT + office + power)
- Steady payment terms

**Sub-Categories:**
- Financial services
- Insurance companies
- Professional services
- BPO/Call centers
- Telecom companies

**Contact Titles:**
- Procurement Manager
- Facilities Manager
- IT Manager
- Office Manager
- CFO

**Product Needs:**
- IT hardware
- Office equipment
- Power systems (UPS, generators)
- Security systems
- WiFi/networking

---

### 5. Utilities & Telecoms

**Why Emerging Priority:**
- Large capital projects
- Long-term contracts
- Predictable renewal cycles
- High dollar value

**Sub-Categories:**
- Power companies
- Water utilities
- Telecom operators
- Internet service providers
- Data centers

**Contact Titles:**
- Procurement Manager
- Operations Manager
- Infrastructure Manager
- Project Manager
- IT Manager

**Product Needs:**
- Power systems (backup, UPS)
- IT infrastructure
- Networking equipment
- Security monitoring
- Marine/power cable supplies

---

### 6. Hospitality & Tourism

**Why Secondary Priority:**
- Growing sector in Guyana
- Consistent maintenance needs
- VIP service opportunity
- Seasonal adjustments

**Sub-Categories:**
- Hotels & resorts
- Restaurants & bars
- Event venues
- Tourism operators
- Entertainment facilities

**Contact Titles:**
- General Manager
- Operations Manager
- Facilities Manager
- Head of Security
- IT Manager

**Product Needs:**
- Security systems
- Power backup
- WiFi/IT infrastructure
- Office equipment
- PPE for staff

---

## 🗂️ CONTACT DATABASE SCHEMA

### Core Fields (Required for Every Contact)

```
┌─────────────────────────────────────────┐
│ CONTACT CORE INFORMATION                │
├─────────────────────────────────────────┤
│ 1. Contact ID (Auto-generated)          │ Unique identifier
│ 2. Full Name                            │ First + Last
│ 3. Job Title                            │ Procurement Manager, etc.
│ 4. Company Name                         │ Official company name
│ 5. Company Size                         │ Micro/Small/Medium/Large
│ 6. Industry Vertical                    │ Oil & Gas, Construction, etc.
│ 7. Phone (WhatsApp)                     │ +592-XXX-XXXX format
│ 8. Email                                │ Primary business email
│ 9. LinkedIn Profile                     │ If available
│ 10. Company Website                     │ If available
│ 11. Physical Address                    │ Office location
│ 12. Date Added                          │ When contact was captured
│ 13. Source                              │ LinkedIn, Referral, Cold, Event
│ 14. Status                              │ New, Active, Prospect, Customer
└─────────────────────────────────────────┘
```

### Product Interest Fields

```
┌─────────────────────────────────────────┐
│ PRODUCT CATEGORY INTEREST               │
├─────────────────────────────────────────┤
│ 1. PPE Interest                         │ Yes/No/Maybe
│ 2. Industrial Tools Interest            │ Yes/No/Maybe
│ 3. IT Hardware Interest                 │ Yes/No/Maybe
│ 4. Security Systems Interest            │ Yes/No/Maybe
│ 5. Power & Backup Interest              │ Yes/No/Maybe
│ 6. Marine Supplies Interest             │ Yes/No/Maybe
│ 7. Construction Supplies Interest       │ Yes/No/Maybe
│ 8. Office Equipment Interest            │ Yes/No/Maybe
│ 9. Specific Product Need                │ Free text field
│ 10. Estimated Monthly Spend             │ $[Amount]
│ 11. Estimated Annual Spend              │ $[Amount]
│ 12. Budget Approval Authority           │ Contact or Manager name
└─────────────────────────────────────────┘
```

### Engagement Tracking

```
┌─────────────────────────────────────────┐
│ ENGAGEMENT METRICS                      │
├─────────────────────────────────────────┤
│ 1. First Contact Date                   │ When first reached out
│ 2. Last Contact Date                    │ Most recent interaction
│ 3. Days Since Last Contact              │ Auto-calc (today - last)
│ 4. Total Contacts Attempted             │ # of touches
│ 5. Last Communication Method            │ WhatsApp/Email/Call/LinkedIn
│ 6. Response Rate                        │ Yes/No/Maybe
│ 7. RFQs Received                        │ # of RFQs submitted
│ 8. Total RFQ Value                      │ Sum of all RFQs
│ 9. Deals Closed                         │ # of closed deals
│ 10. Total Revenue (All-Time)            │ $ generated from this contact
│ 11. Last RFQ Date                       │ When last RFQ received
│ 12. Follow-up Due Date                  │ Next planned contact
└─────────────────────────────────────────┘
```

### Relationship Depth

```
┌─────────────────────────────────────────┐
│ RELATIONSHIP INDICATORS                 │
├─────────────────────────────────────────┤
│ 1. Customer Segment                     │ Prospect/Active/VIP/Lost
│ 2. Relationship Strength                │ Cold/Warm/Hot/Strategic
│ 3. Decision-Maker Level                 │ User/Manager/Director/C-Level
│ 4. Competitor Relationships             │ Current primary vendor
│ 5. Contract Status                      │ Negotiating/Contracted/Reviewing
│ 6. Payment Terms                        │ Net 30/60/90, Cash
│ 7. Repeat Order Frequency               │ One-time/Monthly/Quarterly/Ad-hoc
│ 8. Cross-Sell Readiness                 │ Low/Medium/High
│ 9. Likelihood to Refer                  │ Low/Medium/High
│ 10. Account Health Score                │ Auto-calc (0-100)
└─────────────────────────────────────────┘
```

### Sales Process Fields

```
┌─────────────────────────────────────────┐
│ SALES PIPELINE STATUS                   │
├─────────────────────────────────────────┤
│ 1. Pipeline Stage                       │ Awareness/Interest/RFQ/Quote/Negotiation/Won
│ 2. Deal Value (Current)                 │ $ of active opportunity
│ 3. Probability of Close                 │ 0-100%
│ 4. Expected Close Date                  │ Forecasted close date
│ 5. Sales Owner                          │ Team member responsible
│ 6. Next Action                          │ Required next step
│ 7. Next Action Date                     │ When to take action
│ 8. Notes & History                      │ Call notes, objections, feedback
│ 9. Objections Raised                    │ Price, delivery, capability
│ 10. Competitive Threats                 │ Other vendors involved
└─────────────────────────────────────────┘
```

---

## 📋 GOOGLE SHEETS TEMPLATE (Copy-Paste Ready)

### Sheet 1: Master Contact List

| Contact ID | First Name | Last Name | Job Title | Company Name | Industry | Phone | Email | LinkedIn | Company Website | Address | Date Added | Source | Status | PPE Interest | IT Interest | Power Interest | Security Interest | Est Monthly Spend | Est Annual Spend | Last Contact | Days Since | Total RFQs | Total Revenue | Segment | Account Score |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| CRM001 | John | Smith | Procurement Manager | ExxonMobil Guyana | Oil & Gas | +592-6XX-XXXX | john@exxonmobil.gy | [URL] | www.exxonmobil.gy | Georgetown | 2026-01-15 | LinkedIn | Active | Yes | Maybe | Yes | Yes | $50,000 | $600,000 | 2026-05-03 | 5 | 3 | $245,000 | VIP | 92 |
| CRM002 | Sarah | Johnson | Safety Officer | Guyana Energy | Oil & Gas | +592-7XX-XXXX | sarah@guyanaenergy.gy | [URL] | www.guyanaenergy.gy | Berbice | 2026-02-01 | Referral | Prospect | Yes | No | Yes | Maybe | $25,000 | $300,000 | 2026-04-28 | 10 | 1 | $45,000 | Customer | 78 |

**Formula for Days Since Last Contact:**
```
=IF(C2="","",TODAY()-C2)
```

**Formula for Account Score (0-100):**
```
=MIN(100, (A2*10 + IF(B2>0,20,0) + IF(C2>0,30,0) + IF(TODAY()-D2<30,20,0)))
```

---

## 🎯 SEGMENTATION STRATEGY

### By Revenue Potential

```
TIER 1 (High Value)
├─ Monthly spend: $50,000+
├─ Annual commitment: $600,000+
├─ Companies: Oil & gas majors, large construction
├─ Action: Personal outreach, dedicated account manager
├─ Contact frequency: Weekly check-ins
└─ Expected RFQs/month: 3-5

TIER 2 (Medium Value)
├─ Monthly spend: $10,000-$50,000
├─ Annual commitment: $120,000-$600,000
├─ Companies: Mid-size contractors, government
├─ Action: Regular WhatsApp outreach
├─ Contact frequency: Bi-weekly
└─ Expected RFQs/month: 1-2

TIER 3 (Emerging Value)
├─ Monthly spend: $5,000-$10,000
├─ Annual commitment: $60,000-$120,000
├─ Companies: Small contractors, offices
├─ Action: Automated WhatsApp sequences
├─ Contact frequency: Monthly
└─ Expected RFQs/month: 0.5-1

TIER 4 (One-Time/Trial)
├─ Monthly spend: <$5,000
├─ Annual commitment: <$60,000
├─ Companies: Prospect pipeline
├─ Action: Bulk WhatsApp campaigns
├─ Contact frequency: As needed
└─ Expected RFQs/month: 0-0.5
```

### By Engagement Stage

```
AWARENESS (Cold prospects)
├─ Never contacted before
├─ Action: Introduction message (Module 2)
├─ Goal: Get response
├─ Timeline: 1-2 weeks
└─ Success = Interest expressed

INTEREST (Warm prospects)
├─ Responded positively
├─ Know what we do
├─ Action: Capability discussion
├─ Goal: Schedule call
├─ Timeline: 2-4 weeks
└─ Success = RFQ submitted

RFQ STAGE (Active deal)
├─ Submitted specific need
├─ Action: Fast quote generation
├─ Goal: Win deal
├─ Timeline: 1-2 weeks
└─ Success = Deal closed

CUSTOMER (Repeat buyer)
├─ Bought once or more
├─ Action: Cross-sell + retention
├─ Goal: Increase frequency + deal size
├─ Timeline: Ongoing
└─ Success = Repeat RFQ + referrals

VIP (Strategic partner)
├─ High value + long-term
├─ Action: Dedicated account manager
├─ Goal: Partnership + expansion
├─ Timeline: Ongoing strategic
└─ Success = Multi-million contracts
```

---

## 🔄 DAILY DATABASE MAINTENANCE

### Morning Routine (30 minutes)

```
☐ Review contacts with "Follow-up Due Date" = TODAY
☐ Check for any overnight RFQs or responses
☐ Update "Last Contact Date" for anyone you reached out to yesterday
☐ Identify 5-10 contacts for today's outreach
☐ Verify phone numbers and email addresses
☐ Flag any high-potential opportunities
```

### Weekly Routine (Friday, 1 hour)

```
☐ Update "Est Monthly Spend" based on recent RFQs
☐ Recalculate "Account Score" for all active prospects
☐ Identify customers eligible for cross-sell (Module 7)
☐ Archive lost opportunities
☐ Add new contacts from referrals/LinkedIn
☐ Segment contacts into outreach buckets for next week
☐ Generate weekly report (see dashboard below)
```

### Monthly Routine (1st of month, 2 hours)

```
☐ Calculate new "Total Revenue" for each contact
☐ Update "RFQs Received" count
☐ Identify top 10 customers by revenue
☐ Identify stalled prospects (>60 days since contact)
☐ Plan re-engagement for stalled prospects
☐ Analyze conversion rate by vertical
☐ Update sales forecast for next month
└─ Prepare monthly board report
```

---

## 📈 TRACKING & METRICS

### Key Metrics to Monitor

```
CONTACT HEALTH
├─ Total contacts in database: [#]
├─ Active prospects (Tier 1-2): [#]
├─ Customers (repeat buyers): [#]
├─ Contacts added this month: [#]
├─ Response rate to outreach: [%]
└─ Average time to respond: [days]

ENGAGEMENT
├─ Contacts touched this week: [#]
├─ Follow-ups due today: [#]
├─ Avg contact frequency: [# per person]
├─ Contacts by engagement stage: [breakdown]
├─ Contacts by vertical: [breakdown]
└─ Contacts by tier: [breakdown]

REVENUE
├─ Total customer lifetime value: $[Amount]
├─ Avg revenue per customer: $[Amount]
├─ Avg revenue per RFQ: $[Amount]
├─ Top 10 customers: [list]
├─ Customers added this month: [#]
└─ Repeat customer rate: [%]
```

---

## 🚀 DATABASE LAUNCH CHECKLIST

**Week 1: Setup**
```
☐ Create Google Sheet master list
☐ Design all fields (use template above)
☐ Create lookup dropdowns (Vertical, Source, Status)
☐ Add formulas for auto-calculations
☐ Set up conditional formatting (color-code by segment)
☐ Create filter views for different team members
```

**Week 2: Population**
```
☐ Import existing contacts (if any): ~50-100
☐ Add LinkedIn prospects: +100
☐ Add referral list: +50
☐ Add government/corporate directory: +100
☐ Research company info for each contact
☐ Validate phone numbers (format, test)
☐ Target: 300-500 contacts by end of week
```

**Week 3: Segmentation**
```
☐ Assign every contact to an industry vertical
☐ Assign product category interests
☐ Calculate account scores
☐ Tier customers (Tier 1-4)
☐ Assign sales owners
☐ Create outreach sequences
```

**Week 4: Launch**
```
☐ Begin daily outreach (20 per day)
☐ Log all responses in database
☐ Update engagement metrics daily
☐ Weekly reporting to leadership
☐ Adjust outreach based on response rates
```

---

## 📊 DATABASE REPORTING

### Weekly Dashboard

```
Monday Report (sent to team):

📊 CONTACT METRICS
├─ New contacts added: [#]
├─ Total active prospects: [#]
├─ Contacts touched this week: [#]
├─ Avg response rate: [%]
└─ Follow-ups scheduled: [#]

💰 REVENUE PIPELINE
├─ Open RFQs: [#]
├─ Est value of open deals: $[Amount]
├─ Closed deals this week: [#]
├─ Revenue this week: $[Amount]
└─ Pipeline coverage ratio: [#]

⭐ TOP PERFORMERS
├─ Most engaged contact: [Name]
├─ Highest value prospect: [Name]
├─ Most responsive vertical: [Vertical]
└─ Best performing sales owner: [Name]

🎯 THIS WEEK'S FOCUS
├─ Follow-up urgency: [#] contacts
├─ Cross-sell opportunities: [#]
├─ Tier 1 touchpoints: [#]
└─ New leads to warm: [#]
```

---

## 🔐 DATA SECURITY & PRIVACY

**Best Practices:**
- ☐ Keep database in Google Drive (encrypted, backed up)
- ☐ Limit access to core team members only
- ☐ Password-protect the sheet (Tools → Protect sheets)
- ☐ Archive old contacts (don't delete)
- ☐ Monthly backup export to CSV
- ☐ Comply with GDPR (if exporting/sharing)
- ☐ Get permission before sharing contact info

---

## ✅ NEXT STEPS

**Move to Module 2:** WhatsApp RFQ Capture System

This database becomes the target list for 20 daily WhatsApp outreaches that drive all revenue.

