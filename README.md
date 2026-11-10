# Loan Portfolio Analytics

An end-to-end banking data analytics project using **SQL** and **Excel** to review loan disbursement, customer borrowing, repayment collections, branch performance and credit risk.

> **Transparency note:** The dataset is synthetic. It is not real banking data and does not describe any real bank, customer or transaction. It was created to demonstrate data analytics skills.

📄 **Full details:** see the [full project report (Word document)](Loan_Portfolio_Analytics_Presentation_Guide.docx) in this repository.

---

## Business Problem

The bank needs to understand how effectively its loan portfolio is being managed. It requires better visibility into loans disbursed, customer borrowing patterns, repayment collections, branch performance and credit risk exposure, so that management can identify risks, monitor lending performance and make informed lending decisions.

The analysis covers these areas: loan portfolio performance, customer borrowing behaviour, repayment and collection performance, branch performance, and credit risk and default.

## Dataset

The dataset was **synthetically generated using ChatGPT**, based on a business problem and data requirements I defined. It holds 18,010 records across four related tables, with all amounts in Nigerian naira (NGN).

| Table | Records |
|---|---:|
| `branch` | 10 |
| `customer` | 2,000 |
| `loan` | 4,000 |
| `repayment` | 12,000 |

## Tools and Technologies

- **ChatGPT**: synthetic dataset generation
- **MySQL / MySQL Workbench**: data import, validation, cleaning and analysis
- **Microsoft Excel**: charts, slicers and dashboard
- **Power Pivot**: attempted but not completed (see below)

## Workflow

1. **Generate** the synthetic dataset with ChatGPT.
2. **Import and inspect** the data in SQL, checking tables, columns and relationships.
3. **Validate and clean** a separate copy (`loanportfolio_clean`), leaving the original database untouched. The data had no duplicates, missing values or orphan records. The fixes were structural: removing stray characters from ID columns, adding primary and foreign keys, and converting text dates to the `DATE` type.
4. **Analyse** the portfolio using SQL queries.
5. **Build the dashboard** in Excel from SQL-combined tables.

## Dashboard

The Excel dashboard has three tabs, with navigation buttons and slicers for filtering by state, branch and employment type.

1. **Loan Portfolio Performance:** loans issued, loan value, outstanding balances, borrowing patterns, portfolio status, and distribution by state and employment type.
2. **Loan Repayment and Collection Performance:** total repayments, outstanding balances, collection performance and trends over time, compared across states and branches.
3. **Credit Risk and Default Analysis:** default rates, defaulted amounts and outstanding balances by state, branch and employment type.

The dashboard has some interactivity but is **not fully dynamic** (see the challenge below).

<!-- Add dashboard screenshots here, e.g. ![Dashboard](images/dashboard.png) -->

## Technical Challenge and Workaround

**Challenge:** I tried to load multiple SQL queries into the Excel Data Model using Power Pivot. The connection produced errors and I could not complete this approach.

**Workaround:** I used SQL to combine multiple queries into larger tables, imported them into Excel, and built the charts and dashboard from them. This works, but gives more limited filtering than a full Data Model would.

## Key Findings

- **4,000 loans** worth **₦2,327,850,000** were disbursed to 1,718 of 2,000 customers. **₦1,132,951,050** is still outstanding.
- Total collections were **₦1,194,898,950**, a collection-to-disbursement ratio of **51.33%**.
- **32.38%** of loans are late (21.80%) or defaulted (10.58%).
- **Ibadan North** and **Lagos Island** lead on both disbursement and collections.
- **Business owners** received high lending but had the lowest collections and the highest default rate (11.40%). **Public sector workers** had the lowest default rate (9.73%).
- Risk is concentrated: the high-risk and very high-risk categories hold **81.67%** of the outstanding portfolio but make up 40.52% of customers.
- First-time borrowers have a slightly higher default rate (11.64%) than repeat borrowers (10.41%).
- Collections fell sharply in 2025 and need investigation.

**Main recommendations:** support growth in strong branches, monitor business owners closely, strengthen retention in key locations, and assess first-time borrowers more rigorously.

## Conclusion

This project took a synthetic loan dataset from inspection and cleaning through SQL analysis to an Excel dashboard, and turned the results into business recommendations. The Power Pivot approach did not work out, so the dashboard has limited interactivity. Rebuilding it on a full Data Model would be a natural next step.

---

**Author:** Nafisat Abdulraheem
