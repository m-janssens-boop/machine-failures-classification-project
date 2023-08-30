machine-failures-classification

Project reqs:
# Project 4 Overview
For Project 4, you will work with your group to solve, analyze, or visualize a problem using machine learning (ML) with the other technologies we’ve learned. Here are the specific requirements:

Find a problem worth solving, analyzing, or visualizing.
1. <s> Use machine learning (ML) with the technologies we’ve learned. </s>
2. <s> You must use Scikit-learn and/or another machine learning library. </s>
3. <s> Your project must be powered by a dataset with at least 10,000 records. </s>
4. You must use Pandas and Matplotlib
5. You must use a database (SQL or MongoDB)
6. <s> You must use GCP or AWS </s>
7. You must either use Javascript (Plotly/Leaflet) OR Tableau

%% Cell type:markdown id:2baddcd6 tags:

# Project 4 Requirements
### Data Model Implementation (25 points)
* <s> A Python script initializes, trains, and evaluates a model (10 points) </s>
* Multiple models and cross validation were used (10 points)
* The data is cleaned, normalized, and standardized prior to modeling (5 points)
    * Data contained at least 10,000 records (contact instructor/TA if you have less than 10000)
* The model utilizes data retrieved from SQL or Spark (5 points)
* <s> The model demonstrates meaningful predictive power at least 75% classification accuracy or 0.80 R-squared. (5 points) </s>
* Cloud computing was used, either AWS or GCP (5 points)

### Data Model Optimization (25 points)
* The model optimization and evaluation process showing iterative changes made to the model and the resulting changes in model performance is documented in either a CSV/Excel table or in the Python script itself (15 points)
* Overall model performance is printed or displayed at the end of the script (10 points)

### GitHub Documentation (25 points)
* GitHub repository is free of unnecessary files and folders and has an appropriate .gitignore in use (10 points)
* The README is customized as a polished presentation of the content of the project (15 points)

### Group Presentation (25 points)
* All group members speak during the presentation. (5 points)
* Content, transitions, and conclusions flow smoothly within any time restrictions. (5 points)
* A dashboard was created using Tableau or Javascript and is relevant to the project. (10 points)
* The presentation maintains audience interest. (5 points)




Machine Failure Classification
--------------------
## Overview/Background
This project tests different machine learning algorithms to find the optimal algorithm to predict machine failures for a large company that produces machine fabricated parts. The dataset used to train the models is synthetically generated and can be found at this [link](https://www.kaggle.com/competitions/playground-series-s3e17/data), it is based on this [Machine Failure Predictions dataset](https://www.kaggle.com/datasets/dineshmanikanta/machine-failure-predictions). 

## Preprocessing the Data - these need to be updated since we changed how the data was preprocessed for each model
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
#### Interpretability


### K-Means/K Nearest Neighbors

#### Additional Data Preprocessing
*
*
*
#### Classification Report
Include screenshot here
#### Time to Run
#### Interpretability

### Random Forest

#### Additional Data Preprocessing
*
*
*
#### Classification Report
Include screenshot here
#### Time to Run
#### Interpretability

### Gradient Boosting Classifier/Grid Search CV

#### Additional Data Preprocessing
*
*
*
#### Classification Report
Include screenshot here
#### Time to Run
#### Interpretability

### Neural Network

#### Additional Data Preprocessing
*
*
*
#### Classification Report
Include screenshot here
#### Time to Run
#### Interpretability

## Final Model Choice and Optimization


## Conclusions and Results

## Project Presentation
The link to our project presentation slides can be found [here](https://docs.google.com/presentation/d/10biaqRep5-ZiiN-dKkGj1IbnFcmimI6NaaFdfJqak3s/edit?usp=sharing)
