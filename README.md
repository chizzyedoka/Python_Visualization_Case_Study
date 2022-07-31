# Python_Visualization_Case_Study
This is my last project on Udacity Data Analyst Nanodegree. I was tasked with creating key insights from a dataset using python and libraries like numpy, pandas and seaborn. The dataset chosen for this project is a Loan dataset.
## Dataset
This data set contains 113,937 loans with 81 variables on each loan, including loan amount, borrower rate (or interest rate), current loan status, borrower income, borrower's Prosper rating, loan term, borrower's stated monthly income, as well as many other features such as borrower's employment status, debt to income ratio and many others.

This [data dictionary](https://docs.google.com/spreadsheets/d/1gDyi_L4UvIrLTEC6Wri5nbaMmkGmLQBk-Yx3z0XDEtI/edit) explains the variables in the data set.
We will not be exploring all of the variables, we will focus on just the very important ones.Focusing our exploration on about 10-15 of them.


## Structure of Dataset
Here are the columns used for my visualizations.
- **Term**: The length of the loan expressed in months.


- **BorrowerAPR**: The Borrower's Annual Percentage Rate (APR) for the loan. It is the actual amount a borrower pays including services fee in terms of percentages


- **ProsperRating(numeric)**: The  Prosper Rating assigned at the time the listing was created: 0 - N/A, 1 - HR, 2 - E, 3 - D, 4 - C, 5 - B, 6 - A, 7 - AA.  Applicable for loans originated after July 2009. HR<E<D<C<B<A<AA.


- **ProsperScore**: A custom risk score built using historical Prosper data. The score ranges from 1-10, with 10 being the best, or lowest risk score.  Applicable for loans originated after July 2009.


- **EmploymentStatusDuration**: The length in months of the employment status at the time the listing was created.


- **CurrentDelinquencies**: Number of accounts delinquent at the time the credit profile was pulled.


- **TradesNeverDelinquent (percentage)**: Number of trades that have never been delinquent at the time the credit profile was pulled.


- **DebtToIncomeRatio**: The debt to income ratio of the borrower at the time the credit profile was pulled. This value is Null if the debt to income ratio is not available. This value is capped at 10.01 (any debt to income ratio larger than 1000% will be returned as 1001%).


- **StatedMonthlyIncome**: The monthly income the borrower stated at the time the listing was created. 


- **LoanOriginalAmount**: The origination amount of the loan.


- **MonthlyLoanPayment**: The scheduled monthly loan payment. 


- **LoanStatus**: The current status of the loan: Cancelled,  Chargedoff, Completed, Current, Defaulted, FinalPaymentInProgress, PastDue. The PastDue status will be accompanied by a delinquency bucket.
    1. Completed -  A loan that has been paid in full
    2. Current -  A loan that is been owned as at that time
    3. Cancelled- Loans that are no longer required to be paid
    4. Chargedoff - Loans that have been written off as a loss
    5. Defaulted - Loan as to which all payments of principal and interest then due have been paid, except for the most recent                    payment then due of principal and interest.
    6. FinalPaymentInProgress - Final loan payment before a loan is completed
    7. PastDue - Loans payment that has passed their due date


- **ProsperRating(Alpha)**: The Prosper Rating assigned at the time the listing was created between AA - HR.
    HR<E<D<C<B<A<AA.


- **EmploymentStatus**: The employment status of the borrower at the time they posted the listing.
 
 
## Summary of Findings

### Univariate Exploration

- In this exploaration I found out that about 50% of the loans are currently active and 33% of loans have been completed(that is paid fully) also Chargedoff and defaulted loans made up for about 16% of loans.

- The distribution of BorrowerAPR looks multimodal and it has same pattern as LenderYield which is logical because the more a borrower pays on a loan the more the lender gains.

- Most loans were given to people either employed or self employed.

- We have more borrowers earning less than the average monthly salary yet we have more borrowers paying larger monthly payment.


### Bivariate Exploration

- The larger the loans the larger the monthly payments to be paid.

- The dataset is almost evenly distributed between home owners and non-home owners

- Larger loans require more time to pay

- Borrowers rating are affected by monthly income, requested loan and borrower APR

- Loans with large borrowerAPR are most likely going to be defaulted or chargedoff


### Multivariate Exploration

- A surprising interaction is that the borrower APR and loan amount is negatively correlated when the Prosper ratings are from HR to B, but the correlation is turned to be positive when the ratings are A and AA. Another interesting thing is that the borrower APR decrease with the increase of borrow term for people with HR-C raings. But for people with B-AA ratings, the APR increase with the borrow term.


-  We see that lower ratings like HR,E,D and C were given to people with lower monthly income and lower loans.Also, higher ratings were given to people with high monthly income and monthly loan payment. Thus the higher the loans you collect the more your ratings increases



### Key Insights for Presentation

1. The prosper loan dataset is highly inter related but the relations that stood out are:

2. The BorrowerAPR is negatively correlated with the prosper rating, the BorrowerAPR also follows the same trend as the LenderYield

3. The prosperRating is strongly affected by the BorrowerAPR, stated monthly income and loan original amount

4. Borrowers with low income have their loans chargedoff or they default them.
