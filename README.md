## 1. Introduction
This project focuses on detecting online payment fraud for Blossom Bank (BBL PLC), a multinational financial services group headquartered in London, UK. With the increasing prevalence of digital transactions, the risk of fraudulent activities has risen dramatically. Effective fraud detection is crucial for safeguarding both the bank's assets and its customers' financial security. By leveraging advanced machine learning techniques and data analytics, this project aims to develop a robust system that identifies and mitigates fraudulent transactions in real-time, ensuring a secure banking experience for all users.

## 2. Dataset
Data used in this project can be downloaded from this link: https://drive.google.com/file/d/1ZIjmAjPccvy16mOk7nrPtWe-_3rRP5zy/view?usp=sharing
![image](https://github.com/user-attachments/assets/48e098be-f0a6-4410-875a-cfa620caeb8f)

It consists of 1048575 rows and 10 columns, in which 1047433 rows are nonfraud cases and the other 1142 rows are fraud cases.
## 3. Exploratory Data Analysis
- The online payment transaction of Blossom Bank mostly in cashout service, following by payment, cashin, transfer, and debit.

![image](https://github.com/user-attachments/assets/c74d9811-5533-4c1c-9e82-92ab5386af42)

- In this data, the distribution of nonfraud and fraud cases is heavily imbalanced, which fraud case is only 0.11% of total data while nonfraud case consists of 99.89% of total data.

![image](https://github.com/user-attachments/assets/7698679c-dfbe-40cc-b58f-24ce774dae81)

- For fraud case, the fraud amount is between 119 and 10000000 and the average is 1192628.93.
![image](https://github.com/user-attachments/assets/3daa58ba-7dd5-4e63-a4c7-5469aa28fc74)

- The fraud cases usually happen in these two services: cashout and transfer.
![image](https://github.com/user-attachments/assets/f28c8e7c-f92e-4365-8240-810484bd31ac)

## 4. Models & Results
### 4.1 Data Preparation
Before applying the models, we perform several essential data preparation steps. 
- First, we remove unnecessary columns, such as "nameOrig" and "nameDest," to streamline the dataset and enhance model performance.
- Next, we convert the "type" column from an object datatype to integers using one-hot encoding, which transforms categorical variables into a format suitable for machine learning algorithms.
- Lastly, we divide data into training and testing with a ratio of 80-20%.
### 4.2 Models 
We apply two models for fraud detection classification: Random Forest and XGBoost. Given the imbalanced nature of the dataset, we will implement both undersampling and oversampling techniques to address this issue. By comparing the results from these approaches, we aim to determine the most effective method for improving model performance and accurately identifying fraudulent transactions. The models will be evaluated by several important metrics including precision, recall, f1-score, and roc curve.
### 4.3 Results
Based on the evaluation metrics, the XGBoost model utilizing the undersampling technique demonstrated superior performance, achieving an AUC of 1.00, a precision of 0.98, a recall of 1.00, and an F1-score of 0.99 for fraud detection. These results indicate that the model effectively identifies fraudulent cases with a high degree of accuracy and minimal false positives.

The performance metrics for both models across different techniques are summarized in the table below:

![image](https://github.com/user-attachments/assets/abee235d-fd66-4e7c-84e2-54cf8696ef6a)

![image](https://github.com/user-attachments/assets/6db1d583-cd97-4d86-b59c-714f7c8fb12e)

![image](https://github.com/user-attachments/assets/01fc0675-ce22-4070-a848-77b346f459c3)

![image](https://github.com/user-attachments/assets/f0f4b602-0696-4344-879a-047d4d5e6d9c)

## 5. Conclusion
The analysis reveals that the XGBoost model with the undersampling technique is the most effective approach for detecting fraudulent transactions in this dataset. Its high AUC, precision, recall, and F1-score highlight its ability to accurately identify fraud while minimizing false positives. In contrast, while Random Forest also showed competitive results, it did not match the performance of XGBoost under similar conditions. These findings underscore the importance of model selection and the impact of data preprocessing techniques in achieving optimal results in fraud detection tasks. Future work could explore additional feature engineering and other advanced techniques to further enhance detection capabilities.
