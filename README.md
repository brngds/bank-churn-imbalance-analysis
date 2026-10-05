# ⚖️ Bank Churn & Class Imbalance Analysis

Machine learning analysis of bank customer churn with a focus on **class imbalance**, resampling strategies, model optimization, and classification performance.

## 📌 Context

Customer churn is an important challenge for financial institutions because retaining existing customers can be more cost-effective than acquiring new ones.

In this project, historical customer data from **Beta Bank** is used to predict whether a customer is likely to leave the bank.

The analysis places particular emphasis on one of the most common challenges in classification problems: **imbalanced classes**.

## 🎯 Problem

The objective is to build a classification model capable of identifying customers at risk of leaving the bank.

The main performance requirement is:

**F1-score ≥ 0.59 on the test dataset**

Because churned customers represent a minority of the dataset, the project also investigates different strategies for handling class imbalance and evaluates how these strategies affect model performance.

**ROC-AUC** is used as an additional metric to complement the F1-score evaluation.

## 📊 Dataset

The analysis uses the `Churn.csv` dataset containing customer profile and banking behavior information.

### Features

- `CreditScore` — customer credit score
- `Geography` — country of residence
- `Gender` — customer gender
- `Age` — customer age
- `Tenure` — length of relationship with the bank
- `Balance` — account balance
- `NumOfProducts` — number of banking products used
- `HasCrCard` — whether the customer has a credit card
- `IsActiveMember` — whether the customer is an active member
- `EstimatedSalary` — estimated salary

### Target

- `Exited`
  - `0` — customer remained
  - `1` — customer churned

Identifier columns such as `RowNumber`, `CustomerId`, and `Surname` are excluded from model training.

## 🔎 Approach

The project follows this machine learning workflow:

1. Data loading and inspection
2. Missing-value treatment
3. Feature preparation
4. Categorical encoding
5. Train, validation, and test split
6. Target class distribution analysis
7. Baseline model evaluation
8. Class imbalance treatment
9. Model and hyperparameter comparison
10. Validation using F1-score
11. Final test evaluation
12. ROC-AUC analysis

## ⚖️ Class Imbalance

The target variable is significantly imbalanced, with customers who remain at the bank representing the majority class.

Training a classifier directly on this distribution can cause the model to favor the majority class and reduce its ability to correctly identify customers who churn.

The analysis therefore evaluates techniques designed to improve minority-class detection, including **class balancing and resampling strategies**.

## 🔄 Resampling Strategy

One of the key approaches explored in this project is **upsampling**.

Upsampling increases the representation of the minority class in the training dataset, allowing the model to learn from a more balanced sample.

The performance of the resulting model is compared using validation F1-score before the final model is evaluated on unseen test data.

## 🤖 Model Evaluation

The primary evaluation metric is **F1-score**, which combines precision and recall and is particularly useful for imbalanced classification problems.

The final model achieves approximately:

**F1-score: 0.611**

This exceeds the required threshold of **0.59**.

The model also achieves approximately:

**ROC-AUC: 0.856**

The ROC-AUC result provides an additional perspective on the model's ability to distinguish customers who churn from customers who remain.

## 💡 Key Findings

The analysis demonstrates several important machine learning concepts:

- customer churn presents a clear class imbalance problem;
- evaluating only overall accuracy would not adequately represent model quality;
- imbalance treatment improves the model's ability to identify churned customers;
- resampling can materially affect classification performance;
- model selection should be performed using validation data rather than test data;
- F1-score and ROC-AUC provide complementary perspectives on model performance.

The final model successfully exceeds the project's minimum F1-score requirement.

## 🚀 Business Applications

A churn classification model can help financial institutions:

- identify customers with elevated churn risk;
- prioritize retention initiatives;
- target customers with personalized offers;
- support proactive customer-service actions;
- improve CRM segmentation;
- allocate retention resources more efficiently.

In a real production environment, churn probabilities could be integrated into CRM systems to support automated retention journeys.

## ⚠️ Limitations

The model identifies statistical relationships between customer characteristics and churn but does not establish causal relationships.

The analysis also does not explicitly incorporate:

- customer lifetime value;
- retention campaign costs;
- different financial costs for false positives and false negatives;
- changes in customer behavior over time.

A production implementation would require continuous monitoring, threshold optimization, and evaluation against business outcomes.

## 🛠️ Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Classification Models
- Upsampling
- F1-score
- ROC-AUC
- Jupyter Notebook

## 📁 Repository Structure

```text
bank-churn-imbalance-analysis/
│
├── README.md
│
├── data/
│   └── Churn.csv
│
└── notebook/
    └── bank_churn_imbalance_analysis.ipynb
```

## ▶️ Running the Project

Clone the repository and open the Jupyter Notebook located in the `notebook` directory.

The dataset is stored in the `data` directory.

The analysis requires **Python**, **Pandas**, **NumPy**, **Matplotlib**, and **Scikit-learn**.

---

### Author

**Brunno Almeida**

Data Science | Data Analytics | Python | SQL | Machine Learning
