# Customer Behavior & Marketing Analytics

A data analytics project exploring customer purchasing behavior, loyalty patterns, product preferences, and order outcomes using an electronic sales dataset.

The project covers the analysis process from data understanding and cleaning to exploratory analysis, preprocessing, feature selection, and baseline classification modeling.

---

## Project Overview

The dataset contains **20,000 electronic sales transactions** with information about customer demographics, loyalty membership, products, ratings, order status, payment methods, pricing, shipping, and add-on purchases.

The analysis focuses on understanding customer behavior across different purchasing and loyalty patterns, while also exploring whether order status can be predicted from the available transaction and customer features.

---

## Dataset

The dataset contains variables such as:

- Customer ID
- Age
- Gender
- Loyalty Member
- Product Type
- Rating
- Order Status
- Payment Method
- Total Price
- Unit Price
- Quantity
- Purchase Date
- Shipping Type
- Add-ons Purchased
- Add-on Total

The original dataset contains:

```text
20,000 transaction records
```

---

## Analysis Workflow

### 1. Data Understanding

The dataset was first explored to understand:

- Dataset structure
- Data types
- Unique values
- Missing values
- Customer and transaction characteristics

### 2. Data Cleaning

The cleaning process included:

- Handling missing values
- Checking duplicated records
- Standardizing inconsistent categorical values
- Converting purchase dates into datetime format
- Reviewing numerical outliers

After IQR-based outlier handling, the dataset was reduced from:

```text
20,000 rows
```

to:

```text
19,373 rows
```

### 3. Exploratory Data Analysis

The exploratory analysis focuses on:

- Customer demographics
- Product preferences
- Order completion and cancellation
- Payment methods
- Shipping methods
- Add-on purchases
- Customer ratings
- Average Order Value
- Loyalty behavior
- Purchasing trends over time

The visualizations are included directly in the Jupyter Notebook.

---

## Loyalty Analysis

Customer loyalty behavior was tracked across purchases and grouped into four statuses:

- **Non Member**
- **New Member**
- **Regular Member**
- **Churned**

The analysis found:

| Loyalty Status | Customers |
|---|---:|
| Non Member | 9,805 |
| Regular Member | 2,682 |
| Churned | 1,353 |
| New Member | 1,328 |

This grouping was then used to compare purchasing behavior across different types of customers.

---

## Average Order Value

Average Order Value was also compared across loyalty groups.

| Loyalty Status | Average Order Value |
|---|---:|
| New Member | $3,237.40 |
| Non Member | $3,192.94 |
| Churned | $3,182.00 |
| Regular Member | $3,092.65 |

The notebook also compares order value with and without add-on purchases.

---

## Data Preparation

Before modeling, several preprocessing steps were applied.

### Encoding

Binary variables such as:

```text
Gender
Loyalty Member
Order Status
```

were converted into numerical values.

Other categorical features were transformed using one-hot encoding.

### Date Features

Additional features were extracted from purchase dates:

- Year
- Month
- Day of Week

### Scaling

Numerical features were standardized using `StandardScaler`.

### Feature Selection

Mutual Information was used to select features related to order status.

The selected features for the Random Forest model were:

```text
Day_of_Week
Unit Price
Rating
Add-on Total
Age
```

---

## Classification Models

Two classification models were tested to predict whether an order would be:

```text
Completed
or
Cancelled
```

The models used were:

- Random Forest Classifier
- XGBoost Classifier

The data was split into training and testing sets using an 80/20 split.

---

## Model Results

### Random Forest

```text
Accuracy: 62%
ROC-AUC: 0.5107
```

### XGBoost

```text
Accuracy: 67%
ROC-AUC: 0.5019
```

XGBoost produced higher accuracy, but both ROC-AUC scores were close to 0.50.

Because of this, the models are treated as baseline experiments rather than strong predictive models. The main focus of the project remains the customer behavior analysis, preprocessing process, and exploration of purchasing patterns.

---

## Tech Stack

| Area | Tools |
|---|---|
| Programming | Python |
| Data Manipulation | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn, XGBoost |
| Environment | Google Colab / Jupyter Notebook |
| Version Control | Git, GitHub |

---

## Project Structure

```text
customer-behavior-marketing-analysis/
│
├── data/
│   └── ElectronicSales.csv
│
├── notebook/
│   └── customer_behavior_marketing_analysis.ipynb
│
├── .gitignore
└── README.md
```

---

## Notebook

The complete analysis is available in:

```text
notebook/customer_behavior_marketing_analysis.ipynb
```

The notebook contains the data exploration, visualizations, preprocessing, feature selection, and model evaluation.

GitHub can render the notebook directly, so the outputs can be viewed without running it locally.

---

## My Role

### Data Analysis & Modeling Contributor

My contribution focused on:

- Supporting exploratory data analysis and customer behavior analysis
- Assisting with data preprocessing and preparation for modeling
- Contributing to model testing and interpretation of the results

---

## Notes

The classification models were used as baseline experiments.

Their ROC-AUC scores were close to 0.50, which suggests that the available features have limited ability to separate completed and cancelled orders.

Possible next steps include:

- Handling class imbalance
- Additional feature engineering
- Hyperparameter tuning
- Testing other classification models
- Adding more customer-history features

---

## License

This project was developed for educational and portfolio purposes.