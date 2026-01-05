# ml-bank-campaign-effectiveness-analysis
Predicting term deposit subscriptions using classification models (Logistic Regression, KNN, Decision Trees, SVM). Comparative analysis of model performance and hyperparameter tuning. Developed as part of the UC Berkeley Professional Certificate in Machine Learning and Artificial Intelligence.

## Project Overview
This project anlyzes a dataset that represents the outcomes of 17 direct marketing campaigns carried out by a Portuguese bank. These campaigns involved direct marketing using phone calls, conducted between May 2008 and November 2010, with each record corresponding to a client contact attempt and its result (client suscribed for term-deposit or not). The objective is to provide actionable insights to improve the efficiency of marketing campaigns.

**Full analysis and code:**  
👉 [Jupyter Notebook – Bank Campaign Effectiveness Analysis](./ml-bank-campaign-effectiveness-analysis.ipynb)

## Business Objective
The business objective of this task is to help a bank institution improve the effectiveness of its direct marketing via phone by predicting whether a customer will subscribe to a long-term deposit. By using historical marketing data and customer attributes, the goal is to identify main characterstics that effect the success rate, helping bank instiution in a better management of available resources and selection of a high quality and affordable set of potential buying customers.

## Data Understanding
In this application, a dataset from the UCI Machine Learning repository is used. The data is from a Portugese banking institution and is a collection of the results of multiple marketing campaigns. The data represents the outcomes of 17 direct marketing campaigns carried out by a Portuguese bank. These campaigns involved direct marketing using phone calls, conducted between May 2008 and November 2010, with each record corresponding to a client contact attempt and its result.
* There are no missing or NaN values in the dataset
* The target variable falls into binary classification with values 'yes' and 'no'. So it requires appropriate numeric mapping (like 0-no, 1-yes)
* There are no exterme outliers or anomolies

## Data Preparation
* The feature "duration" from the dataset is not known before a call is performed. Also, after the end of the call the result (yes or no) is obviously known. Hence, the duration is removed from the dataset to prepare a realistic predictive model.
* Encoded output variable (y) - 'no' to 0 and 'yes' to 1 to represent in numerical form.

## Modeling
* Following classification models were trained and evaluated on the same test dataset:
  * Logistic Regression
  * K-Nearest Neighbors (KNN)
  * Decision Trees
  * Support Vector Machines (SVM)
* To compare the performance of the regression models, the following metrics were used:
  * Training accuracy score
  * Test accuaracy score
  * Training Time

## Evaluation
* Based on the results, Logistic Regression with tuned hyperparameters is selected as the final model. It achieved higher test accuracy, faster execution and minimal overfitting.
  
## Deployment
### Findings
* Campaign timing significantly impacts the success rate. Marketing efforts are more effective in the month of March and less effective in the months of May and November.
* Customers are less likely to commit term deposits during higher employment activity and higher interest rates, possibly due to alternate spend and invenstment channels.
* Customers are more likely to respond positively when communicated via mobile phones than landline phones. Marketing should aim to prioratize such contact methods.
* Repetitive contacts during the same campaign period are less effective.

### Future Improvements & Next Steps

While the Logistic Regression model achieved high accuracy, the **Confusion Matrix** revealed a potential for improvement by focusing on **Recall**.

* **Optimize for Recall:** Currently, the model is balanced for accuracy. In a business context, missing a potential subscriber (False Negative) is more costlier than calling a non-subscriber. Future iterations will use **Precision-Recall Curves** to tune the model.
* **Feature Engineering:** Based on the high success rate in March, I recommend creating seasonal features to better capture timing based customer behaviors.


