# Using Bagging, Boosting and Stacking Ensemble Learning Techniques to Predict Loan Eligibility of the Applicants

## Problem Statement
Dream Housing Finance company wants to automate the loan eligibility process (real time) based on customer detail provided while filling online application form. These details are Gender, Marital Status, Education, Number of Dependents, Income, Loan Amount, Credit History and others. To automate this process, they have provided a dataset to identify the customers segments that are eligible for loan amount so that they can specifically target these customers. The company deals in all kinds of home loans. They have presence across all urban, semi urban and rural areas. Customer first applies for home loan and after that company validates the customer eligibility for loan.

## Data Description
 **Train file:** CSV containing the data for 614 customers for whom loan eligibility is known as 'Loan_Status<br/>
 **Test file:** CSV containing the data for 367 customers for whom loan eligibility is to be predicted<br/><br/>
 **Train Variables Description**<br/>
 ![Train variables](https://github.com/akshaydnicator/Ensemble-Techniques-Bagging-Boosting-Stacking/blob/master/Train%20variables%20screenshot.jpg)<br/>
 **Test Variables Description**<br/>
 ![Test variables](https://github.com/akshaydnicator/Ensemble-Techniques-Bagging-Boosting-Stacking/blob/master/Test%20variables%20screenshot.png)<br/><br/>

## Approach and Implementation
Both the training and test file tweets have been pre-processed using one standardized process as given below:
 - Converting the categorical variables into numerics and make adjustments for the null values
 - Using **Principal Component Analysis (PCA)** to reduce the dimensions of the input variables and using it further for the predictive analytics
 <br/>
 After pre-processing, the data is used as input for training various **ML/DL ensemble models** mainly using the following techniques:<br/>
 1. Bagging<br/>
 2. Boosting<br/>
 3. Stacking<br/>
 
 

