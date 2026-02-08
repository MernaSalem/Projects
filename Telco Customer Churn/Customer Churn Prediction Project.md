## 1\. Project objective

The objective of this project was to develop a machine learning solution capable of predicting customer churn and identify the main factors contributing to customer attrition.  
Also to generate actionable insights that can support business decisions to improve customer retention.  
Customer churn prediction is a binary classification problem where the target variable represents whether a customer leaves the service (churn \= 1\) or remains active (churn \= 0).

## 2\. Data Understanding and Preparation

The project began with exploratory data analysis (EDA) to understand the dataset structure, feature distributions, and relationships between variables and churn behavior.

Key steps included:

* Identifying numerical and categorical features.  
* Handling missing values where applicable.  
* Encoding categorical variables for model compatibility.  
* Scaling numerical variables where required by algorithms.  
* Splitting the dataset into training and testing sets to ensure unbiased model evaluation.

During this phase, attention was given to class imbalance, which is common in churn datasets and directly affects model performance metrics.

## 3\. Feature Engineering and Analysis

Feature relationships were explored using correlation analysis and statistical inspection to identify variables with strong influence on churn behavior.

Important outcomes included:

* Identification of features strongly associated with customer retention or churn risk.  
* Creation of derived or grouped variables where useful for model interpretability.  
* Validation that selected features contributed meaningful predictive information rather than noise.

This stage ensured that the models learned meaningful patterns rather than overfitting to irrelevant signals.

## 

## 4\. Model Development

Multiple supervised learning models were implemented and evaluated, including:

* Decision Tree Classifier  
* Gradient Boosting-based model  
* Additional baseline comparisons where necessary

A pipeline approach was used to ensure consistent preprocessing and modeling steps across training and evaluation.

Model evaluation focused on metrics appropriate for churn prediction:

* Precision (how many predicted churners actually churned)  
* Recall (how many actual churners were successfully detected)  
* F1 Score (balance between precision and recall)  
* ROC-AUC for overall ranking performance

Given the business context, recall was treated as particularly important since failing to identify potential churners carries higher business cost.

## 5\. Model Evaluation and interpretation

After training, model outputs were analyzed beyond accuracy to understand decision behavior.

Key activities included:

* Threshold analysis to balance false positives and false negatives.  
* Performance comparison across models.  
* Model interpretation using SHAP values to identify feature importance and explain predictions.

This step transformed the model from a black box into a decision-support tool by showing which features most strongly influenced churn predictions.

### **5.1 Risk Segmentation Based on Model Probabilities**

Instead of relying only on binary churn predictions, the trained model produces a probability representing the likelihood of churn for each customer. These probabilities were used to group customers into three risk categories: Low Risk, Medium Risk, and High Risk. This segmentation translates model output into a business-oriented structure that supports decision-making and prioritization. By converting probabilities into risk levels, the analysis moves from prediction toward actionable insight.

### **5.2 Validation of Risk Segments**

To ensure that the risk segmentation was meaningful, the observed churn rate was evaluated within each risk group using the test dataset. The results showed a clear ordering, where customers classified as High Risk exhibited significantly higher actual churn rates compared to Medium and Low Risk groups. This validation step confirms that the predicted probabilities are aligned with real outcomes and that the model’s risk estimates can be reliably used for further interpretation and analysis.

### **5.3 Segment-Level Model Interpretation Using SHAP**

After validating the risk segmentation, SHAP (SHapley Additive exPlanations) analysis was applied specifically to the High-Risk customer segment. While global feature importance explains overall model behavior, segment-level interpretation focuses on understanding the factors driving churn among customers most likely to leave. This approach allows the identification of dominant churn drivers within the high-risk population, providing more targeted and actionable insights compared to global explanations alone. The analysis highlights which features contribute most strongly to increased churn probability within this segment, supporting more informed retention strategies.

## 6\. Key Findings

The project demonstrated that:

* Customer churn can be predicted with meaningful reliability using behavioral and demographic features.  
* Certain customer segments exhibit significantly higher churn probability.  
* Model interpretability techniques revealed actionable drivers behind churn rather than only providing predictions.

These insights enable targeted retention strategies instead of generalized marketing efforts.

