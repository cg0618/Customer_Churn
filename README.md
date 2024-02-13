# Telecom Customer Churn

## Brief Introduction
Customer churn occurs when clients or subscribers cease their engagement or business relationship with a company or service provider.

The dataset contains churn data from a fictional telecommunications company. In the telecom industry, customers have the flexibility to select from a diverse range of service providers, often opting to switch between them. This dataset provides insights into customer behaviors and factors influencing churn within this highly competitive market.

The primary objective is to broaden coverage and enhance customer loyalty.

## Objectives
- To determine the percentage of customers who have churned and those who remain active with the services.
- To identify the most appropriate predictive model for accurately classifying customers into churned and non-churned categories.
- To examine the data with regard to different features influencing customer churn.

## The dataset
 [Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn/data)

### The dataset comprises data pertaining to:

- Customers who closed their contract/subscription in the past month, identified by the column labeled "Churn"
- Demographics – gender, age range, and if they have partners and dependents
- Information regarding customer accounts, such as their tenure, contract status, payment method, preference for paperless billing, monthly charges, and total charges.
- Services to which each customer has subscribed, which include phone, multiple lines, internet, online security, online backup, device protection, technical support, and streaming TV and movies.


## Exploratory Data Analysis (EDA)

### Demographics
#### 1. Senior Citizens
Approximately only 16% of the customers are senior citizens, implying that most of our customers in the data are younger people.

### Distribution of Total Charges by Churn
The boxplot below suggests that individuals categorized as Churners or Churned customers show smaller total charges in comparison to non-churners. Churners do not complete the contract, implying a likelihood of lower total charges compared to non-churners. To delve deeper into this data, the boxplot has been organized based on their respective contracts.
![totChargeDist](https://github.com/cg0618/Customer_Churn/blob/80864801200b6f0ef3d111b7085468aab3041015/images/totChargeDist.png)

Surprisingly, it appears that customers with one-year and two-year contracts have higher total charges, which implies that different contract durations might contribute in influencing the total charges incurred by customers. Further, this means that after having their one-year and two-year contracts, customers are more likely to churn if they are having more total charge.
![totChargeContractDist](https://github.com/cg0618/Customer_Churn/blob/80864801200b6f0ef3d111b7085468aab3041015/images/totChargeContractDist.png)
