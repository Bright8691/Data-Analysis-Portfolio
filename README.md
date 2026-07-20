# :  Cross-Border Transaction Fraud Detection and Risk Analysis Using Python End-to-End Machine Learning

Project Overview
Financial fraud is a major challenge for banks, payment service providers, and e-commerce platforms. In order to minimize financial losses, maintain trust of the customers and be stable in business it is pertinent to quickly and accurately detect fraudulent transactions.
End-to-End fraud Detecting System was used to apply machine learning techniques to identify fraudulent transactions. The project also covers the major data science lifecycle which if from data understand and exploratory, data preprocessing and feature engineering, model development, evaluation and deployment, threshold optimization, business interpretation and business intelligence report using Power BI.
Business Problem
Fraud in financial institutions can cause great financial losses, instability and ruin long term reputation of the institution. Thus, the objective of this project is to evaluate and develop a learning model capable to identify fraud and balance false positives with fraudulent transactions.
Data
The dataset contains some transaction records and are not limited to the following:
•	Transaction Identification
•	Customer Identification
•	Home Country
•	Channel 
•	Transaction Amount                  
•	Bank Charge 
•	Transaction Currency
•	Device Identification
•	IP Address
•	Country IP                   
•	Location Mismatch              
•	IP Risk Score                  
•	Account Age               
•	Device Trust Score           
•	Charge Back History      
•	Internal Risk Score          
•	Transaction Velocity               
•	Fraud Label (is_fraud )   
Target Variable: is_fraud  
•	0 = Legitimate Transaction
•	1 = Fraudulent Transaction

Technologies Used
Programming Language 
•	Python 3.13.9
Libraries
•	Pandas
•	NumPy
•	Matplotlib
•	Scikit-learn
•	XGBoost
•	Joblib
Business Intelligence
•	Microsoft Power BI
Development Environment
•	Jupyter Notebook
Project Workflow
An end-to-end machine learning pipeline which consists of 8 major phases was use to evaluate and develop the model
Phase 1 – Project Setup & Data Collection
•	Import libraries
•	Load dataset
________________________________________
Phase 2 – Data Understanding & Exploration
•	Dataset inspection
•	Missing value analysis
•	Duplicate detection
•	Summary statistics
•	Exploratory Data Analysis (EDA)
•	Fraud distribution
•	Correlation analysis

Phase 3 – Data Preprocessing & Feature Engineering
•	Handle missing values
•	Remove duplicates
•	Data type conversion
•	Outlier treatment
•	Feature engineering
•	Train-test split
•	Data transformation
•	Preprocessing pipeline

Phase 4 – Model Development
Machine learning models evaluated:
•	Logistic Regression
•	Decision Tree
•	Random Forest
•	XGBoost
Model optimization:
•	Hyperparameter tuning
•	Cross-validation

Phase 5 – Model Evaluation
Evaluation metrics:
•	Accuracy
•	Precision
•	Recall
•	F1-score
•	ROC-AUC
•	Precision-Recall Curve
•	Confusion Matrix
•	Threshold Optimization

Phase 6 – Model Deployment
•	Save trained model
•	Load model
•	Predict new transactions

Phase 7 – Business Interpretation
•	Model limitations
•	Business recommendations

Phase 8 – Project Conclusion
Which summarized the findings and discuss future improvements.

Machine Learning Workflow
Raw Data
|
V
Data Cleaning
|
V
Exploratory Data Analysis
|
V
Feature Engineering
|
V
Train-Test Split
|
V
Preprocessing Pipeline
|
V
Model Training
|
V
Model Evaluation
|
V
Threshold Optimization
|
V
Model Development
|
V
Power BI Dashboard
The interactive dashboard provides insights into transaction activity and fraud trends



# Executive KPIs
•	Total Transaction
•	Total Fraud
•	Fraud Rate
•	Total Transaction Amount
•	Fraud Loss Amount
•	Legit Transaction
•	Average Fraud
Dashboard Visualizations
•	Fraud vs Legitimate Transactions
•	Total Fraud by Month
•	Fraud and Legitimate Transaction by Type
•	Fraud Loss by  Channel
•	Fraud transaction by Country
•	Fraud by Device Type
•	Logistic Regression Model
 
# Dashboard Preview
 
<img width="300" height="160" alt="fraud_powerbi" src="https://github.com/user-attachments/assets/630619fb-da32-4f64-82b0-7c68fa2243d9" />
  
# Model Performance
The result of the model development. Logistic Regression model was selected as the best model in  fraud detection.
|	Model				|	Accuracy	|	Precision	|	Recall		|	F1		|	ROC_AUC |
|-----------------------|---------------|---------------|---------------|-----------|-----------|
|	Logistic Regression	| 	0.6535		|	0.0407		|	0.7435		|	0.0772	|	0.7468  |
|	Decision Tree		|	0.7160		|	0.0318		|	0.4615		|	0.0596	|	0.5864  |
|	Random Forest		|	0.9730		|	0.0588		|	0.0256		|	0.0357	|	0.6898  |
|	XGBoost				|	0.9805		|	0.0000		|	0.0000		|	0.0000	|	0.0000  |

						
Why Choose Logistic Regression?

In fraud detection, accuracy is not the most important metric because fraud is an imbalance classification problem. 
•	Random Forest achieved 97.35% accuracy
•	XGBoost achieved 98.05% accuracy
A closer look on the table they have the following:
•	Precision = 0
•	Recall = 0
•	F1 = 0

Which means they did not identify a single fraudulent transaction. They simply predicted every transaction as legitimate because fraud cases are rare. As such they are not the best for fraud detection.

# Logistic Regression

The Logistic Regression achieved:
•	Accuracy = 65.40%
•	Precision = 4.07%
•	Recall = 74.35%
•	F1-score = 7.73%
•	ROC-AUC = 0.7452 (highest)

This means it successfully detected about 74% of fraudulent transactions, which is generally the priority in fraud detection. Although it generated many false positives (low precision), suspicious transactions can often be reviewed manually or subjected to additional verification. Missing fraud is usually more costly than investigating legitimate transactions.

# Threshold Selection
Several classification thresholds were evaluated. Although higher thresholds improved Precision, they also reduced Recall substantially. A threshold of 0.50 was selected because it met the objective of the project, fraud detection. 

# ROC Curve

<img width="800" height="800" alt="roc_curve" src="https://github.com/user-attachments/assets/78c1fb23-b74e-4b2d-814b-c976da26e5ab" />

AUC = 0.68
This indicates poor-to-moderate predicting power. The Random Forest model  with AUC of 0.69 is underperforming and can not be reliable in decision-making. That is why Logistic Regression with AUC of 0.75 was selected

# Confusion Matrix

<img width="800" height="800" alt="confusion_matrix_logisticRegression" src="https://github.com/user-attachments/assets/e5e99472-39eb-462d-b002-0c10ce28c489" />

Matrix Breakdown
•	1278 (True Negatives) Legitimate transaction predicted
•	683 (False Positives) incorrectly flagged Legitimate transaction as Fraud
•	10 (False Negatives) incorrectly missed Fraud transaction labelled as Legitimate
•	29 (True Positives)

Accuracy: 65.40% == The model correctly predicted 1,307(True Legitimate) out of 2,000 transactions.
Recall : 74.36 == The model detected 29 fraud cases out of 39 actual fraud cases, and loss 10
Precision: 4.07% == Which means out of the 712 times, it was only 29 times was the true fraud. 
Please Note: For the purpose of the project no further modelling was evaluated to improve prediction model

# Precision Recall

 <img width="800" height="800" alt="precision_recall_curve" src="https://github.com/user-attachments/assets/e2d03785-d1c2-41a8-b6ee-d41c5325f6ef" />

 Precision = 0.04
 
This is low, because the maximum is 1.0.  This means that the model is performing no better random guessing the in fraud prediction

How to Run This Project
Clone the repository:
git clone https://github.com/Bright8691/Fraud-Detection-System.git
Navigate to the project directory:
cd Fraud-Detection-System
Install dependencies:
pip install -r requirements.txt
Open the notebook:
Jupyter notebook
Run the notebook from top to bottom.

# Skills Demonstrated

•	Data Cleaning & Preprocessing
•	Exploratory Data Analysis (EDA)
•	Feature Engineering
•	Machine Learning Classification
•	Model Evaluation
•	Hyperparameter Tuning
•	Threshold Optimization
•	Model Deployment
•	Power BI Dashboard Development
•	Business Intelligence Reporting

 Author
Bright C Egbuchulem
Data Analyst | Machine Learning Enthusiast | Civil Engineer
•	GitHub: https://github.com/Bright8691
•	Email: bc.egbuchulem@gmail.com

# Observations
During the investigation, i discovered that there are 37 Unknow Transaction in the channel column.
36 ====> Legitimate Transaction
1 ======> Fraud
This represents less than 0.5% of the dataset.
Since it contained both legitimate and fraudulent transactions, i have to keep it 

During the investigation, i discovered that there are 32 Unknow Transaction in the home_country column.
31 ====> Legitimate Transaction
1 ======> Fraud
This represents less than 0.5% of the dataset.
Since it contained both legitimate and fraudulent transactions, i have to keep it 

