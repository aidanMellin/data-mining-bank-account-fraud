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

  1. session_lengths_in_minutes had several entries with a negative value, all being -1. This was likely a placeholder because the data wasn’t tracked.
  2.  device_distinct_emails_8w had a single negative value (-1). This was most likely a placeholder for no entry.

  *Side note of Data Cleanings*
    - payment_type had anonymized values falling into a pattern AA, AB, AC, AD, or AE for the sake of protecting private data. While these values aren’t able to really be extrapolated to new data, the values can still be used to show that there are trends with fraud based on specific payment type, though the specifics may not be known.
    - Intended_balcon_amount had primarily negative numbers (which doesn’t seem to make sense), so the column while not removed was essentially ignored when considering our data set using iloc.
   
  - While performing data cleaning, few missing values were encountered. These missing values were replaced by using the mean of the attribute.
    - previous_address_months_count
      - One missing value
    - current_address_months_count
      - One missing value
      - One zero value
    - bank_months_count
      - One missing value
 
- **EDA Related to Hypothesis**: 
  - Focused on age and income groups.
- **EDA Unrelated to Hypothesis**: 
  - Investigated the country of request origin and credit risk score.

---

### Data Mining Techniques

- **Random Forest**: 
  - Achieved an accuracy of approximately 98%.
  <img width="930" alt="image" src="https://github.com/aidanMellin/data-mining-bank-account-fraud/assets/50143737/b24c3f56-5106-48ad-a20d-bc0a1cb82558">

- **Neural Network (MLPClassifier)**: 
  - Resulted in a correctness of approximately 95.77%.
  <img width="989" alt="image" src="https://github.com/aidanMellin/data-mining-bank-account-fraud/assets/50143737/8b440790-b363-4077-b098-22b1f076828f">


---

### Findings

- **Accepted Hypotheses**: 
  - As income increases, the likelihood of falling victim to fraud increases.
  - As age increases, the likelihood of falling victim to fraud increases.
- **Key Insights**: 
  - ~75% of fraudulent applications were in their 30’s - 50’s.
  - Higher chances of fraud for requests originating from a foreign country.
  - Average valid applications had a Credit Risk Score of ~100, while fraudulent applications had ~200.
 
### Key Graphs

- EDA Related to Hypothesis:  
  1.  Hypothesis: As age increases, the likelihood of falling victim to fraud increases.
    - Description: Proportion of Total Valid/Total Fraud Applications per Age Group  
        - ~75% of fraudulent applications were in their 30’s - 50’s
        - From the second graph we see that risk of fraud increases with age.
        - A comparatively much higher proportion of applicants in their 90’s are victims of
fraud than applicants in their late teens or 20’s.
    - Results: Based on our findings, we are accepting our initial hypothesis that as age increases, the likelihood of falling victim to fraud increases.
        - As demonstrated in the graphs below, the proportion of fraudulent applications steadily increases with age. Graph 2 gives a good visual representation of the steady increase in fraudulent applications based on age group. 
  <img width="627" alt="image" src="https://github.com/aidanMellin/data-mining-bank-account-fraud/assets/50143737/079757bb-889e-4631-a571-20bd52a9a7b3">

  <img width="586" alt="image" src="https://github.com/aidanMellin/data-mining-bank-account-fraud/assets/50143737/42f70ef1-105b-4dff-851b-937b377b2bad">

  2. Hypothesis: As income increases, the likelihood of falling victim to fraud for a number of reasons (including but not limited to the chance of being approved for an account) increases.
    - Description: Proportion of Total Valid Applications per Income Group
      - Supports our hypothesis that as income increases, the chance of fraud increases.
      - Fraud levels at their highest in group 0.9, but still relevant in groups 0.1, 0.6, 0.7, and 0.8.
    - Results:
      - Based on our findings, we are accepting our initial hypothesis that as income increases, the likelihood of falling victim to fraud increases.
      - As we can see in our graphs, fraud levels are definitely at their highest in group0.9 (the highest income group).
      - Relating back to our initial question of finding a correlation between income and fraud, it is important to note that fraud levels are still relevant in groups 0.1, 0.6, 0.7, and 0.8.

<img width="1029" alt="image" src="https://github.com/aidanMellin/data-mining-bank-account-fraud/assets/50143737/64132f73-4372-429c-920d-303db32c3ca3">

- EDA unrelated to Hypothesis:
  1. Proportion of Total Valid/Total Fraud Applications per Credit Risk Score
    - Average valid application seems to have a CRS of ~100 while the average fraudulent application is ~200.

  <img width="828" alt="image" src="https://github.com/aidanMellin/data-mining-bank-account-fraud/assets/50143737/eee870e6-8e21-41df-8cf6-86ec3fbe56d9">

---

## Getting Started

To replicate this analysis, you will need to:

1. Clone the repository.
2. Install the required Python packages.
3. Run the Jupyter notebook.

For more details, please refer to the Jupyter notebook included in this repository.

