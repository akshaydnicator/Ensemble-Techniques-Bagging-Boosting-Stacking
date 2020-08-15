# Bagging, Boosting and Stacking Ensemble Learning Techniques to Predict Loan Eligibility of the Applicants

## Problem Statement
Dream Housing Finance **company wants to automate the loan eligibility process (real time) based on customer detail provided while filling online application form**. These details are Gender, Marital Status, Education, Number of Dependents, Income, Loan Amount, Credit History and others. To automate this process, they have provided a dataset to identify the customers segments that are eligible for loan amount so that they can specifically target these customers. The company deals in all kinds of home loans. They have presence across all urban, semi urban and rural areas. Customer first applies for home loan and after that company validates the customer eligibility for loan.

## Data Description
 **Train file:** CSV containing the data for **614 customers** for whom loan eligibility is known as 'Loan_Status<br/>
 **Test file:** CSV containing the data for **367 customers** for whom loan eligibility is to be predicted<br/><br/>
 **Train Variables Description**<br/>
 ![Train variables](https://github.com/akshaydnicator/Ensemble-Techniques-Bagging-Boosting-Stacking/blob/master/Screenshots/Train%20variables%20screenshot.jpg)<br/>
 **Test Variables Description**<br/>
 ![Test variables](https://github.com/akshaydnicator/Ensemble-Techniques-Bagging-Boosting-Stacking/blob/master/Screenshots/Test%20variables%20screenshot.png)<br/>


## Approach and Implementation
Both the training and test file tweets have been **pre-processed** using one standardized process as given below:
 - Converting the categorical variables into numerics and make adjustments for the null values
 - Using **Principal Component Analysis (PCA)** to reduce the dimensions of the input variables and using it further for the predictive analytics<br/>

After pre-processing, the data is used as input for training various **ML/DL ensemble models** mainly using the following techniques:<br/><br/>
**1.  Bagging Algorithms:** Bagging meta-estimator using **(i) Max Voting, (ii) Averaging and (iii) Weighted Average | Algorithms: BaggingClassifier(), DecisionTreeClassifier() and RandomForestClassifier() <br/><br/>**
**2.  Boosting Algorithms:** Combining a number of weak learners to form a strong learner and employing **GridSearchCV** to find the **best estimate parameters** for the respective models using  **multiprocessing | Algorithms: AdaBoostClassifier(), GradientBoostingClassifier(), XGBClassifier(), Light GBM and CatBoostClassifier()<br/><br/>**
**3.  Stacking Ensemble Techniques:** Using **StratifiedKfold** to split the train data into 10 subsets and using **Bootstrapping** techniques to create an output to be used as **features in the final meta-classifier | Additional models** used apart from the ones mentioned above: **LinearSVC(), KNeighborsClassifier(), LogisticRegression(), VotingClassifier() and Deep Neural Networks (DNNs)<br/>**
 
## Analysis and Evaluation
The are three different jupyter notebooks attached in this repository as a part of this project:<br/>
 - Principal Component Analysis **(PCA)** on Train-Test Data
 - **Bagging and Boosting** Machine Learning Ensemble Techniques
 - **Ensemble Stacking ML models Over a DNN** - Loan Eligibility Prediction<br/>

For **Bagging and Boosting ensemble techniques**, mainly ML and Ensemble classifiers were used to create independent predictions on the dataset and thereby selecting the best model using GridSearchCV. After all the models have been trained and best model parameters have been identified, the final predictions are made using ensemble model created by assigning best trained models to the VotingClassifier() as estimators. Here, the Max Voting, Averaging and Weighted Average was used to find the best combination of the models in the ensemble.<br/><br/>
For **Stacking ML models on the DNN, BootStrapping technique** was employed using **StratifiedKfold**, whereby a number of weak ML models are trained on train set, and the holdout validation set and test set are used for making new predictions at each fold. This process allows the maximum usage of limited amount of data as the model gets to train on all of the training set. Moreover, as the **predictions are made on the cross validation sets**, it upholds the integrity of the learning process as the model does not get to see the validation data until the predictions are made. The predictions on train validation set and test set are obtained from all of the selected 10 models. In order to improve the efficiency of the model learning process, **PCA** is done further on the output of the ML algorithms and the dimensions of the data is reduced to 5 principal components. Finally, **these PCs are used as input features in the DNN.** The final output obtained from this DNN is considered as the final predictions obtained from the stacking ensemble.          

# Result
A variation of different combinations of ensemble modeling techniques led to the **highest f1 score of 81.25** on the test dataset and it **ranked #46 on public leaderboard** as on August 16, 2020 with 61,886 total number of participants having made 7,426 number of unique submissions.

# Acknowlegdement
Many snippets of the code used may have been taken from other open GitHub repositories to ease the rapid production and pace up the flow in the competition. It is acknowledged here that the inpiration has been taken from multiple sources. I am thankful to all of them for their mentorship and help.
