
# Telco Customer Churn Prediction


**Problem**: Develop a machine learning model that can predict customers who will leave the company.

This pyhton code tests model performance of mutiple machine learning models to find best model.

***Note: The codes are from the Miuul 'Machine Learning' course. Some parts of the codes are modified by me.***

- Clone the 'churn prediction' repository using your terminal or git bash.

```
git clone https://github.com/burcukuleci/churn-prediction.git
```
- Download all required packages using the requirements.txt file by running the below command in the terminal.

```
pip install -r requirements.txt
```

- **dataset**: 'Telco-Customer-Churn.csv'

**21 Variables 7043 Observations**

```
CustomerId 
Gender
SeniorCitizen : Whether the customer is elderly (1, 0)
Partner : Whether the client has a partner (Yes, No) 
Dependents : Whether the customer has dependents (Yes, No) (Child, mother, father, grandmother)
tenure : Number of months the customer stays with the company
PhoneService : Whether the customer has telephone service (Yes, No)
MultipleLines : Whether the customer has more than one line (Yes, No, No phone service)
InternetService : Customer's internet service provider (DSL, Fiber optic, No)
OnlineSecurity : Whether the customer has online security (Yes, No, No internet service)
OnlineBackup : Whether the client has an online backup (Yes, No, No internet service)
DeviceProtection : Whether the customer has device protection (Yes, No, No internet service)
TechSupport : Whether the customer receives technical support (Yes, No, No internet service)
StreamingTV : Whether the customer has TV reception (Yes, No, No Internet service)
StreamingMovies : Whether the customer streams movies (Yes, No, No internet service)
Contract : Customer's contract period (Month-to-month, One year, Two years)
PaperlessBilling : Whether the customer has a paperless invoice (Yes, No)
PaymentMethod : Customer's payment method (Electronic check, Mailed check, Bank transfer (automatic), Credit card (automatic))
MonthlyCharges : Amount collected from the customer on a monthly basis
TotalCharges : Total amount collected from customer
Churn : Whether the customer is a user (Yes or No) - Customers who left within the last month or quarter
```

- Each row represents a unique customer.

- Services customers have signed up for - phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies.

- Customer account information - how long they have been a customer, contract, payment method, paperless billing, monthly fees, and total charges.

- Demographic information about customers - gender, age range, and whether they have partners and dependents.


## EXPLORATORY DATA ANALYSIS

Categorical and numeric columns are determined. Data types of columns are fixed.

## FEATURE ENGINEERING

- Missing Values

Rows with missing values are dropped.

- Outliers

Outliers are replaced with threshold values that are determined with IQR method.

- Feature Extraction

New columns are created. 

- Encoding 

Categorical columns are encoded with label encoding and one-hot encoding.

- Scaling

Numerical columns are sclaed with *StandardScaler*.

## MODEL

Multiple machine learning models are trained with default hyper parameter values.

## HYPERPARAMETER OPTIMIZATION

Hyperparamter optimization is performed with *GridSearchCV* method of 5 folds to determine final models with best hyper parameter values. 

Model performance is measured with cross validation. 

In addition, *confusion matrix* is also considered. (Positive class is churn (1).)

- RandomForestClassifier
- XGBClassifier
- LGBMClassifier
- CatBoostClassifier

```
MODEL ACCURACY (hyperparameter optimization)
                Before   After
RandomForest    0.79     0.799
XGBoost         0.78     0.799
LigtGBM         0.79     0.802
CatBoost        0.80     0.804
```

## FEATURE IMPORTANCE 

Feature importance for RandomForest, XGBoost, LigtGBM and CatBoost models is examined.




