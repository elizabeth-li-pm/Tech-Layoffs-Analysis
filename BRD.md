# Business Requirements Document (BRD)
## Tech Industry Layoffs Analysis (2020–2025)

**Author:** Elizabeth Li | MS Marketing Analytics, Simon Business School, University of Rochester
**Target Role:** Business Analyst

---

## 1. Project Background

Since 2022, tech industry layoffs have become a recurring topic across social 
media and news outlets. However, public discourse on this topic is largely 
driven by isolated headlines and anecdotal claims (e.g., "Company X just laid 
off employees again"), rather than systematic, comparative data.

This creates a structural problem for job seekers evaluating company stability: 
**information asymmetry**. A single headline does not indicate whether a layoff 
event is a one-time correction or part of a recurring pattern, nor how it 
compares to industry norms. Without quantification, job seekers cannot assess 
real risk — and without a comparative benchmark, they cannot judge whether a 
company's layoff history is abnormal or simply consistent with its industry 
or funding stage.

This information asymmetry has a direct, measurable cost: it increases the 
likelihood of job seekers either (a) accepting offers from companies with 
underlying instability that is not visible from a single news cycle, or 
(b) avoiding companies whose layoffs are statistically normal for their 
industry or growth stage, narrowing their opportunity set without justification.

This project uses a dataset of 2,412 reported tech layoff events (2020–2025, 
sourced from layoffs.fyi and Peerlist) to replace speculation with evidence — 
quantifying layoff patterns by company, industry, time period, and funding 
stage to give job seekers a comparative, data-backed basis for risk assessment.

## 2. Business Objective

Enable job seekers to answer three specific decision-relevant questions 
that headline-driven information cannot answer:

1. **Severity** — How large/frequent are this company's layoffs relative to others?
2. **Trend** — Is the risk increasing, decreasing, or stable over time?
3. **Benchmark** — Is this company's layoff pattern typical for its industry 
   and funding stage, or an outlier?

## 3. Primary Stakeholder

| Stakeholder | Core Decision | Current Pain Point |
|---|---|---|
| Job seekers (tech industry, primary focus) | Whether to apply to / accept an offer from a given company | Cannot quantify or benchmark layoff risk from fragmented news coverage |

*Secondary insights relevant to company HR teams and investors are noted 
where applicable, but this analysis is structured around the job seeker's 
decision-making process.*

## 4. Business Questions

1. Which companies and industries have experienced the most severe layoffs 
   (by volume and by percentage of workforce)?
2. How have layoff trends changed over 2020–2025? Has the rate accelerated 
   in the AI-driven period (2023–2025)?
3. What is the relationship between company size and layoff severity — are 
   larger companies more or less likely to lay off a high percentage of staff?
4. Does funding stage (e.g., Series A vs. IPO) correlate with layoff risk?
5. Does geographic location (region/country) influence layoff frequency or severity?

## 5. Scope & Data Limitations

This analysis is based on 2,412 reported tech layoff events (2020–2025). 
Several data characteristics affect how the business questions above 
should be interpreted:

**Company-level analysis (Question 1):** Of 1,713 unique companies, most 
appear only once or twice in the dataset. Company-level rankings (e.g., 
"most severe layoffs") are limited to companies with sufficient occurrences 
(top 15–20 by frequency, such as Google, Amazon, Microsoft) to avoid drawing 
conclusions from single, potentially anomalous events. Industry-level 
analysis uses the full dataset, as aggregation across companies reduces 
this noise.

**Time trend analysis (Question 2):** 2021 shows an anomalously low number 
of layoffs (14 events vs. 330–694 in other years). This is not a data quality 
issue — it reflects a real hiring boom driven by near-zero interest rates 
post-pandemic. The 2020–2025 period should be read as three distinct phases 
(pandemic shock → over-hiring correction → AI-driven restructuring) rather 
than one continuous trend.

**Company size analysis (Question 3):** `Company_Size_before/after_Layoffs` 
has 23–27% missing data, the highest of any field used in this analysis. 
Conclusions involving company size are based on a reduced sample and should 
be read with appropriate caution.

**Funding stage and amount analysis (Question 4):** The `Stage` field 
includes an "Unknown" category (14.8% of records), which is treated as 
missing data during analysis. `Money_Raised_in__mil` is right-skewed 
(mean: $683.8M vs. median: $161M) due to a small number of high-profile 
companies; median values are used instead of the mean to avoid distortion 
from outliers.

**Geographic analysis (Question 5):** The `Region` field is too coarse 
(67% classified as "other") to support meaningful comparison and is excluded; 
`Country` is used instead. However, USA accounts for 64.6% of all records — 
this likely reflects both genuine industry concentration and a data collection 
bias toward English-language media sources. Country-level comparisons should 
therefore be read as "US vs. other major reported tech hubs" rather than a 
complete global picture.

**General note:** All company name fields require standardization before 
analysis (e.g., "UK" and "United Kingdom" appear as separate values).