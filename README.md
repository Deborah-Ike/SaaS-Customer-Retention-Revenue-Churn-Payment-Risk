# SaaS-Customer-Retention-Revenue-Churn-Payment-Risk

## Project Overview

**Role:** Data Analyst  
**Tools:** SQL Server, T-SQL, Power BI  
**Industry:** B2B SaaS  
**Dataset period:** January 2023 to December 2025

### Business Problem

A SaaS business needs to understand how well it retains customers, where its recurring revenue comes from, and whether customer cancellations or payment problems pose financial risks.

The purpose of this project was to analyze customer subscriptions, recurring revenue, historical cancellations, cohort retention, and payment activity to identify business areas that may require management attention.

### Business Questions

1. Who are the customers, and which groups generate the most recurring revenue?
2. Which customer groups have the highest historical cancellation rates?
3. How much recurring revenue has been lost through cancellations?
4. Are payment failures associated with customer cancellations?
5. How does customer retention vary across signup cohorts?

## Analysis and Key Findings

### 1. Customer Profile and Revenue Distribution

The dataset contains 5,000 subscriptions, of which 4,035 are active. Current monthly recurring revenue (MRR) is $1,387,441.

SMB customers represent 3,522 subscriptions, approximately 70.4% of the customer base. However, the mid-market segment generates the highest MRR among customer segments, at $591,734.

The Enterprise plan generates the highest MRR among plans, at $558,069, despite having only 283 subscriptions.

**Business implication:** Customer volume and revenue contribution differ. Retention decisions should consider the financial value of customer groups, not just the number of customers.

### 2. Customer Churn

There are 965 cancelled subscriptions out of 5,000, giving a historical cancellation rate of 19.3%.

The Enterprise plan has the highest cancellation rate among plans, at 21.2%. By acquisition channel, outbound has a 21.53% cancellation rate and organic has a 21.29% rate. Partner acquisition has the lowest rate, at 16.80%.

These are historical cancellation rates across the observed subscriptions, not monthly or annual churn rates.

**Business implication:** Outbound and organic acquisition, along with Enterprise plan cancellations, are reasonable areas for further investigation. The analysis does not establish why these groups have different rates.

### 3. Recurring Revenue and Financial Risk

Total MRR associated with cancelled subscriptions is $342,673.

The mid-market segment has the highest cancelled MRR among segments, at $137,271. The Enterprise plan has the highest cancelled MRR among plans, at $150,040.

Current MRR peaked at $1,417,797 in October 2025 and fell to $1,387,441 by December 2025, a decline of $30,356.

**Business implication:** Revenue retention efforts should account for the value of lost recurring revenue. The decline in MRR during the final two months of 2025 warrants further review to determine which subscription changes contributed to it.

### 4. Payment Failures and Recovery

The dataset contains 87,287 payment attempts, of which 7,186 failed. The payment attempt failure rate is approximately 8.23%.

Of the 7,186 invoices with at least one failed attempt, 6,722 later had a successful payment attempt, giving a recovery rate of approximately 93.54%.

The historical cancellation rate was 17.01% among subscriptions with a recorded payment problem and 24.67% among those without one. The data therefore does not show a higher historical cancellation rate for subscriptions with payment problems.

**Business implication:** Payment failures should be monitored alongside recovery outcomes. Further analysis should focus on unresolved failures and the timing of payment problems relative to cancellation, rather than assuming payment failures cause churn.

### 5. Cohort Retention

Customer cohorts retain at least 98% of subscriptions through month 3. By month 12, retention ranges from 81.0% to 91.5% across cohorts with sufficient observation time.

The January 2024 cohort has the highest observed 12-month retention at 91.5%, while the August 2023 cohort has the lowest at 81.0%.

**Business implication:** Retention differences become more visible over longer periods. Comparing onboarding and customer engagement practices across cohorts may help identify factors associated with stronger long-term retention. The current analysis identifies differences but does not explain their causes.

## Recommendations

1. **Investigate the recent MRR decline.** Identify the subscription cancellations and revenue changes that contributed to the decline from October to December 2025.
2. **Prioritize revenue-aware retention analysis.** Review cancellations involving the Enterprise plan and mid-market customers because these groups account for substantial cancelled MRR.
3. **Review acquisition channel performance.** Investigate why outbound and organic cohorts have higher historical cancellation rates than partner-acquired customers.
4. **Monitor payment recovery.** Track failed attempts, successful recoveries, and invoices that remain unpaid.
5. **Compare long-term retention across cohorts.** Examine differences in customer onboarding and engagement while accounting for cohort age and the available observation period.

## Tools and Technical Approach

SQL Server and T-SQL were used to validate data types, join relational tables, aggregate subscription and invoice metrics, calculate cancellation rates, analyze MRR, measure payment failure and recovery, and compare retention across signup cohorts.

The analysis was organized into separate SQL files for data validation, customer profiling, churn, revenue retention, cohort analysis, payment risk, and business findings.

Power BI will be used to present the verified metrics in an interactive dashboard for business stakeholders.

## Conclusion

The analysis shows that the SaaS business has a substantial active subscription base and $1.39 million in current MRR, while historical cancellations account for $342,673 in cancelled MRR. Cancellation rates and cancelled revenue vary across plans, customer segments, and acquisition channels. Payment failures are frequent enough to monitor, although most invoices with failed attempts eventually show a successful attempt in the dataset.

The recommended next step is to investigate the recent MRR decline and prioritize retention analysis using both cancellation rates and financial impact. These findings provide a basis for further investigation, rather than proof of the causes of churn.
