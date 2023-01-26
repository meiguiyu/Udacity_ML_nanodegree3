*NOTE:* This file is a template that you can use to create the README for your project. The *TODO* comments below will highlight the information you should be sure to include.

# Your Project Title Here

*TODO:* Write a short introduction to your project.<br/><br/>
This project aims to predict churn rate for a customer. Both autoML and hyperparamter tuning will be used
to train this data set. Only the model with better accuracy will be deployed. 

## Dataset

### Overview
*TODO*: Explain about the data you are using and where you got it from.<br/><br/>
This dataset is randomly collected from an Iranian telecom companyâ€™s database over a period of 12 months. A total of 3150 rows of data, each representing a customer, bear information for 13 columns. The attributes that are in this dataset
are call failures, frequency of SMS, number of complaints, number of distinct calls, subscription length, age group, the charge amount, type of service, seconds of use, status, frequency of use, and Customer Value.

All of the attributes except for attribute churn is the aggregated data of the first 9 months. The churn labels are the state of the customers at the end of 12 months. The three months is the designated planning gap.

Data can be download using this url: https://archive.ics.uci.edu/ml/machine-learning-databases/00592/Churn_Dateset.csv.

### Task
*TODO*: Explain the task you are going to be solving with this dataset and the features you will be using for it.<br/><br/>
I am going to build a classification model using feature age, Systolic Blood Pressure as SystolicBP, Diastolic BP as DiastolicBP, Blood Sugar as BS, Body Temperature as BodyTemp, HeartRate and RiskLevel. 
to predict is a woman is in high risk of getting maternal mortality.

### Access
*TODO*: Explain how you are accessing the data in your workspace.<br/><br/>
The data set has been uploaded to the workspace and registered used key "Churn". 
This data can be accessed using below code.<br/><br/>
*Figure 1-1: Access Data*
![plot1](./images/0-1.PNG)
<br/><br/>
*Figure 1-2: Access Data*
![plot1](./images/0-2.PNG)
<br/><br/>

## Automated ML
*TODO*: Give an overview of the `automl` settings and configuration you used for this experiment<br/><br/>
The automl settings and configuraiton can be found in below figure.  <br/><br/>
*Figure 2: Automl settings*
![plot2](./images/2-1.PNG)


### Results
*TODO*: What are the results you got with your automated ML model? What were the parameters of the model? How could you have improved it?

*TODO* Remeber to provide screenshots of the `RunDetails` widget as well as a screenshot of the best model trained with it's parameters.<br/><br/>

The best automodel is a voting ensemble model with an accuracy of 0.9581. 
We can add a k-fold cross validation in the automl settings to improve the model accuracy.

Below figure shows the results of automl model.  <br/><br/>
*Figure 3: Training results*
![plot3](./images/2-2.PNG)
<br/><br/>
Below figure shows the the run details of the automl model.  <br/><br/>
*Figure 4: Run details*
![plot4](./images/2-3.PNG)
<br/><br/>
Below figure shows the best automl model.  <br/><br/>
*Figure 5-1: Best automl model*
![plot5](./images/2-4.PNG)
<br/><br/>
Below figure shows the the run details of the automl model.  <br/><br/>
*Figure 5-2: Best automl model*
![plot4](./images/2-5.PNG)
<br/><br/>
Below figure shows the parameters of the best automl model.  <br/><br/>
*Figure 6: Best automl model parameters*
![plot6](./images/2-6.PNG)
<br/><br/>

## Hyperparameter Tuning
*TODO*: What kind of model did you choose for this experiment and why? Give an overview of the types of parameters and their ranges used for the hyperparameter search.<br/><br/>
A Logistic Regression was used for this classification problem. 
Parameters C and max_iter are selected to be optimized. 
The option of the hyperparameters are (0.1, 1, 5) for C and (25, 50, 100, 200, 500) for max_iter. 
<br/><br/>
*Figure 7: Hyperparameter settings*
![plot7](./images/1-1.PNG)
<br/><br/>

### Results
*TODO*: What are the results you got with your model? What were the parameters of the model? How could you have improved it?

*TODO* Remeber to provide screenshots of the `RunDetails` widget as well as a screenshot of the best model trained with it's parameters.<br/><br/>
The best model has an accuracy of 0.8670886 with C as 0.1 and max_iter as 500 the best. A wider range of C and max_iter could be used to improve the model accuracy.
<br/><br/>
*Figure 8: Hyperparameter tuning run details*
![plot8](./images/1-2.PNG)
<br/><br/>
*Figure 9: Hyperparameter tuning results*
![plot9](./images/1-3.PNG)
<br/><br/>
*Figure 10: Hyperparameter tuning best model*
![plot10](./images/1-4.PNG)
<br/><br/>
*Figure 11: Hyperparameter tuning best model*
![plot11](./images/1-5.PNG)
<br/><br/>
*Figure 12: Hyperparameter tuning best model parameters*
![plot12](./images/1-6.PNG)
<br/><br/>

## Model Deployment
*TODO*: Give an overview of the deployed model and instructions on how to query the endpoint with a sample input.<br/><br/>
The best model (generated from automl) is deployed using ACI webservice. See below for the ACI configuration settings and the status of endpoint deployed.
<br/><br/>
*Figure 13: Code to deploy the model*
![plot12](./images/3-1.PNG)
<br/><br/>
*Figure 14: Model endpoint*
![plot13](./images/3-2.PNG)
<br/><br/>
*Figure 15: Send a request to the endpoint*
![plot15](./images/3-3.PNG)
<br/><br/>
*Figure 16: Send a request to the endpoint*
![plot16](./images/3-4.PNG)
<br/><br/>

## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:
- A working model
- Demo of the deployed  model
- Demo of a sample request sent to the endpoint and its response

Link: <a href="https://www.youtube.com/watch?v=YXz6kT5-pSE" target="_blank">Screencast video</a>