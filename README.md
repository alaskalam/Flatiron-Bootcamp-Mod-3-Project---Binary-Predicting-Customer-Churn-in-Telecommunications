
# Module 3 Final Project


## Introduction

There are many factors that can affect customer churn in telecommunications companies, including number of services used, tenure, type of contract and type of services used. The goal of this project was to create a model that could reliably predict whether or not a given customer would cease using a given telecommunications company's services.


## Methodology

Analyze past customer churn data from Telco, to make recommendations for your telecommunications company, on how to most efficiently retain customers and market to new ones

###The dataset

We used the Telco communications dataset from Kaggle, which contains the following datapoints.
[Customer Churn Data](https://www.kaggle.com/becksddf/churn-in-telecoms-dataset)


gender - male or female customer

SeniorCitizen - whether or not customer is a senior citizen

Partner - whether or not customer has a partner

Dependents - whether or not customer has any dependents

tenure - number of months customer has used company's services

PhoneService - Whether the customer has a phone service or not

MultipleLines - Whether the customer has multiple lines or not (Yes, No, No phone service)

InternetService- Customer’s internet service provider (DSL, Fiber optic, No)

OnlineSecurity - Whether the customer has online security or not (Yes, No, No internet service)

OnlineBackup - Whether the customer has online backup or not (Yes, No, No internet service)

DeviceProtection- Whether the customer has device protection or not (Yes, No, No internet service)

TechSupport - Whether the customer has tech support or not (Yes, No, No internet service)

StreamingTV - Whether the customer has streaming TV or not (Yes, No, No internet service)

StreamingMovies - Whether the customer has streaming movies or not (Yes, No, No internet service)

Contract - The contract term of the customer (Month-to-month, One year, Two year)

PaperlessBilling - Whether the customer has paperless billing or not (Yes, No)

PaymentMethod - The customer’s payment method (Electronic check, Mailed check, Bank transfer (automatic), Credit card (automatic))

MonthlyCharges - The amount charged to the customer monthly

TotalCharges - The total amount charged to the customer

Churn - Whether the customer churned or not (Yes or No)


## The Model

We decided to focus on optimizing recall, as false negatives were most important to decrease. False negatives are when we believe the customer will stay loyal, but they end up churning.

False positives, aka believing the customer will churn when they in fact stay, are not nearly as harmful in their effects.

We decided to conduct a baseline random forest model, and then proceeded to run SMOTE, create 2 new features (whether or not a customer had changed types of membership plans, and the number of services a customer currently subscribes to), perform hyperparameter tuning and create a new model. The results are below:




Our finished model, with our new features of "number of services used" and "switched plans or not", added includes a recall for 1 of .77, which is a drastic increase from our baseline model of .46.

Our false negatives have also decreased to 5.92%, from 6.53%, as a result of adding our new features.

##Conclusions

Those who are not subscribed to tech support or online security, are more likely to churn. These are two of the most paramount factors and are highly recommended for your company to focus marketing efforts on.

Number of services often has significantly more impact on churn than whether or not a customer has a specific service, namely for movie and tv streaming, and phone service itself. The higher the number, typically the less likely a customer will be to churn. Upselling and providing marketing deals for existing customers with relatively smaller number of services used, will be worth investigating.

Whether a customer has changed a plan or not, has only a small impact. Monthly and lifetime charges had virtually no impact - so it may not be worth it to focus churn-avoidance efforts on those who have small bills.

Those who have month-to-month contracts are significantly more likely to churn vs yearly contract customers, unless they are subscribed to tech support. Consider offering special deals for those who sign up for a yearly contract.

Those with tenure of less than 6 years are significantly more likely to churn. Consider focusing your churn-avoidance efforts on customers who have recently signed up.

## Future Work

Investigating the difference between upgrading vs downgrading one's membership plan

Test specifically for paperless billing vs non paperless

Loyalty programs

Type of carrier used



