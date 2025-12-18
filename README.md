 Bank loan analysis
                        **Project Overview**

This project analyzes real bank loan data with more than 100,000 loan records from 2021.
The aim is to understand how different types of borrowers behave, which loans perform well, and which factors increase the risk of default.

📊 Dataset Details
File:financial_loan 
Fields: id, addressstate, emplength, emptitle, grade, subgrade, homeownership, issuedate, loanstatus, purpose, loanamount, intrate, installment, dti, term, totalpayment, verificationstatus
Records: 100,000+
Year: 2021

Important Columns
Loan Information
id – Unique loan number
addressstate – Borrower’s state
issuedate – Loan issued date
loanstatus – Fully Paid, Current, or Charged Off

Borrower Details
emplength – Job experience
emptitle – Job title
homeownership – Rent, Mortgage, or Own
annualincome – Yearly income

Loan Details
loanamount – Amount borrowed
intrate – Interest rate
installment – Monthly payment
dti – Debt-to-income ratio
term – 36 or 60 months
purpose – Car, credit card, debt consolidation, etc.
Risk & Performance
grade – Loan grade (A to G)
subgrade – Detailed grade
verificationstatus – Income verification
totalpayment – Total amount repaid

Tools Used
Python (Pandas, Matplotlib, Seaborn)
SQL (MySQL / PostgreSQL)

Business Impact:
Risk Management: Identify high-risk borrower segments to reduce future defaults
Pricing Optimization: Set appropriate interest rates by grade/purpose combinations
Portfolio Strategy: Balance 36/60-month terms and geographic exposure
Marketing Targeting: Focus on proven borrower profiles (homeowners, stable jobs)
Regulatory Reporting: Track loan performance by state and loan type
The dataset includes comprehensive fields like loan amounts ($2K-$30K), payment histories, verification status, and total recoveries, making it perfect for building production-ready dashboards, risk models, and automated reporting workflows.

🚀 Quick Start
Prerequisites
bash
Python 3.8+ | Pandas | Matplotlib | Seaborn | Jupyter
Power BI | SQL Server/MySQL | n8n (optional)

Setup
git clone <your-repo-url>
cd bank-loan-analysis
pip install -r requirements.txt

Key Findings
✅ Good Loans: 70% (Fully Paid + Current)
❌ Bad Loans: 20% (Charged Off)  
💰 Avg Loan: $8K | Avg Rate: 14% | Avg DTI: 18%
📍 Top States: CA, TX, FL (highest volume)
🎯 Riskiest: Grade E/F/G, 60-month terms, renters

Overall Summary
Total loans analyzed: 100,000+
Around 70% loans are good (Fully Paid or Current)
About 20% loans are Charged Off
Average interest rate is around 14%
Higher interest rate and longer loan term increase risk



sql
SELECT grade,
       COUNT(*) AS total_loans,
       AVG(intrate*100) AS avg_interest_rate,
       SUM(CASE WHEN loanstatus='Charged Off' THEN 1 ELSE 0 END) * 100.0 / COUNT(*) AS default_rate
FROM bank_loan_data
GROUP BY grade
ORDER BY grade;

Key Measures:
GoodLoan% = DIVIDE(CALCULATE(COUNTROWS(Loans), Loans[Status] IN {"Fully Paid", "Current"}), COUNTROWS(Loans))
DefaultRate% = DIVIDE(CALCULATE(COUNTROWS(Loans), Loans[Status] = "Charged Off"), COUNTROWS(Loans))
RecoveryRate% = DIVIDE(SUM(Loans[totalpayment]), SUM(Loans[loanamount]))


Conclusion
This project clearly shows how data analysis helps in understanding loan risk and borrower behavior.
From the analysis, it is evident that:
Loan grade, interest rate, and loan term are the strongest risk factors
Shorter-term loans are safer and more profitable
Borrowers with stable income and home ownership perform better
Certain states and loan purposes need closer monitoring
Overall, this project demonstrates real-world financial data analysis skills, including data cleaning, KPI creation, SQL querying, and dashboard reporting.
It reflects how banks can use historical data to reduce defaults, improve credit policies, and make smarter lending decisions.

Power BI

Jupyter Notebook
