# Orthopedics

### Objective
In this project I create models to scan patients for hernias and spondylolithesis.

### The data
I am given several measurements of the patient such as pelvic tilt, sacral slope, and lumbar lordosis angle. I am also given a label on whether the patient was deemed to have a hernia, spondylolithesis, or neither.

## Results
In this project I prioritized recall as the performance metric because it is better to treat a healthy person than to not treat an ill person.

For the hernia classifier I used a logistic regression model. The test results were as follows:
recall: 0.83
precision: 0.71
accuracy: 0.90

For the sponylolithesis model I used a random forest model. The test results were as follows:
recall: 1.0
precision: 0.93
accuracy: 0.96

## The Process
In this project I went through the normal steps of data cleaning, exploratory data analysis, feature engineering, modeling, and evaluation. I have already gone over the results of the evaluation, so here is a breakdown of the rest of this repo.

### Data Cleaning
The data provided was already clean. There were no missing values or innappropriate data types. However there was class imbalance, so I made use of a stratified split when splitting the training set from the testing set.

### Exploratory Data Analysis
In the analysis of the data I first noticed that the spondylolisthis angle was highly scewed in its distribution, so I log transformed it. Several of the variables had a linear relationship with the targets, such as pelvic incidence and the spondylolisthis angle. When analyzing the data for bivariate relationships amoungst the features I noticed several of the features had linear relationships. Lastly when checking relationships involving two features along with a target I found no noticable relationships.

### Feature engineering
The main goal of my feature engineering was to reduce multicolinearity. I ran several statistical tests to deduce what the best feature might be. I put the chosen features into new dataframes and saved them to .csv files. 

### Modeling
I tried several different machine learning models as well as both the original and engineered data sets. I concluded that the original datasets were better to work with than the engineered data. I used grid searches to tune the hyperparameters of each model. After the best models were found, I used the precision-recall tradeoff to enhance the recall of the hernia classifier.
