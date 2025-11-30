# fraud_detection_project
Healthcare Provider Fraud Detection using Machine Learning - Medicare Claims Analysis

Project Overview

This project aims to detect fraudulent healthcare providers within Medicare claims data using machine learning techniques. Fraudulent healthcare providers often engage in activities such as billing for non-rendered services, upcoding, and submitting claims for deceased patients, which significantly impacts the healthcare system. The model developed in this project seeks to assist investigators by automating the process of fraud detection, reducing manual investigation efforts and improving the detection accuracy.

Objectives:

Detect fraudulent providers in the U.S. Medicare system using machine learning models.

Handle class imbalance using techniques like SMOTE (Synthetic Minority Over-sampling Technique).

Evaluate the model's performance using metrics like Precision, Recall, F1-Score, ROC-AUC, and PR-AUC.

Scope:

This project involves data exploration, feature engineering, model training, and evaluation. The final model provides an automated solution for detecting fraud, aiming to reduce false positives and ensure a more accurate fraud detection process.

Team Members

Habiba: Data Exploration & EDA Lead

Responsibilities: Loading datasets, cleaning, handling missing data, performing exploratory data analysis (EDA), and generating insights.

Menna: Model Selection & Training

Responsibilities: Selecting and training machine learning models (Logistic Regression, Random Forest, Gradient Boosting), handling class imbalance, and tuning hyperparameters.

Malak: Model Evaluation & Error Analysis

Responsibilities: Evaluating model performance, computing metrics (e.g., Precision, Recall, F1-Score), and performing error analysis (false positives and false negatives).

Moussa: Report Writing & Documentation & Business Impact & Presentation Design

Responsibilities: Writing the project documentation, creating the report, summarizing the results for technical review and designing the presentation.

Summary of Results

Best Model: Gradient Boosting outperformed other models in terms of Precision, Recall, F1-Score, ROC-AUC, and PR-AUC.

Model Performance:

Precision: 0.80

Recall: 0.80

F1-Score: 0.80

ROC-AUC: 0.85

PR-AUC: 0.81

Key Features: Important features for predicting fraud included reimbursement amount, number of claims, and provider age.

Key Insights:

False Positives: Legitimate providers incorrectly flagged as fraudulent. This can lead to unnecessary investigations.

False Negatives: Fraudulent providers missed by the model. This could result in missed fraud cases and significant financial losses.

Business Impact:

Efficiency: Automating fraud detection reduces the burden on investigators by prioritizing high-risk providers.

Cost Savings: Identifying fraudulent providers early can help save significant resources in healthcare spending.

Scalability: The model can be deployed in real-time systems for continuous monitoring of healthcare claims.

Reproduction Instructions

To reproduce the results and run the project, follow these steps:

1. Prerequisites

Ensure you have the following installed:

Python 3.10+

Libraries:

pandas

numpy

matplotlib

seaborn

sklearn

imbalanced-learn (for SMOTE)

pickle (for model saving/loading)

2. Install Dependencies

Clone the repository and create a virtual environment:

git clone <repository-url>
cd healthcare-fraud-detection
conda create -n fraud-detection-env python=3.x
conda activate fraud-detection-env
pip install -r requirements.txt


Alternatively, if you're using pip, you can install the libraries directly:

pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn

3. Data Preparation

Ensure you have access to the data files:

Train_Beneficiarydata.csv

Train_Inpatientdata.csv

Train_Outpatientdata.csv

Train_Labels.csv

Place these files in the ../data/raw/ directory (adjust the path in the code if necessary).

4. Running the Code

Preprocessing: The first notebook (01_data_exploration_and_feature_engineering.ipynb) loads the data, explores it, and performs feature engineering.

Run all cells to prepare the data for modeling.

Modeling: The second notebook (02_modeling.ipynb) handles the training of multiple machine learning models (Logistic Regression, Random Forest, Gradient Boosting, etc.).

Run all cells to train the models, evaluate their performance, and save the best model.

Evaluation: The third notebook (03_evaluation.ipynb) evaluates the best model using metrics such as Precision, Recall, ROC-AUC, and PR-AUC.

Run all cells to generate the evaluation metrics and analyze the errors.

5. Saving and Loading Models

To save the trained model:

with open("best_model.pkl", "wb") as f:
    pickle.dump(best_model, f)


To load the saved model:

with open("best_model.pkl", "rb") as f:
    best_model = pickle.load(f)