# GA_Python_Final_Project


## Project Description

My project is a data science project focusing on predicting heart disease.  For this project, I am using the KNN (K-Nearest Neighbors) algorithm.  

My project depends on 3 files:
•	CBB_Final_Project_UIC_Heart_Data.ipynb
•	heart.csv
•	heart_dummy_data4.csv

Within the heart.csv dataset, the “target” column includes values of 0-1 which indicate 0 for  “No Heart Disease” or 1 for “Presence of Heart Disease”.  Other fields capture the gender, blood pressure, maximum heart rate, etc.

from my initial analysis of the dataset, I noticed the following:
Out of 303 records, men made up 207 records.  45% of the men in the dataset had heart disease.  The dataset had 96 women records, which had heart disease was present in 75% of them.
The age groups with the biggest impact were 50 year old men and 40 year old  women.  50 year old men led all age-gender cohorts in total members [41 men] with heart disease.  40 yr old women led all age-gender cohorts in % of cohort with heart disease [95%].  The cohorts with the lowest % of heart disease were 50-60 yr old men with 45% and 25% heart disease impacts.

## KNN Algorithm results

1.	Initial source data set accuracy
I initially split the training/test sets by the 80/20 rule, which gives the testing set 80% of the records.  I set the amount of “Neighbors” equal to 3 which resulted in a classification accuracies of 88% and 83% for my training and test sets.  I proceeded to test the KNN algorithm against 1-9 neighbors.  I noticed that the test set began to outperform the training set around 5 and 7 neighbors.  This leads me to question whether overfitting may be a problem.

2.	Initial dummy data set accuracy
For the initial dummy data KNN test, I also split the dummy data by 80/20.  The dummy data set roughly had the same amount of records (317 in the dummy file vs 303 in the source file].  The KNN model scored 75% on the training set but only 53% on the test set.  After running a correlation test on the dummy data, I noticed that there were no significant coefficients for the dummy data set’s “target” column.  I believe that this is a flaw that hurt the accuracy of the KNN model’s scoring.

3.	Final source data set accuracy
For the final KNN run, I increased the training data set to 90% and decided to remove “ca” [number of major vessels impacted], “thal” , “oldpeak” [ST depression] and “exang” [exercise induced angina] from the dataset.  After re-running the model against the source data set, the KNN scored 85% against the training dataset and 77% against the test data set.  This was lower than the initial test, but I noticed that overfitting didn’t occur until 7.5 neighbors compared to 5 neighbors in the previous run

4.	Final dummy data set accuracy
For the final dummy data KNN run, I also increased the training set up to 90% data and removed the same columns.  After re-running the KNN model, I noticed after evaluating it for 1-9 neighbors, it outperformed the previous dummy data run around 7/+ neighbors.


## About the KNN Algorithm
The KNN algorithm is an older algorithm that uses Euclidean distance between points in the test set and the training set.  Using Euclidean distance allows the KNN algorithm to identify the classification of the points in the training set and classify the test data set point(s) based upon location to points classified in the training set.  You can learn more about the KNN algorithm at the following link:  https://www.analyticsvidhya.com/blog/2018/03/introduction-k-neighbours-algorithm-clustering/


After discussing with the data science community, KNN is not often used.  The drawbacks to the KNN algorithm are the following:
1.	KNN struggles with big datasets
2.	KNN cannot handle datasets with both categorical data and numerical data
3.	[not confirmed] KNN may not be an algorithm that learns from incremental runs

## Other algorithms that I used included the following:
1.	Logistic Regression
2.	Decision Tree – appeared to be overfitting with standard configurations
3.	Random Forest – appeared to be overfitting with standard configurations
4.	Gradient Boost

The Logistic Regression and Gradient Boost algorithms worked well 86%, 90% predictions respectively.  I chose to not include them at this time as I continue to research and implement them.  Decision Tree is also an algorithm that I would like to get more experience with.  Decision trees require a lot of configuration (pruning trees, etc) to get them to perform correctly.

One of the biggest lessons that I learned during this project was the presence of Overfitting and Underfitting.  Overfitting seems to cause your model to predict a high percent (98-100%) but is not stable and when introduced to a new dataset, it could perform drastically worse (i.e. 50%).  A properly trained model will be able to perform well across different datasets (data refresh, etc).

Underfitting, is typically associated with datasets that have few features or the model is too simple.  Underfitting leads to less variance in outcomes 
