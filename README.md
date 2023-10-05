# README: Bank Account Fraud Detection

## Overview

This project aims to detect and analyze trends in bank account fraud. The analysis is based on the Bank Account Fraud Dataset Suite (NeurIPS 2022) and employs various data mining techniques like Random Forest and Neural Networks along with Exploratory Data Analysis (EDA).

## Table of Contents

1. [Project Design and Outline](#project-design-and-outline)
2. [Preprocessing and EDA](#preprocessing-and-eda)
3. [Data Mining Techniques](#data-mining-techniques)
4. [Findings](#findings)

---

### Project Design and Outline

- **Dataset**: [Bank Account Fraud Dataset Suite (NeurIPS 2022)](https://www.kaggle.com/datasets/sgpjesus/bank-account-fraud-dataset-neurips-2022?select=Base.csv)
- **Questions/Hypotheses**: 
  - Vulnerable demographics for victims of fraud.
  - Correlation between income and fraud.
  - Success rate of different fraud tactics.

---

### Preprocessing and EDA

- **Data Cleaning and Manipulation**: 
  - Negative values set to zero.
  - Missing values replaced with the mean of the attribute.
- **EDA Related to Hypothesis**: 
  - Focused on age and income groups.
- **EDA Unrelated to Hypothesis**: 
  - Investigated the country of request origin and credit risk score.

---

### Data Mining Techniques

- **Random Forest**: 
  - Achieved an accuracy of approximately 98%.
- **Neural Network (MLPClassifier)**: 
  - Resulted in a correctness of approximately 95.77%.

---

### Findings

- **Accepted Hypotheses**: 
  - As income increases, the likelihood of falling victim to fraud increases.
  - As age increases, the likelihood of falling victim to fraud increases.
- **Key Insights**: 
  - ~75% of fraudulent applications were in their 30’s - 50’s.
  - Higher chances of fraud for requests originating from a foreign country.
  - Average valid applications had a Credit Risk Score of ~100, while fraudulent applications had ~200.

---

## Getting Started

To replicate this analysis, you will need to:

1. Clone the repository.
2. Install the required Python packages.
3. Run the Jupyter notebook.

For more details, please refer to the Jupyter notebook included in this repository.

