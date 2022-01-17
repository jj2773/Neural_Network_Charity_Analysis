# Neural Network Deep Learning for Charity Analysis

## Overview 

A fictitious company Alphabet Soup has recieved funding from 34,000 organizations over the years.  A dataset is provided with application information and whether the money was used successfully or not.  It is desired to use deep learning to be able to predict if applicants  will successfully use the money.

## Results: 


### As a first step the Data Preprocessing was performed on the raw table shown below.  

![alt text](https://github.com/jj2773/Neural_Network_Charity_Analysis/blob/main/readme_images/datasampleall.PNG)

* The target variable was identified as IS_SUCCESSFUL

* It was found that the EIN and NAME fields were not relavent to the analysis thus removed

* Categorical fields with more than 10 counts were identified for groupings.

![alt text](https://github.com/jj2773/Neural_Network_Charity_Analysis/blob/main/readme_images/catfieldcounts.PNG)

![alt text](https://github.com/jj2773/Neural_Network_Charity_Analysis/blob/main/readme_images/groupingtoreducecounts.PNG)

* Hot encoder was used to then take all categorical data and transform it to numerical data.

* The sklearn train_test_split function was used to separate the data into a testing and training set.

* Lastly, the StandardScaler was used to scall and transform the X_train data

### Compiling, Training, and Evaluating the Model

Two hidden layers were selected with the number of neurons being 80 and 30 respectively.  The value of neurons selected used the general rule of 2X the independent variables.  An output layer was used with the sigmoid activation function since the output is logical (0 or 1).  The initial model performance was accuracy was 72.4.  The target level performance goal of 75 was not achieved, but three attempts were made:

* Attempt 1 drop ASK_AMT column and changed activation funtion on layer 2 to relu from leaky_relu ==>Accuracy 72.65
* Attempt 2 add third hidden layer with 15 nodes => Accur 72.5
* Attempt 3 change APPLICATION_TYPE bucketing value to less than 500 counts as other. => Accur 72.4


## Summary: 
This deep learning model was able to predict with an accuracy of around 73%.  For future analysis a logistic regression with random forest should be tried and compared.