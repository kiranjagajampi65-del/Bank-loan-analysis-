 Bank loan analysis
                        **Project Overview**

# 💰 Bank Loan Risk Analysis (100K+ Records)

## What I Built


This project delivers an in-depth analysis of 100,000+ bank loan records to evaluate borrower behavior, loan performance, and default risk. By combining Python, SQL, and Power BI, the analysis identifies key risk drivers and provides actionable insights that can improve credit policies, pricing strategies, and portfolio management.


To understand what makes borrowers repay on time vs. default. This project helps banks spot risky loans early, set better interest rates, and target safer customers.


## Business Objectives

- Identify high-risk borrower segments and default patterns 

- Evaluate loan performance across grades, terms, and purposes

- Analyze the impact of interest rates, DTI, and employment stability

-  Support data-driven lending and risk mitigation decisions
## 📋 The Data

**financial_loan.csv** - 100K+ records with 17 key columns:

**Core Loan Info:**
- `id`, `loanamount` ($2K-$30K), `intrate`, `term` (36/60 months)
- `loanstatus` (Fully Paid, Current, Charged Off)
- `issuedate`, `grade` (A-G), `purpose` (debt consolidation, car, etc.)

**Borrower Profile:**
- `addressstate`, `homeownership` (Rent/Own/Mortgage)
- `emplength`, `dti` (debt-to-income), `annualincome`
- `verificationstatus`

## 🛠️ Tools I Used


## 🔍 What I Discovered

**The Numbers:**
- ✅ **70% Good Loans** (Fully Paid + Current)
- ❌ **20% Defaults** (Charged Off)
- 💵 **Avg Loan: $8,100** | **Avg Rate: 14%** | **Avg DTI: 18%**

**Biggest Risk Factors:**
1. **Grades E/F/G** - 40%+ default rates
2. **60-month terms** - twice as risky as 36 months
3. **Renters** - default 2x more than homeowners
4. **CA/TX/FL** - highest loan volume (watch these states)


```sql
SELECT 
    grade,
    COUNT(*) AS total_loans,
    AVG(intrate * 100) AS avg_interest_rate,
    SUM(CASE WHEN loanstatus = 'Charged Off' THEN 1 ELSE 0 END) * 100.0 / COUNT(*) AS default_rate
FROM bank_loan_data
GROUP BY grade
ORDER BY grade;
  

Conclusion

This project demonstrates practical financial data analysis skills applied to real-world lending data. The insights show how banks can leverage historical loan performance to reduce defaults, improve profitability, and make informed, data-driven credit decisions. It reflects strong capabilities in data analysis, SQL querying, KPI development, and business-focused reporting.  
Power BI

Jupyter Notebook
