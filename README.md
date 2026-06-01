# Banking Risk Analysis (Power BI Report)

An interactive Power BI report that analyses customer loan and deposit behaviour across a banking client base. Built on two data sources, the report helps banking teams understand credit exposure, deposit composition, and customer demographics- broken down by income band, nationality, occupation, and banking relationship.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [File Structure](#file-structure)
3. [Data Sources](#data-sources)
4. [Report Pages](#report-pages)
   - [Home Page](#home-page)
   - [Loan Analysis](#loan-analysis)
   - [Deposit Analysis](#deposit-analysis)
   - [Summary](#summary)
5. [Business Impact & Insights](#business-impact--insights)
6. [Preview of the Dashboard](#preview-of-the-dashboard)

---

## Project Overview

| Attribute | Detail |
|-----------|--------|
| Tool | Microsoft Power BI Desktop |
| File format | `.pbix` (Power BI Report with embedded data) |
| PBI version | 1.28 |
| Report pages | 4 - Home Page, Loan Analysis, Deposit Analysis, Summary |

The report is designed to answer questions such as:
- How much total loan and deposit value does the bank hold?
- Which income bands, nationalities, and occupations carry the most loan or deposit exposure?
- How does business lending compare to personal bank loans?
- What is the breakdown of savings accounts, chequing accounts, and credit card balances?
- How many clients are on the books, and how long have they been engaged?

---

## File Structure

```
Banking_Risk_Analysis.pbix
├── Version                          # PBI version (1.28)
├── [Content_Types].xml
├── DiagramLayout                    # Model view layout
├── DataModel                        # Compressed tabular data model
├── Settings
├── Metadata
├── SecurityBindings
└── Report/
    ├── Layout                       

```

---

## Data Sources

The report uses two tables loaded into the data model.

### banking-clients

Contains client-level banking engagement data.

| Column | Description |
|--------|-------------|
| `Total Clients` | Count of unique banking clients |
| `Total Fees` | Total fees charged to clients |
| `Foreign Currency Amount` | Value held in foreign currency accounts |
| `Engagement Length` | How long the client has been with the bank |

### customer

Contains detailed financial product and demographic data per customer.

| Column | Description |
|--------|-------------|
| `BRId` | Banking Relation IDs (Retail, Institutional, Private Bank, Commercial) |
| `GenderId` | Customer gender |
| `Income Band` | Income tier (e.g. low, medium, high) |
| `Nationality` | Customer nationality |
| `Occupation` | Customer occupation category |
| `Year of Joining` | Year the customer joined the bank |
| `Total Loan` | Total loan value held by the customer |
| `Total Deposit` | Total deposit value held by the customer |
| `Bank Loans` | Standard bank loan balance |
| `Business Lending` | Business lending balance |
| `Credit Card Balance` | Outstanding credit card balance |
| `Amount of Credit Cards` | Number of credit cards held |
| `Bank Deposits` | Bank deposit balance |
| `Saving Accounts` | Savings account balance |
| `Chequing Accounts` | Chequing account balance |

---

## Report Pages

### Home Page

**Purpose:** Executive summary landing page, a single view of the bank's total financial position and client base.

**Visuals:**
- 6 **KPI Cards**: Total Loan, Total Deposit, Business Lending, Savings Accounts, Checking Accounts, Total Clients
- 2 **Slicers**: Gender and Year of Joining- for filtering the entire report
- 6 **Navigation buttons**: Quick links to the other report pages

**Key question answered:** What is the overall size of the loan book, deposit base, and client count, and how does it look for a selected gender or year?

---

### Loan Analysis

**Purpose:** Deep dive into loan exposure- how loans are distributed across banking relationships, nationalities, and occupations.

**Visuals:**
- 4 **KPI Cards**: Total Loan, Bank Loans, Business Lending, Credit Card Balance
- **Donut Chart**: Loan distribution by Income Band
- **Clustered Column Chart**: Bank Loans by BRId (banking relationship ID)
- **Clustered Column Chart**: Bank Loans by Nationality
- **Clustered Column Chart**: Bank Loans by Occupation
- 3 **Slicers**: Year of Joining, BRId, Gender- for cross-filtering

**Key question answered:** Which banking relationships, nationalities, and occupations hold the largest share of the loan book? Where is credit risk most concentrated?

---

### Deposit Analysis

**Purpose:** Mirror of the Loan Analysis page, focused on deposit behaviour.

**Visuals:**
- 4 **KPI Cards**: Total Deposit, Bank Deposits, Savings Accounts, Chequing Accounts
- **Donut Chart**: Deposit distribution by Income Band
- **Clustered Column Chart**: Bank Deposits by BRId (banking relationship)
- **Clustered Column Chart**: Bank Deposits by Nationality
- **Clustered Column Chart**: Bank Deposits by Occupation
- 3 **Slicers**: Year of Joining, BRId, Gender

**Key question answered:** Which customer segments are contributing most to deposit growth? Is deposit concentration aligned or misaligned with loan concentration?

---

### Summary

**Purpose:** Consolidated view of all key metrics in one place, a single-page snapshot for senior stakeholders.

**Visuals:**
- 12 **KPI Cards** covering every major metric: Total Clients, Total Loan, Bank Loans, Business Lending, Total Deposit, Total Fees, Bank Deposits, Chequing Accounts, Amount of Credit Cards, Saving Accounts, Foreign Currency Amount, Engagement Length
- 4 **Slicers**: BRId, Gender, Year of Joining, and one additional dimension
- **Navigation buttons** to move between pages

**Key question answered:** What does the full banking picture look like for any selected customer segment, banking relationship, or time period?

---

## Business Impact & Insights

Here are five key things this report tells you, and what to do about them.

---

### 1. Loan concentration is a hidden risk

If a large chunk of the total loan book is held by one or two nationalities, or occupation groups, the bank is more exposed than it looks on the surface. A single economic shock to that group could cause a spike in defaults. **What to do:** Use the Loan Analysis page to check whether loans are bunched in one area. If they're bunched, that's a conversation to have with the credit risk team.

---

### 2. Credit card balances signal financial stress

High credit card balances relative to bank loans or deposits, especially in lower-income bands, are an early warning sign. Customers carrying heavy credit card debt alongside loans are more likely to default. **What to do:** Filter the Home Page by income band and watch how credit card balance compares to total loan. Any segment where credit card balance is disproportionately high deserves closer monitoring.

---

### 3. Deposits and loans should balance out. If they don't, that's a problem

The bank funds loans with deposits. If total loans are growing faster than total deposits, the bank may be over-extending. The Summary page puts both numbers side by side in one glance. **What to do:** Track this ratio over time using the Year of Joining slicer. A widening gap between loan and deposit growth is a flag for the treasury team.

---

### 4. Some customer segments are underserved

The Deposit Analysis page breaks down savings accounts, chequing accounts, and bank deposits by occupation and nationality. If certain groups have high deposits but low loan uptake, those customers aren't being offered the right products. **What to do:** Cross-reference high-deposit, low-loan segments on both analysis pages. These are prime candidates for targeted lending product campaigns.

---

### 5. Engagement length tells you who to retain

The `Engagement Length` metric on the Summary page shows how long clients have been with the bank. Long-tenured customers tend to hold more products and are cheaper to serve. If average engagement length is short, churn may be a bigger issue than new client acquisition. **What to do:** Segment by Year of Joining and compare engagement length; if newer cohorts have shorter engagement, the onboarding and retention experience may need attention.

---

## Preview of the Dashboard

[Click here to view the dashboard PDF](https://github.com/basvi-chunara/Banking-Risk-Analysis/blob/main/Banking%20Risk%20Analysis.pdf)

![Dashboard preview](https://github.com/basvi-chunara/Banking-Risk-Analysis/blob/main/Dashboard%20preview.png)
