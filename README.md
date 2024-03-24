# BANK-CUSTOMER-CHURN-ANALYSIS-REPORT
---

![](![Untitled](https://github.com/Bhassyt/BANK-CUSTOMER-CHURN-ANALYSIS-REPORT/assets/158210164/e71871a5-639e-4109-be82-0ae7602b65d7))

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
- Between male and female customers, which gender had a higher percentage of customers who churned?
- Which country had the highest percentage of customers who churned (exited)?
- What was the churn rate for customers with 0 active members?
- What is the range of minimum balances among customers who are likely to churn?
- What is the distribution of customer exits based on tenure, and how does the churn rate vary across different tenure groups?
- What is the count of customers who churned among those who had a credit card?
- What is the count of customers who exited within a specific age range?

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
- Mostly female customers are exited around 11.4% and male are exited around 9%.
- Mostly customer are exited from Germany 8.1% and France 8.1% and Spain 4.1%.
- Mostly 0 number of active member are exited around 1302.
- Customers with a minimum balance ranging from 50,000 to 250,000 were more likely to churn, indicating a potential correlation between minimum balance levels and customer churn.
- Among customers who have been with the company for 10 years, approximately 101 have exited. Additionally, customers with tenures of 8 and 9 years, totaling around 197 and 213 respectively, have also exited.
- The majority of customers with a credit card, specifically around 1,424 individuals, have exited.
- Mostly minimum age 40 of range and maximum of the age 60 range are customers exited.

## Conclusions and Recommendations
---

**Conclusions**
- **Customer Distribution:** France had the highest count of customers, followed by Germany and Spain.
- **Gender Distribution:** Male customers outnumbered female customers.
- **Churn Rate:** A significant portion of customers did not churn, but there is still a notable churn rate.
- **Credit Card Usage:** A majority of customers had a credit card.
- **Activity Status:** Most customers were active, but there was a significant number of inactive customers.
- **Product Preference:** Product 1 was the most popular among customers, while Product 4 had the lowest adoption.
- **Churn Patterns:** Churn rates varied by gender, country, active membership, balance levels, tenure, and credit card usage.
- **Age Group:** Customers within the age range of 40 to 60 were more likely to churn.

**Recommendations**

Based on the analysis, i recommend the following actions:
- **Targeted Marketing:** Focus marketing efforts on retaining customers in countries with higher churn rates like Germany, France, and Spain. Tailor marketing strategies to appeal to both male and female demographics.
- **Retention Strategies:** Implement retention strategies to reduce churn rates, especially among customers with credit cards and those within the age range of 40 to 60. Offer incentives, personalized promotions, or loyalty programs to encourage customer loyalty.
- **Product Improvement:** Assess the performance of less popular products (like Product 4) and consider improving or discontinuing them based on customer preferences and feedback.
- **Customer Engagement:** Engage with inactive customers to understand their needs and reasons for disengagement. Offer personalized experiences or incentives to re-engage them with the company's products and services.
- **Risk Management:** Monitor customers with minimum balance levels between 50,000 to 250,000 closely and proactively address any issues to prevent churn.
- **Long-Term Customer Relationships:** Focus on retaining long-term customers by providing excellent service and tailored offerings. Investigate the reasons behind the churn of customers with longer tenures and implement strategies to mitigate future attrition.
- **Data-driven Decision Making:** Continuously analyze customer data to identify trends, patterns, and opportunities for improvement. Use insights to refine marketing strategies, product offerings, and customer retention initiatives.

By implementing these recommendations, the company can work towards reducing churn, enhancing customer satisfaction, and driving long-term profitability.
