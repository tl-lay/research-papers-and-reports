
The training job is split into three notebook files. 

(1) Data Exploration and Model Selection
(2) Data Preparation
(3) Classifying Risk of Default Payment - Logistic Regression

========

(1) Data Exploration and Model Selection

This notebook provides insight on data preparation and model training using the training data.

The exploratory analysis demonstrates the motivation behind feature engineering and
feature selection after handling missing values and preparing the data for the training job.

Various models were used to classify the risk of default payments. 
The selected model was evaluated based on ROC and AUC and determined to be Logistic Regression

========

(2) Data Preparation

This notebook prepares the testing data for the training job based on the data exploration. 
The same transformations seen in (1) are performed on both the training and testing data.

This file exports two CSV files with encoded categorical features.
 * The first CSV file contains the training set that will be used for the training job.
 * The second CSV file contains the testing set to make predictions with the final model

The purpose of this file is to transform the data and select the features which will be 
used in the training job. 

========

(3) Classifying Risk of Default Payment - Logistic Regression

This file imports the two csv files that were exported from (2).

Running the code in this file will train the model and make predictions on the testing set.
The predictions are concatenated to a data frame with the corresponding order IDs.
This dataframe is exported to a text file called 'classification-result.txt'

========

'classification-result.txt' contains ORDER-ID and CLASS showing the order IDs and the
predicted label: 'no' being low risk and 'yes' being high risk. 

This output is separated by tabs.
