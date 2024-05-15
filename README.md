# Lending Club Case Study
Solving this assignment will give you an idea about how real business problems are solved using EDA. In this case study, apart from applying the techniques you have learnt in EDA, you will also develop a basic understanding of risk analytics in banking and financial services and understand how data is used to minimise the risk of losing money while lending to customers


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Contact](#contact)

<!-- You can include any other section that is pertinent to your problem -->

## General Information

### Business Understanding

You work for a consumer finance company which specialises in lending various types of loans to urban customers. When the company receives a loan application, the company has to make a decision for loan approval based on the applicant’s profile. Two types of risks are associated with the bank’s decision:

If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company

If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company

The data given below contains information about past loan applicants and whether they ‘defaulted’ or not. The aim is to identify patterns which indicate if a person is likely to default, which may be used for taking actions such as denying the loan, reducing the amount of loan, lending (to risky applicants) at a higher interest rate, etc.

In this case study, you will use EDA to understand how consumer attributes and loan attributes influence the tendency of default.

When a person applies for a loan, there are two types of decisions that could be taken by the company:

Loan accepted: If the company approves the loan, there are 3 possible scenarios described below:

Fully paid: Applicant has fully paid the loan (the principal and the interest rate)

Current: Applicant is in the process of paying the instalments, i.e. the tenure of the loan is not yet completed. These candidates are not labelled as 'defaulted'.

Charged-off: Applicant has not paid the instalments in due time for a long period of time, i.e. he/she has defaulted on the loan 

Loan rejected: The company had rejected the loan (because the candidate does not meet their requirements etc.). Since the loan was rejected, there is no transactional history of those applicants with the company and so this data is not available with the company (and thus in this dataset)
 

### Business Objectives
This company is the largest online loan marketplace, facilitating personal loans, business loans, and financing of medical procedures. Borrowers can easily access lower interest rate loans through a fast online interface. 

Like most other lending companies, lending loans to ‘risky’ applicants is the largest source of financial loss (called credit loss). Credit loss is the amount of money lost by the lender when the borrower refuses to pay or runs away with the money owed. In other words, borrowers who default cause the largest amount of loss to the lenders. In this case, the customers labelled as 'charged-off' are the 'defaulters'. 

If one is able to identify these risky loan applicants, then such loans can be reduced thereby cutting down the amount of credit loss. Identification of such applicants using EDA is the aim of this case study.

In other words, the company wants to understand the driving factors (or driver variables) behind loan default, i.e. the variables which are strong indicators of default.  The company can utilise this knowledge for its portfolio and risk assessment. 

To develop your understanding of the domain, you are advised to independently research a little about risk analytics (understanding the types of variables and their significance should be enough).



## Conclusions

### Data Cleaning
- Check for columns which has more than 90% NaN and drop them
- Check for columns which has missing values, analyse if you want to fix/replace data or drop it
- Before updating missing values, format data to make it uniform and of relevant data type
- Update missing data with respective values
- Check columns for invalid data and fix them. For ex: earliest_cr_line can not have future date or ratio open_acc/total_acc can not be creater then one
- Plot Histogram, analyse, identify outliers(>99%) and replace them with median in columns

### Univariate Analysis
- Loan Amount : Most Borrowers have applied loan for amount 10000, followed by 5000.
- Annual Income : Most Borrowers have self proclaimed income of 59000.
- 2year Delinquency : Most of the Borrowers have defaulted before finishing 1st year of loan, which is bad.
- Earliest Credit-Line : Most of Borrowers has Credit-Line opened for more than 310months, which is good.
- Verification Status : Most Borrowers had income verfied, which is good. 
- Loan Status : Most Borrowers have fully paid their loan.

### Bivariate Analysis
- Loan Amount vs. Annual Income:
    - As Income increases from 0 to 50000, Loan Amount gratually increases
    - As Income crosses 100000, number of Loans taken decreases
    - Most Borrower have taken loan with Annual Income less than 100000 and Loan Amount less than 20000.
- Verification Status vs. Loan Status:
    - Full Paid Loans are more when Income was Verified as compare to Not-Verified.
- Loan Status vs. Debt-to-Income Ratio:
    - When DTI ratio is lower for Fully Paid Loans
- Earliest Credit Line vs. Loan Amount:
    - Ealiest Cresit Line is directly proportional to Loan Amount.
- Home Ownership vs. Loan Status:
    - Borrower with Home Ownership as Rent or Own has mostly Paid the Loans fully.

### Multi-variate Analysis
- Loan Amount, Annual Income, and Loan Status
    - Most Borrower have taken loan with Annual Income less than 100000 and Loan Amount less than 20000.
    - Most of the loans are fully paid
    - When Income is between 50,000 to 100,000 and loan Amount is less than 7,500, the Charged off are less
- Loan Amount, DTI, and Loan Status
    - Most Borrowers has DTI less than 25 and Loan Amount under 10,000 are fully paid off
    - Lesser the DTI and Loan Amount, greater is number of loan fully paid and Vise-versa.
- Annual Income, Verification Status, and Loan Status
    - Most Borrowers irrespective of loan status or income verification has annual income between 40,000 to 100,000.
    - Income of Borrowers with income verified are better than than of non-verfied
- Total Recoveries, Loan Status, and Public Records
    - Total recoveries and Public records are only for Charged Off loans.
    - Even for Charged off loans, most Borrowers have Public records as clear.

### Business Analysis
- Calculate normalized CBIL Score based on data available and mapped it against Loan Status
- Used CBIL score to understand Risk/Portfolio Assestment.
- Conclusion:
    - If CBIL Score is greater than of equal to 70, then Borrower is good candidate for Loan.
    - If CBIL Score is between 60 to 69, then Borrower is ok candidate for loan. We decrease the Loan Amount to mitigate risk.
    - If CBIL Score is below 60, then Borrower is risky candidate for loan. We can increase the Loan interest rate to mitigate risk.


<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- pandas - version 2.1.4
- matplotlib - version 3.8.4
- seaborn - version 0.12.2



## Contact
Created by [@rishifrnds] and [@anand-swati] - feel free to contact!

You can find me on LinkedIn: [Rishi](https://www.linkedin.com/in/rishi-tode-a7805417/)
