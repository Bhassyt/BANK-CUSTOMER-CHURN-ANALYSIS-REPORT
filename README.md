# BANK-CUSTOMER-CHURN-ANALYSIS-REPORT
---

**Documentation Outlines**

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools Used](#tools-used)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Data Analysis](#data-analysis)
- [Results and Findings](#results-and-findings)
- [Conclusions and Recommendations](#conclusions-and-recommendations)

## Project Overview
---
In the competitive banking industry, customer retention is paramount for sustained growth and profitability. Customer churn, the rate at which customers switch banks, poses a significant challenge. Analyzing churn patterns offers insights to retain existing customers and attract new ones. This project aims to comprehensively analyze bank customer churn using data-driven approaches.

## Data Sources
---
The primary dataset utilized for this analysis is the "bank_customer_churn_data.xlsx" file. The bank customer churn dataset is a commonly used dataset for predicting customer churn in the banking industry. It contains information on bank customers who either left the bank or continue to be a customer. The dataset includes the following attributes:
- **Customer ID:** A unique identifier for each customer.
- **Surname:** The customer's surname or last name.
- **Credit Score:** A numerical value representing the customer's credit score.
- **Geography:** The country where the customer resides (France, Spain or Germany).
- **Gender:** The customer's gender (Male or Female).
- **Age:** The customer's age.
- **Tenure:** The number of years the customer has been with the bank.
- **Balance:** The customer's account balance.
- **NumOfProducts:** The number of bank products the customer uses (e.g., savings account, credit card).
- **HasCrCard:** Whether the customer has a credit card (1 = yes, 0 = no).
- **IsActiveMember:** Whether the customer is an active member (1 = yes, 0 = no).
- **EstimatedSalary:** The estimated salary of the customer.
- **Exited:** Whether the customer has churned (1 = yes, 0 = no).

The dataset aims to determine customer churn, enabling banks to anticipate and prevent customer attrition. By determining churn, banks can proactively retain customers and reduce turnover rates. This facilitates the implementation of targeted strategies to enhance customer retention, fostering long-term profitability in the competitive banking sector.

## Tools Used
---
- Microsoft Excel (For Data Cleaning)
- Microsoft Power BI (For Reporting and Dashboarding)

## Data Cleaning and Preparation
---
In the initial data preparation phase, the following tasks were performed:
- Data Loading and Inspection.
- Handling Duplicate Data.
- Handling Missing Data.
- Data Formatting.
- Feature Selection/Engineering.

**Exploratory Data Analysis**

EDA entails delving into the data to address various questions regarding its characteristics, which includes:
- Among the analyzed countries (France, Germany, and Spain), which geographic location had the highest customer count?
- Among the analyzed customer base, which gender had the highest customer count?
- Which churn status (churned or not churned) had the higher number of customers?
- Among the customers analyzed, which group (those with a credit card or those without a credit card) had a higher customer count?
- Between active and inactive customers, which customer group had a higher count?
- Which product had the highest number of customers among all the analyzed products?

## Data Analysis
---
Here is where I incorporated certain Data Analysis Expressions (DAX) utilized during my analysis.
```
Active Member Count = CALCULATE(COUNTROWS('Bank Customer Churn'), 'Bank Customer Churn'[IsActiveMember] = 1)
```
```
Churn Rate = SUM('Bank Customer Churn'[Exited]) / COUNT('Bank Customer Churn'[CustomerId])
```
```
Churned = CALCULATE(COUNTROWS('Bank Customer Churn'), 'Bank Customer Churn'[Exited] = 1)
```
```
Customers with Credit Card = CALCULATE(COUNTROWS('Bank Customer Churn'), 'Bank Customer Churn'[HasCrCard] = 1)
```
```
Customers without Credit Card = CALCULATE(COUNTROWS('Bank Customer Churn'), 'Bank Customer Churn'[HasCrCard] = 0)
```
```
Female Count = CALCULATE(COUNTROWS('Bank Customer Churn'), 'Bank Customer Churn'[Gender] = "Female")
```
```
France Count = CALCULATE(COUNTROWS('Bank Customer Churn'), 'Bank Customer Churn'[Geography] = "France")
```
```
Germany Count = CALCULATE(COUNTROWS('Bank Customer Churn'), 'Bank Customer Churn'[Geography] = "Germany")
```
```
Male Count = CALCULATE(COUNTROWS('Bank Customer Churn'), 'Bank Customer Churn'[Gender] = "Male")
```
```
Non-Active Member Count = CALCULATE(COUNTROWS('Bank Customer Churn'), 'Bank Customer Churn'[IsActiveMember] = 0)
```
```
Not Churned = CALCULATE(COUNTROWS('Bank Customer Churn'),'Bank Customer Churn'[Exited] = 0)
```
```
Spain Count = CALCULATE(COUNTROWS('Bank Customer Churn'), 'Bank Customer Churn'[Geography] = "Spain")
```

## Results and Findings
---
This is where the insights obtained from the analysis are presented. "Access my insights here:[[Dashboard Report Link](https://app.powerbi.com/view?r=eyJrIjoiMmY3NDFhNGMtNjE0Ni00ODE3LWE4MmYtNGQzNzk1MWExYjMwIiwidCI6IjBlZjcwYWU3LWI3NmUtNGI4ZC04NWEzLWZlZmFmNjg4MDAxZCJ9)]"
- Among the analyzed countries, France had the highest count of customers, totaling 5,014. Germany followed with 2,509 customers, and Spain had 2,477 customers.
- The count of male customers was higher, with 5,457 individuals, compared to female customers, which totaled 4,543.
- The count of customers who did not churn was higher, with 7,963 individuals, compared to those who churned, totaling 2,037.
- The count of customers with a credit card was higher, totaling 7,055 individuals, compared to those without a credit card, which amounted to 2,945.
- The count of active customers was higher, totaling 5,151 individuals, compared to those who were not active, which amounted to 4,849.
- Among the analyzed products, product 1 had the highest count of customers, totaling 5,084 individuals, which was 8,373.33% higher than product 4, which had the lowest count of customers at 60.
