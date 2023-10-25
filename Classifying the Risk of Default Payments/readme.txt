
All the codes and data are stored in the folder 'Codes + Exports and Results'.

The training job is split into three notebook files. 

(1) Data Exploration and Model Selection
(2) Data Preparation
(3) Classifying Risk of Default Payment - Logistic Regression

The raw data files are stored in the 'data' folder where
the codes are importing the data from.

========

(1) Data Exploration and Model Selection

This notebook file contains the various steps and analyses used to 
select the final model and process the data. This is where we determine the logic
behind handling missing values and preparing the data for the training job.

The exploratory analysis shows the motivation behind the feature engineering and
feature selection after handling missing values.

The model evaluation is the last section of this notebook file.
It shows the various models used to attempt to classify the label
and determines which model performed best using ROC and AUC.

The selected model was Logistic Regression.

The purpose of this code is to simply provide insight as to how we should
prepare our data and train our model.

========

(2) Data Preparation

Using the logic in file (1), this notebook prepares the data for the training job.
It imports the datasets and handles any missing values according to what
was done in the data exploration phase. The same transformations seen in (1) are
performed on both the training and testing data.

This file exports two CSV files with encoded categorical features.
 * The first CSV file contains the training set that will be used for the training job.
 * The second CSV file contains the testing set to make predictions with the final model

The purpose of this file is to transform the data and select the features which will be 
used in the training job. The training and testing sets are exported into the same directory.
========

(3) Classifying Risk of Default Payment - Logistic Regression

This file imports the two csv files that were exported from file (2).
The CSV files should have been exported into the same working directory.

Running the code in this file will train the model and make predictions on the testing set.
The predictions are concatenated to a data frame with the corresponding order IDs.
This dataframe is exported to a text file called 'classification-result.txt'

========

'classification-result.txt' contains ORDER-ID and CLASS showing the order IDs and the
predicted label: 'no' being low risk and 'yes' being high risk. 

This file is separated by tabs. In file (3), changing 'sep' when exporting this text file from '\t' 
to another value will change the seperator used to display the predicted results.
For example, we can use commas or spaces.