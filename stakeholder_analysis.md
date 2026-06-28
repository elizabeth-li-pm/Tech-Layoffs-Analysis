# Stakeholder Analysis
## Tech Industry Layoffs Analysis

## 1. Overview

This document expands on the stakeholder identified in the BRD (Section 3) 
by mapping out their decision journey in detail — what they need to know, 
at what stage of their job search, and how this shapes the design of the 
final analysis and dashboard.

## 2. Stakeholder Profile

**Primary stakeholder:** Job seekers targeting roles in the tech industry.

**Current situation:** They rely on fragmented, headline-driven information 
about layoffs (social media posts, news articles about individual companies) 
with no systematic way to compare risk across companies, industries, or 
funding stages.

**Core need:** A data-backed way to assess employer stability before 
investing time in an application or accepting an offer.

## 3. Decision Journey — Two Stages

Job seekers engage with layoff data at two distinct points in their job 
search, each with different information needs.

### Stage 1: Screening
**When it happens:** Before deciding which companies to apply to.

**What they want to know:** Broad, comparative trends — which industries, 
company sizes, or funding stages carry higher layoff risk in general — to 
help narrow down where to focus their job search.

**Example question:** "Should I prioritize applying to large, Post-IPO 
companies or early-stage startups right now?"

### Stage 2: Decision
**When it happens:** After receiving an interview invitation or job offer 
from a specific company.

**What they want to know:** That specific company's layoff history — how 
often, how severe, and whether the trend is worsening — to assess whether 
accepting the offer carries elevated risk.

**Example question:** "Company X just offered me a role. Have they laid 
off staff before? Is this a one-time event or a pattern?"

## 4. Information Needs by Stage

| Stage | Level of Detail | Data Needed |
|---|---|---|
| Screening | Macro / aggregated | Layoff trends by industry, funding stage, company size, region, and year |
| Decision | Micro / company-specific | Full layoff history for a single named company (frequency, size, dates, % of workforce) |

## 5. Design Implications

Because the two stages require different levels of detail, the final 
dashboard must support both:

- **An overview view** — aggregated charts (by industry, funding stage, 
  region, time) for the screening stage.
- **A company lookup view** — the ability to filter/search for a specific 
  company and see its individual layoff history for the decision stage.

This dual structure ensures the analysis is useful both for narrowing down 
a job search broadly and for validating a specific opportunity.