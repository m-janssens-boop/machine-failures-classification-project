machine-failures-classification
--------------------
## Overview/Background
This project tests different machine learning algorithms to find the optimal algorithm to predict machine failures for a large company that produces machine fabricated parts. The dataset used to train the models is synthetically generated and can be found at this [link](https://www.kaggle.com/competitions/playground-series-s3e17/data), it is based on this [Machine Failure Predictions dataset](https://www.kaggle.com/datasets/dineshmanikanta/machine-failure-predictions). 

## Preprocessing the Data
* The csv files of the dataset were placed in s3 buckets on AWS
* The `id` columns were dropped from both the training and the testing datasets
* The target array was created using the `Machine Failures` column
* The Features contains the remainder of the variables
* To test the models locally, the training set was split into testing and training sets using `sklearn` 

## Models and Their Performance

### Logistic Regression

#### Additional Data Preprocessing
* The testing and training sets were concatenated into a dataframe so that one-hot encoding could be implemented, using the `pd.get_dummies()` function
* The categorically encoded datasets were then split again into their respective training and testing sets
* The training and testing sets were scaled using `StandardScaler()`
#### Classification Report
<img width="406" alt="logistic_regression_classification_report" src="https://github.com/m-janssens-boop/machine-failures-classification-project/assets/127706155/f19fd131-2657-4ea0-9031-906aa76b5d44">

#### Time to Run
12.5 seconds

### K-Means/K Nearest Neighbors

#### Additional Data Preprocessing
*
*
*
#### Classification Report
Include screenshot here
#### Time to Run


### Random Forest

#### Additional Data Preprocessing
* The `Product ID` column was dropped from the features dataframe
* One-hot encoding was used on the features dataframe
* Oversampling was done on the training set so that the set had 10% machine failures, as machine failures made up just over 1% of the original training set
  * RandomOverSampler from imblearn was used to oversample the data
#### Classification Report
Both of the classification reports, pre and post oversampling are included below:
##### Without oversampling
<img width="434" alt="random_forest_without_oversampling" src="https://github.com/m-janssens-boop/machine-failures-classification-project/assets/127706155/d2f7a4cf-0b04-4e39-a757-52a3fd5cd789">

#### Time to Run
600 seconds

##### With oversampling
<img width="398" alt="random_forest_with_oversampling" src="https://github.com/m-janssens-boop/machine-failures-classification-project/assets/127706155/92b2970d-e2a8-42d2-8d98-7e12f35b504d">

#### Time to Run
270 seconds

### Gradient Boosting Classifier/Grid Search CV

#### Additional Data Preprocessing
* The testing and training sets were concatenated into a dataframe so that one-hot encoding could be implemented, using the `pd.get_dummies()` function
* The `Product ID` column was dropped from the features dataframe
* The categorically encoded datasets were then split again into their respective training and testing sets
* Oversampling was done on the training set so that the set had 50% machine failures, which were only just over 1% in the original set
#### Classification Report
<img width="406" alt="logistic_regression_classification_report" src="https://github.com/m-janssens-boop/machine-failures-classification-project/blob/main/Visualizations/Classification_Report_PNGs/gboost_best_model_classification_report.png">

#### Time to Run

173.7 seconds

### Neural Network

#### Additional Data Preprocessing
* Due to a low rate of machine failure, oversampling was done to boost the rate of machine failure to 50% of the data set.
* In order to remove the categorical data, the `Product ID` column was dropped and `LabelEncoder()` was used to transform the `Type` column into numerical data.
* The model was run with two hidden layers of 10 nodes and 3 nodes respectively, both using `relu` as their activation. The output layer had one node with the `sigmoid` output in order to make it approximate a boolean output.
#### Classification Report
<img width = "400" alt="nn_model_oversampled_1" src="https://github.com/m-janssens-boop/machine-failures-classification-project/blob/main/Visualizations/nn_classification_resports/nn_model_oversampled_1.png?raw=true">
#### Time to Run

303.6 seconds

## Final Model Choice and Optimization


## Conclusions and Results

## Project Presentation
The link to our project presentation slides can be found [here](https://docs.google.com/presentation/d/10biaqRep5-ZiiN-dKkGj1IbnFcmimI6NaaFdfJqak3s/edit?usp=sharing) and the link to our Tableau dashboard can be found [here](https://public.tableau.com/views/Machine_Failure_Dashboard/GradientBoostOptimization?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link).
