# Retail Pharmacy Sales Performance & Diagnostic Root Cause Analysis

> **Power BI \| Sales Analytics \| Diagnostic Analytics \| Retail
> Pharmacy**

## 1. Project Overview

This project analyzes **sales performance, profitability, discount behavior, return leakage, and operational patterns** for a retail pharmacy business using Power BI.

The dashboard is designed around two analytical questions:

-   **Page 1 --- Sales Performance Overview:** What happened to sales
    and profitability?
-   **Page 2 --- Diagnostic Root Cause Analysis:** Why did the
    performance change, and where are the main leakage risks?
-   **Page 3 --- Store & Product Drill-through:** How we could investigate transaction-level?

## 2. Business Context

The management team wants to gain a clear view of the company’s sales performance in the previous month, with a focus on revenue, profitability, transaction volume, discounts, returns, and channel performance. The analysis aims to identify the key factors driving performance changes and highlight potential areas of revenue or margin leakage. Based on these findings, the company can develop practical improvement plans for the next three months, focusing on optimizing sales channels, controlling discount leakage, improving operational performance during peak hours, and strengthening overall profitability.

------------------------------------------------------------------------

## 3. Data Preparation

The data preparation process was performed in **Power BI**, starting from the source Excel files and progressing through cleaning and data modelling.

### 3.1 Load Excel Data

The raw transaction data was imported from Excel into Power BI.

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

The objective was to ensure that the dataset was sufficiently clean and consistent before building analytical measures and visuals.

### 3.3 Data Modelling in Power BI

After cleaning, the data was structured for dashboard analysis.

<img src="Pictures\Loan_grade.jpg" width="1000">

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

The dashboard also uses drill-through functionality to move from aggregated performance indicators to transaction-level records.

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

The monthly trend shows a clear seasonal pattern: revenue generally runs lower during **Jan--Jun**, increases through Q3, reaches a peak around **Oct--Nov**, and then normalizes in December.

### 4.2 Discount Risk

Discount behavior was investigated using:

-   Discount Rate
-   Discount Amount
-   High-Discount Transactions
-   Decomposition Tree

The Decomposition Tree enables the discount amount to be drilled down
by:

**Channel → Payment Method → Campaign → State**

This revealed a recurring concentration of discounts in the Walk-in channel, particularly where discounts were associated with **"No Campaign"**.

### 4.3 Return Risk

Return risk was evaluated using:

-   Return Leakage
-   Return Transactions
-   Return Transaction %
-   Pareto analysis of Return Amount
-   Return-related transaction details

December Return Leakage was **890.58**, down **62.0% MoM**, but this improvement should be interpreted cautiously because it was based on only **7 return transactions**.

### 4.4 Operational Timing Risk

A **Day-of-Week × Hour heatmap** was used to identify periods with concentrated activity.

The analysis highlights the evening period, particularly around **18:00--21:00**, as a peak operating window that should be considered in staffing and inventory planning.

------------------------------------------------------------------------

# 5. Key Business Findings

## 5.1 Jan--Jun Is Typically Lower Than Oct--Nov → Prepare for Q1 2026

### Finding

The FY2025 trend shows a recurring seasonal shape:

-   **Jan--Jun:** approximately 60--90K/month
-   **Oct--Nov:** approximately 100--120K/month

This indicates that the Q1 2026 revenue base may naturally be lower than the Q4 2025 peak.

### Business Interpretation

A lower Q1 revenue number should not automatically be interpreted as a business problem.

If the FY2025 seasonal pattern repeats, Q1 2026 could normalize toward approximately **65--85K/month**.

### Business implication

The business should **prepare for the seasonal dip before it happens**, rather than waiting for the KPI to deteriorate.

Priority should be given to:

-   Front-loaded commercial actions in January
-   Cross-selling higher-value categories
-   Discount control
-   Channel optimization
-   Staffing and inventory planning

------------------------------------------------------------------------

## 5.2 Sales Performance Is Highly Concentrated in Walk-in Channel



### Finding

December channel revenue:

  - Walk-in             **48K**
  
  - App                 **23K**
  
  - Quick Commerce      **13K**
  
  - Home Delivery        **6K**
  
  - Telemedicine Rx      **4K**

### Business Interpretation

Sales performance is highly concentrated in the **Walk-in channel**, generating approximately **48K revenue**, more than twice the contribution of the App channel (23K) and significantly higher than Quick Commerce (13K), Home Delivery (6K), and Telemedicine Rx (4K).

This indicates that the company's sales performance is still strongly dependent on **traditional in-store transactions**, while digital and remote channels contribute a smaller share of total revenue

### Business implication

The current channel structure creates both an opportunity and a risk:

- Walk-in: Main revenue driver, but over-reliance may limit scalability.
- App: Second-largest channel, indicating potential for further digital growth.
- Quick Commerce: Meaningful contribution and stronger than Home Delivery.
- Home Delivery & Telemedicine Rx: Smaller revenue contribution, suggesting potential areas for optimization.

Therefore, management should maintain Walk-in as the core revenue channel while gradually strengthening digital channels, particularly App and Quick Commerce, to diversify the revenue mix and reduce dependence on physical-store traffic.

> **Action:** Protect the core, diversify the growth.
Maintain Walk-in performance while investing selectively in App and Quick Commerce through targeted promotions, customer retention initiatives, and digital-channel adoption.

------------------------------------------------------------------------

## 5.3 Discount Leakage Is Concentrated in Walk-in Transactions

### Finding

The decomposition shows:

-   **Walk-in:** 8.23K, approximately **44.4%** of total discount
-   **UPI:** 3.61K
-   **No Campaign:** 1.61K within the drilled Walk-in + UPI path

### Business Interpretation

Discount leakage is primarily concentrated in the Walk-in channel, which accounts for approximately **8.23K in discount amount**, making it the largest contributor among the channels analyzed. The decomposition analysis also shows that transactions without a campaign contributed approximately **1.61K** in discount amount

This suggests that a significant portion of discount spending is associated with the **Walk-in channel and transactions without a clearly defined campaign**, highlighting an opportunity to review how discounts are applied at the store level

### Business implication

Rather than reducing discounts across all channels, management should focus on **controlling discount allocation where the leakage is concentrated** while maintaining promotions that effectively support sales.

Recommended Action:

> Review Walk-in discount policies, particularly transactions without campaigns, and introduce clearer discount rules, approval thresholds, and campaign tracking to improve discount efficiency.

------------------------------------------------------------------------

## 5.4 Sales Activity Peaks During 18:00–21:00

### Finding

The Day × Hour heatmap shows concentrated activity during the evening period, particularly around:

**18:00 → 19:00 → 20:00 → 21:00**

### Business Interpretation

The hourly heatmap shows a clear concentration of sales activity during the **18:00–21:00 period**, indicating that the evening is a key operating window for the business.

This pattern suggests that customer demand is particularly concentrated during the evening, making this period important for both **sales execution and operational capacity planning**.

### Business implication

The company has an opportunity to better align resources with customer demand. Insufficient staffing or operational capacity during these peak hours could negatively affect the customer experience and sales execution.

> **Action:** Prioritize staffing, inventory availability, and promotional activities during **18:00–21:00**, while monitoring transaction volume and operational performance to determine whether additional resources are justified.

------------------------------------------------------------------------

# 6. Recommendations

The recommendations are prioritized by **business impact, confidence and implementation urgency**.

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

The Walk-in / No Campaign pattern is the strongest and most repeatable root cause identified.

#### 2. Prepare for Q1 seasonality

Do not wait for revenue to fall in Q1 2026. Front-load commercial actions in January.

#### 3. Diversify Channel Growth Beyond Walk-in

Maintain Walk-in as the core sales channel while gradually increasing the contribution of digital channels, particularly App and Quick Commerce, to reduce channel dependency and build a more balanced revenue mix.

#### 4. Optimize Peak-hour Operations

Align staffing, inventory availability, and promotional activities with the **18:00–21:00** demand peak.

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
