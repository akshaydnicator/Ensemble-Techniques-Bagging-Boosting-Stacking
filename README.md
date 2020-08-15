# Using Bagging, Boosting and Stacking Ensemble Learning Techniques to Predict Loan Eligibility of the Applicants

## Problem Statement
Dream Housing Finance company wants to automate the loan eligibility process (real time) based on customer detail provided while filling online application form. These details are Gender, Marital Status, Education, Number of Dependents, Income, Loan Amount, Credit History and others. To automate this process, they have provided a dataset to identify the customers segments that are eligible for loan amount so that they can specifically target these customers. The company deals in all kinds of home loans. They have presence across all urban, semi urban and rural areas. Customer first applies for home loan and after that company validates the customer eligibility for loan.

## Data Description
 **Train file:** CSV containing the data for 614 customers for whom loan eligibility is known as 'Loan_Status<br/>
 **Test file:** CSV containing the data for 367 customers for whom loan eligibility is to be predicted<br/><br/>
 **Train Variables Description**<br/>
 ![Train variables](https://github.com/akshaydnicator/Ensemble-Techniques-Bagging-Boosting-Stacking/blob/master/Train%20variables%20screenshot.jpg)<br/>
 **Test Variables Description**<br/>
 ![Test variables](https://github.com/akshaydnicator/Ensemble-Techniques-Bagging-Boosting-Stacking/blob/master/Test%20variables%20screenshot.png)<br/>

## Approach and Implementation
Both the training and test file tweets have been pre-processed using one standardized process as given below:
 - Converting the categorical variables into numerics and make adjustments for the null values
 - Using **Principal Component Analysis (PCA)** to reduce the dimensions of the input variables and using it further for the predictive analytics<br/>

After pre-processing, the data is used as input for training various **ML/DL ensemble models** mainly using the following techniques:<br/><br/>
**1.    Bagging Algorithms:** Bagging meta-estimator using **(i) Max Voting, (ii) Averaging and (iii) Weighted Average | Classifiers: BaggingClassifier(), DecisionTreeClassifier() and RandomForestClassifier() <br/><br/>**
**2.    Boosting Algorithms:** Combining a number of weak learners to form a strong learner and using **GridSearchCV** to find the **best estimate parameters** for the respective models to be used in an ensemble **| Algorithms: AdaBoostClassifier(), GradientBoostingClassifier(), XGBClassifier(), Light GBM and CatBoostClassifier()<br/><br/>**
**3.    Stacking Ensemble Techniques:** Using **StratifiedKfold** to split the train data into 10 subsets and using **Bootstrapping** techniques to create an output to be used as **features in the final meta-classifier | Additional models** used apart from the ones mentioned above: **LinearSVC(), KNeighborsClassifier(), LogisticRegression(), VotingClassifier() and Deep Neural Networks (DNNs)<br/>**
 
## Models Used and Evaluation
The are three different notebooks attached in this repository as a part of this project:<br/><br/>
 - **Principal Component Analysis on Train/Test Data**
 - **Bagging and Boosting Machine Learning Ensemble Techniques**
 - **Stacking Ensemble Techinique - ML Models Stacked Over DNN**
