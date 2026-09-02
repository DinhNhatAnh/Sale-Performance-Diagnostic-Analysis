# Retail Pharmacy Sales Performance & Diagnostic Root Cause Analysis

> **Power BI \| Sales Analytics \| Diagnostic Analytics \| Retail
> Pharmacy**

## 1. Project Overview

This project analyzes **sales performance, profitability, discount
behavior, return leakage, and operational patterns** for a retail
pharmacy business using Power BI.

The dashboard is designed around two analytical questions:

-   **Page 1 --- Sales Performance Overview:** What happened to sales
    and profitability?
-   **Page 2 --- Diagnostic Root Cause Analysis:** Why did the
    performance change, and where are the main leakage risks?

The analysis focuses on December 2025 while benchmarking performance
against the FY2025 trend and average. The final dashboard also includes
a **Store & Product Drill-through** page for transaction-level
investigation.

### Dashboard Pages

  -----------------------------------------------------------------------
  Page                    Purpose                 Main Visuals
  ----------------------- ----------------------- -----------------------
  **01. Sales Performance Monitor revenue, margin KPI Cards, Revenue by
  Overview**              and transaction         Channel, Monthly Trend,
                          performance             Category Analysis,
                                                  Revenue Waterfall,
                                                  State Table

  **02. Diagnostic Root   Identify discount,      KPI Cards,
  Cause Analysis**        return and margin       Decomposition Tree,
                          leakage drivers         Heatmap,
                                                  Margin-at-Risk, Return
                                                  Pareto

  **03. Store & Product   Investigate             Transaction table with
  Drill-through**         transaction-level       store, channel, product
                          details                 and KPI fields
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 2. Business Context

The business needs to distinguish between a **real deterioration in
performance** and a **normal seasonal movement**.

December 2025 initially appears concerning because:

-   Gross Profit decreased **10.7% MoM**
-   Transactions decreased **10.3% MoM**
-   AOV decreased **3.9% MoM**

However, a MoM comparison alone can overstate the severity of the
situation. December Gross Profit was still **5.8% above the FY2025
monthly average**, while AOV was **5.6% above the FY2025 average**.

The key business question is therefore:

> **Is December a structural decline, or a seasonal normalization after
> the October--November peak?**

The analysis also investigates two important profitability risks:

1.  **Uncontrolled discount leakage**
2.  **Return-related revenue leakage**

The report concludes that December is better classified as **"Needs
Attention --- seasonal, not structural"**, while discount control
remains the highest-confidence revenue-recovery opportunity.

------------------------------------------------------------------------

## 3. Data Preparation

The data preparation process was performed in **Power BI**, starting
from the source Excel files and progressing through cleaning and data
modelling.

### 3.1 Load Excel Data

The raw transaction data was imported from Excel into Power BI.

The dataset contains transaction-level information including:

-   Transaction ID
-   Date
-   State
-   City
-   Channel
-   Category
-   Product Name
-   Quantity
-   Revenue
-   Gross Margin (%)
-   Discount (%)
-   Return (%)

### 3.2 Data Cleaning

The Power Query layer was used to prepare the dataset for analysis.

Key activities included:

-   Reviewing column names and data types
-   Converting date and numeric fields into appropriate formats
-   Checking missing and inconsistent values
-   Standardizing categorical fields
-   Validating transaction-level records
-   Preparing time-related fields for monthly and day/hour analysis
-   Creating fields required for discount, return and margin analysis

The objective was to ensure that the dataset was sufficiently clean and
consistent before building analytical measures and visuals.

### 3.3 Data Modelling in Power BI

After cleaning, the data was structured for dashboard analysis.

The model supports analysis across:

**Time → Geography → Channel → Category → Product → Transaction**

Key analytical measures include:

-   Gross Profit
-   Gross Margin %
-   COGS
-   Revenue
-   Discount Amount
-   Discount Rate
-   AOV
-   Transactions
-   Return Amount / Return Leakage
-   Return Transaction %
-   High-Discount Transactions
-   Margin at Risk

The dashboard also uses drill-through functionality to move from
aggregated performance indicators to transaction-level records.

------------------------------------------------------------------------

## 4. Exploratory Risk Analysis

The exploratory analysis was structured into four areas.

### 4.1 Sales & Profitability

The first stage evaluates:

-   Revenue trend
-   Gross Profit
-   Gross Margin %
-   COGS
-   AOV
-   Transaction volume
-   Channel contribution
-   Category performance

The monthly trend shows a clear seasonal pattern: revenue generally runs
lower during **Jan--Jun**, increases through Q3, reaches a peak around
**Oct--Nov**, and then normalizes in December.

### 4.2 Discount Risk

Discount behavior was investigated using:

-   Discount Rate
-   Discount Amount
-   High-Discount Transactions
-   Decomposition Tree

The Decomposition Tree enables the discount amount to be drilled down
by:

**Channel → Payment Method → Campaign → State**

This revealed a recurring concentration of discounts in the Walk-in
channel, particularly where discounts were associated with **"No
Campaign"**.

### 4.3 Return Risk

Return risk was evaluated using:

-   Return Leakage
-   Return Transactions
-   Return Transaction %
-   Pareto analysis of Return Amount
-   Return-related transaction details

December Return Leakage was **890.58**, down **62.0% MoM**, but this
improvement should be interpreted cautiously because it was based on
only **7 return transactions**.

### 4.4 Operational Timing Risk

A **Day-of-Week × Hour heatmap** was used to identify periods with
concentrated activity.

The analysis highlights the evening period, particularly around
**18:00--21:00**, as a peak operating window that should be considered
in staffing and inventory planning.

------------------------------------------------------------------------

# 5. Key Business Findings

## 5.1 Insight #1 --- Lower the December MoM Alert Level

### Finding

December shows a noticeable MoM decline:

-   **Gross Profit:** 26.53K, **-10.7% MoM**
-   **Transactions:** 262, **-10.3% MoM**
-   **AOV:** 358.68, **-3.9% MoM**

At first glance, this could trigger a critical-performance alert.

However, benchmarking against FY2025 changes the interpretation:

-   Gross Profit: **+5.8% vs FY2025 monthly average**
-   AOV: **+5.6% vs FY2025 monthly average**
-   Gross Margin: **28.2%, +0.9pp vs FY2025 average**

### Business Interpretation

The December decline is more consistent with **seasonal normalization
after the October--November peak** than with a structural deterioration.

Therefore:

> **December should be classified as Low--Medium severity / Watch rather
> than Critical.**

The pattern still needs to be monitored through Q1 2026 to confirm
whether the seasonal behavior repeats.

### Business implication

Avoid overreacting to a single MoM decline. Performance monitoring
should combine:

**MoM movement + FY average benchmark + seasonal pattern**

------------------------------------------------------------------------

## 5.2 Insight #2 --- Jan--Jun Is Typically Lower Than Oct--Nov → Prepare for Q1 2026

### Finding

The FY2025 trend shows a recurring seasonal shape:

-   **Jan--Jun:** approximately 60--90K/month
-   **Oct--Nov:** approximately 100--120K/month

This indicates that the Q1 2026 revenue base may naturally be lower than
the Q4 2025 peak.

### Business Interpretation

A lower Q1 revenue number should not automatically be interpreted as a
business problem.

If the FY2025 seasonal pattern repeats, Q1 2026 could normalize toward
approximately **65--85K/month**.

### Business implication

The business should **prepare for the seasonal dip before it happens**,
rather than waiting for the KPI to deteriorate.

Priority should be given to:

-   Front-loaded commercial actions in January
-   Cross-selling higher-value categories
-   Discount control
-   Channel optimization
-   Staffing and inventory planning

------------------------------------------------------------------------

## 5.3 Insight #3 --- Quick Commerce Overtook Home Delivery

### Finding

December channel revenue:

  Channel             Revenue
  ----------------- ---------
  Walk-in             **48K**
  App                 **23K**
  Quick Commerce      **13K**
  Home Delivery        **6K**
  Telemedicine Rx      **4K**

Quick Commerce moved from **FY2025 rank #4 to December rank #3**,
overtaking Home Delivery.

### Business Interpretation

This is an interesting emerging signal, but it is **not yet sufficient
to confirm a structural channel shift** because December represents only
one observation.

### Business implication

The business should test whether Quick Commerce can become a stronger
growth channel through:

-   Targeted marketing
-   Selected product availability
-   Promotion experiments
-   Monitoring repeat purchase behavior
-   Comparing AOV and margin against Home Delivery

> **Action:** Test increased Quick Commerce marketing spend and validate
> whether the channel remains ahead of Home Delivery in subsequent
> months.

------------------------------------------------------------------------

## 5.4 Insight #4 --- Discount Leakage: Walk-in / "No Campaign"

### Finding

December total Discount Amount was approximately **18.55K**.

The decomposition shows:

-   **Walk-in:** 8.23K, approximately **44.4%** of total discount
-   **UPI:** 3.61K
-   **No Campaign:** 1.61K within the drilled Walk-in + UPI path

The same pattern was observed in the FY2025 analysis, where Walk-in
represented approximately **45.2%** of discount.

### Business Interpretation

The repeated concentration of discounts in Walk-in transactions,
combined with discounts tagged **"No Campaign"**, indicates a likely
source of **uncontrolled discretionary discounting**.

Because the pattern is visible across two reporting periods, confidence
in this root cause is high.

### Business implication

This is the **highest-priority revenue-recovery lever** identified in
the analysis.

Recommended control:

> Require approval or predefined rules for non-campaign discounts at the
> Walk-in channel.

The report estimates a potential recovery of approximately
**3--5K/month** in realized revenue.

------------------------------------------------------------------------

## 5.5 Insight #5 --- Peak Hour: 18:00--21:00

### Finding

The Day × Hour heatmap shows concentrated activity during the evening
period, particularly around:

**18:00 → 19:00 → 20:00 → 21:00**

### Business Interpretation

This period represents a critical operating window where insufficient
staffing or stock availability could translate into:

-   Lost sales
-   Longer customer waiting time
-   Lower service quality
-   Operational bottlenecks

### Business implication

Store operations should align staffing and inventory availability with
the evening demand peak.

> **Action:** Reinforce staffing and stock coverage during the
> 18:00--21:00 window.

------------------------------------------------------------------------

# 6. Recommendations

The recommendations are prioritized by **business impact, confidence and
implementation urgency**.

  -----------------------------------------------------------------------------------------
  Priority       Recommendation              Expected Impact  Owner          Timing
  -------------- --------------------------- ---------------- -------------- --------------
  🔴 High        Implement approval controls Recover          Store          Jan 2026
                 for non-campaign Walk-in    \~3--5K/month    Operations     
                 discounts                                    Manager        

  🔴 High        Maintain                    Sustain          Pharmacy / QC  Ongoing
                 prescription-verification   return-leakage   Lead           
                 controls for chronic        reduction                       
                 refills                                                     

  🟠 Medium      Prepare staffing and        Reduce lost      Store          Jan 2026
                 inventory for the           sales during     Operations     
                 18:00--21:00 peak           peak demand      Manager        

  🟠 Medium      Bundle Wellness & FMCG with Potential +3--5% Category       Jan--Feb 2026
                 prescription orders         AOV              Manager        

  🟠 Medium      Test increased Quick        Validate and     Digital        Jan 2026
                 Commerce marketing spend    scale emerging   Channel Lead   
                                             channel                         
  -----------------------------------------------------------------------------------------

### Recommended Management Priorities

#### 1. Control discount leakage first

The Walk-in / No Campaign pattern is the strongest and most repeatable
root cause identified.

#### 2. Prepare for Q1 seasonality

Do not wait for revenue to fall in Q1 2026. Front-load commercial
actions in January.

#### 3. Validate Quick Commerce growth

Quick Commerce overtaking Home Delivery is promising, but should be
treated as a **hypothesis to validate**, not a confirmed trend.

#### 4. Protect peak-hour sales

Ensure adequate staffing and stock coverage during the **18:00--21:00**
demand window.

------------------------------------------------------------------------

## Analytical Framework

The project follows a practical analytics flow:

``` text
Raw Excel Data
      ↓
Power Query
      ↓
Data Cleaning & Transformation
      ↓
Power BI Data Model
      ↓
KPI Monitoring
      ↓
Exploratory Analysis
      ↓
Segment Analysis
      ↓
Diagnostic Root Cause Analysis
      ↓
Business Insights
      ↓
Recommendations
```

------------------------------------------------------------------------

## Tools & Technologies

-   **Microsoft Excel** --- Source data
-   **Power Query** --- Data cleaning & transformation
-   **Power BI** --- Data modelling, DAX measures, visualization and
    dashboard
-   **Power BI Drill-through** --- Transaction-level investigation

------------------------------------------------------------------------

## Key Takeaways

This project demonstrates how a sales dashboard can move beyond
descriptive reporting toward **diagnostic business analysis**.

The most important analytical lessons are:

1.  **Do not interpret MoM movement without seasonal context.**
2.  **Benchmark current performance against a meaningful historical
    baseline.**
3.  **Use decomposition analysis to move from KPI movement to root
    cause.**
4.  **Prioritize recurring leakage patterns over isolated anomalies.**
5.  **Translate dashboard findings into specific operational actions.**

> **The key message:** December's headline decline is primarily a
> seasonal normalization signal, while **uncontrolled Walk-in discounts
> remain the clearest actionable source of revenue leakage.**

------------------------------------------------------------------------

## Dashboard Preview

### Sales Performance Overview

![Sales Performance Overview](assets/dashboard_overview.png)

### Diagnostic Root Cause Analysis

![Diagnostic Root Cause Analysis](assets/dashboard_diagnostic.png)

### Store & Product Drill-through

![Store & Product Drill-through](assets/dashboard_drillthrough.png)

------------------------------------------------------------------------

## Data Limitations

Several conclusions should be interpreted with the following
limitations:

-   December Return Leakage is based on only **7 return transactions**,
    so the improvement may not represent a sustained structural change.
-   The Q1 2026 outlook is a **directional seasonal estimate**, not a
    statistical forecasting model.
-   Some state-level data visible in the dashboard is only partially
    displayed.
-   Category rank movement is based partly on visual comparison where
    exact historical chart labels were unavailable.
-   KPI classifications and alert thresholds are analyst working
    assumptions rather than formal company-wide KPI definitions.
-   Net Revenue and some MoM comparisons are derived metrics and should
    be validated against the source system before being used for
    financial reporting.

------------------------------------------------------------------------

## Project Objective

**Turn sales data into actionable business decisions by connecting
performance monitoring with diagnostic root-cause analysis.**
