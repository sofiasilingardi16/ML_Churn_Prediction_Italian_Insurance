# Predicting Customer Churn in Italian Motor Insurance

An end-to-end machine learning project focused on predicting customer churn for an Italian motor insurance company, with the goal of enabling targeted retention campaigns and improving customer retention.

## Project Overview

Customer churn is a major business issue in the insurance industry, especially in highly competitive markets where policyholders can easily switch providers. In this project, we developed a predictive model to identify customers who are most likely to not renew their motor insurance policy, so the company can intervene before renewal with personalized retention actions.

The project combines:

- Business understanding
- Data cleaning and preparation
- Churn target definition
- Exploratory data analysis
- Feature engineering
- Predictive modeling
- Business interpretation of model outputs

## Business Problem

The company's strategic goal is to reduce customer abandonment by identifying clients who are unlikely to renew their motor insurance contracts before they leave. The churn rate observed in the dataset is approximately **21.5%**, meaning about 1 in 5 customers does not renew their policy.

## Project Objective

Develop a predictive model that estimates the probability of churn within one year, so the business can:

- Prioritize high-risk customers
- Optimize retention campaigns
- Allocate CRM resources more efficiently
- Maximize customer lifetime value

## Dataset Description

The project integrates multiple sources of insurance-related data at the customer level:

### Client Data

Includes demographic and behavioral information such as:

- Age
- Seniority
- Number of accidents
- App usage
- Risk rating
- Province of residence

### Contract Data

Includes:

- Premium amounts
- Discounts
- Payment method
- Number of installments
- Product and risk type
- Warranty indicators / optional coverages

### Contract Dates

Includes:

- Contract effective date
- Contract closing date
- Contract expiration date

### Vehicle Data

Includes:

- Commercial value
- Vehicle type
- Power
- Yearly mileage
- ABS presence
- Airbag presence
- Anti-theft presence

## Unit of Analysis and Timeframe

The unit of analysis is **customer-year**. The project tracks the full customer base active in 2015 and follows complete contract history through 2020. The final modeling dataset is built with one row per customer per year.

## Churn Definition

A customer is classified as churned when their policy expires and they do not renew within 366 days of expiration. This definition was designed to reflect the real business meaning of churn. The project also distinguishes between:

- Early termination without renewal
- Early termination followed by renewal
- Normal expiration followed by renewal or non-renewal

## Data Preparation

Main preprocessing steps included:

- Converting date columns into proper datetime format
- Removing columns with too many missing values
- Converting Yes/No fields into binary variables
- Aggregating contract-level data into one row per customer per year
- Restricting the data to contracts expiring between 2015 and mid-2020
- Handling multicollinearity and removing leakage-prone features

## Exploratory Data Analysis

The exploratory analysis revealed several relevant churn patterns:

- Churn remained relatively stable over time, around 21%
- New customers and mid-tenure customers were more likely to churn
- Customers with no optional coverages had significantly higher churn rates
- Customers with a previous churn event were more likely to churn again
- Low-premium customers churned regardless of discount, suggesting that discount alone is not always an effective retention tool

These findings helped guide both feature engineering and business recommendations.

## Feature Engineering

The final dataset contains approximately:

- **908,000 observations**
- **43 variables**

Feature selection focused on keeping the most informative predictors while reducing redundancy and leakage. Among the strongest signals retained:

- Seniority
- Discount
- Previous churn
- Selected coverages

Expiry-year-related information was removed because it was too strongly correlated with the target and could create data leakage.

## Modeling Approach

We compared several models:

- Logistic Regression as a baseline
- XGBoost
- LightGBM

To ensure realistic evaluation, we used an **out-of-time split**:

- Training on past observations
- Testing on future observations

### Evaluation Metrics

The models were assessed using:

- Accuracy
- ROC-AUC
- Recall
- Precision

Particular attention was given to recall, because in a churn setting it is more costly to miss a customer who is about to leave than to contact some customers who would have stayed anyway.

## Results

The advanced models clearly outperformed the Logistic Regression baseline. In the expanded model comparison:

| Model                  | Accuracy | ROC-AUC | Recall  | Precision |
|-----------------------|----------|---------|---------|-----------|
| Logistic Regression    | 62.01%   | 74.40%  | 76.60%  | 33.33%    |
| XGBoost               | 71.90%   | 92.80%  | 88.50%  | 43.10%    |
| LightGBM             | 71.50%   | 93.40%  | 88.40%  | 42.60%    |

These results show that the best models are highly effective at:

- Ranking customers by churn risk
- Identifying a large share of actual churners
- Supporting retention prioritization

### Business Interpretation

In business terms:

- The model catches about **88 out of 100 customers** who would have churned
- Around **43 out of 100 contacted customers** are truly at risk
- Even when precision is moderate, the model is still valuable because preventing churn is typically worth the cost of contacting some false positives

## Business Insights

The project identified the main high-risk customer segments:

- New clients in their first year
- Mid-tenure clients with 4–7 years of seniority
- Customers with no optional coverages
- Customers with low premium and no discount
- Customers with previous churn history

## Recommended Retention Strategy

Based on the model and EDA findings, the company should:

- Contact high-priority clients 60–90 days before renewal
- Reward loyalty for mid-tenure customers
- Demonstrate value to new customers
- Propose add-on coverages to low-coverage clients
- Integrate churn scores into CRM workflows for targeted retention campaigns

## Limitations and Next Steps

### Main Limitations

- Missing behavioral signals such as call center interactions and digital engagement
- Limited predictive depth due to unavailable CRM and telematics data

### Suggested Next Steps

- Integrate model outputs into CRM systems
- Monitor campaign outcomes and model performance over time
- Retrain the model every 6–12 months
- Enrich the dataset with call center, digital, and telematics signals

## Tech Stack

Example tools and libraries used in the project:

- Python
- pandas
- numpy
- scikit-learn
- XGBoost
- LightGBM
- matplotlib / visualization tools
- Jupyter Notebook

---

**Authors:** Sofia Silingardi Hanna Kassahun Yihunie
Francesco Gambera
Akosua Ayewa Ofori-Karikari
Sukhdeep Singh Saini
Maria Alejandra Zapata Gil
**Repository:** [ML_Churn_Prediction_Italian_Insurance](https://github.com/sofiasilingardi16/ML_Churn_Prediction_Italian_Insurance)
