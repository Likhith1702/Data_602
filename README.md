# Texas Department of Criminal Justice
Link to dataset: https://data.texas.gov/dataset/High-Value-Dataset-January-2022/y6p5-x3b9
## Introduction:
It can be said that in any country, felonies are common no matter how developed or rich a country is. Criminals are subjected to the punishment that they are due. While reforming a society, correction facilities with proper guidelines are necessary. The Texas Department of Criminal Justice (TDCJ) looks after inmates in state prisons, state jails, and private prisons that work with the TDCJ. It is in charge of making sure that inmates who are released from prison on parole or mandatory supervision are being properly watched. My objective is to predict the parole decision for an inmate based on age, projected release date, Maximum Sentence, Race, Sentence date, Gender and Offence.
## Objective:
To predict Parole acceptance with the data based on sentence type, age, Gender, Offence, Race, Sentence
## Dataset Description:
This is a dataset that has onhand inmate population with relevent demographic offence and parol information from texas department of crimal justice.
## Features:
* SID Number :
State Identification number that has been assigned to an individual whose fingerprints have been recorded.

* TDCJ Number:
A number provided by Texas Department of Criminal Justice to keep track of inmates housed in their jails by their loved ones.

* Name:
Name of the inmates

* Current Facility:
Facility where an inmates is housed by TDCJ

* Gender:
Gender of inmate

* Race:
Race of inmate

* Age:
Age of inmate

* Projected Release:
Projected Date on which the inmate could be released

* Maximum Sentence Date:
The date until when an individual is supposed to be in the jail as decided by court of law

* Parole Eligibility Date:
Date when an individual can apply for his parole

* Case Number:
An unique number that is assigned to a case

* County:
Area where the crime took place

* Offense Code:
An unique identifier with which police identifies the crime

* TDCJ Offense:
Description of offense

* Sentence Date:
Date on which an inmate was sentenced to jail by the court of law

* Offense Date:
Date when the offense/crime took place

* Sentenced (Years):
Number of years an inmate has been sentenced to stay in jail

* Last Parole Decision:
Latest parole decision for an inmate

* Next Parole Review Date:
Immediate date of parole review

* Parole Review Status:
States if a parole has been accepted or denied

## Data Cleanup:
1) This dataset contained 118733 rows and 20 columns. I have omitted SID Number, Name, Case Number, Next Parole Review Date columns
As these are not needed in our analysis I dropped these columns and used the trimmed dataset for further processing of data. This will give us a clear picture of our variables.
2) I dropped 'NaN' values from Parole Eligibility Date, Last Parole Decision, Parole Review Status, Maximum Sentence Date columns.
3) In the 'Age' column, 'Life', 'Capital Life' values are replaced with 110 to change the datatype as 'int' to use it in the further analysis.
4) Splitting 'Last Parole Decision' column into 'Parole_Decision' and 'Parole_Decision_Date' columns to visualize meaningful insights.
5) Created 'Decision_Year', 'Decision_Month' columns from 'Parole_Decision_Date' column and removed all 'NaN' values in these columns.

## EDA Outcomes:
### 1) Top 10 Offenses in Texas
I took the crimes that are there in the dataset and plotted them to see which is prevelent in this case. we can see that from the data we have "Murder" tops the list while "Robbery" takes the second place and Sexual assult on minors comes at last.

### 2) Top facilities in which inmates are housed
I took the total inmates that are there and plotted them to see which facility houses the most inmates as per texas department of criminal justice 

### 3) Unsafe counties as per data in Texas
I plotted a graph to see which county has more crime rate to see which one is more safe and which is not. 

### 4) Count of Approved and Denied parole decisions
I plotted a graph to see the total approvals and denials that happened in the data set, I see that there are 48195 denials while approvals stand at 12282

### 5) Acceptance and denial frequency of parole based on Age
I plotted a graph to see which age group has more number of parole approvals and denials. Most approved paroles are given for people aged between 20-30. Also, people who are aged between 60-80 have no approval paroles.

### 6) Acceptance and denial frequency of parole based on sentence years
I plotted a graph to see acceptance and denial of Parole based on Sentence Years to see if there is any trend of parole acceptance that I can see based on the number of years someone got.

### 7) Parole decisions based on Gender and Race
Plotted a graph to see the acceptance and denial of paroles that are based of gender and race. Based on gender we see that many males have got parols accepted 

### 8) Count of approved and denied paroles by year
Plotted a line graph to see the relation between years and acceptace and denial of parole for the dataset

# Modeling and Classification
We are going to do Logistic Regression, Decision Tree, K-Nearest Neighbors Classifier and random forest classifier to see the accuracy of our models. 

## Splitting of Dataset to test and train sets for further analysis. 
The initial cleaned data set is split into test date and train date for analysis. Test data set is used for training the model for review.\
Since, there is a slight imbalance in the class data, I have done oversampling to negate the imbalance to some extent

## Classification using Logistic Regression
The following hyperparameters were used: 1, 10, and 50 were used as penalty strengths for grid search.\
When the hyperparameter C is 10, this model appears to be the most effective for classification.\
In the initial analysis we see that the we get a Validation score of 74.31% and a Test score: 73.72% to choose the best model we use the c value of 5, 10, 15 so as to determine the neighborhood which we can see at 5 so we are using 5 for our results.\
From the testing scores, we see that the accuracy of the dataset is 78% while from the training scores, we see that the accuracy of the dataset is 84% \
From the ROC curve we can see that the area under that is 0.723881

## Classification using Decesion Tree Classifier
Initially, we considered max depth as 1, 10, and 50; and minimum sample split as 0.1, 1 and 10.\
Fom our initial analysis, we got max depth as 10, and min sample split as 10. While the report stands at Validation score of 75.18% and Test score of 75.24% \
Post the initial analysis we see that we got a ma depth of 10 and minimum split of 10\ 
Seeing the results from the initial analysis we are going with max depth of (5, 10, 15) and min sample split of (1, 10, 15)\
After secondary seach we get a Max depth of 15 and minimum sample split of 10. Hence printing the same with 15 as max depth and 10 as minimum sample split.  
From the testing data, with decision tree analysis, we see an accuracy of 79%. From the training data, with decision tree analysis, we see an accuracy of 84%/
Taking in these values we put ROC curve we can see that the area under it is 0.71379 which seems reasonable. 

## Classification using K-Nearest Neighbors Classifier
For our initial analysis the hyperparameters used are 1,10,50 as number of neighbors for grid search. \
This initial model seems to be best for classification when hyperparameter number of neighbors are 50 and we get The accuracy of KNN classifier as 0.79811 for the initial analysis\
From the initial analysis, we see that this classification is best-suited when hyperparameter numbers are in the neighbourhood of 50. So, in the secondary analysis, we considered (40,50,60).\
The model seems to be best for classification when hyperparameter number of neighbours are 60 and we get accuracy of KNN classifier as 0.79803\ 
It seems like KNN is has a comparitively similar accuracy when compared with Logistic and DTC having 79% accuracy \
Also, the area of curve for KNN has decreased to 71% fom 72% which is not too significant\

## Random Forest Classifier 
When we use the Random Forest classifier model we see that that the accuracy is at 68% which is comprartivly very less with regards ro logistic regression and Decesion tree. Hence this is not the correct mode that should be used on this data set for our analysis.\
With the ROC curve we can see that the area under it is 0.6951 which is less compared to other models we have seen above.\

# Conclusion 
From the above analysis we can see that both Logistic regression and decesion tree classifiers are best suited for our dateset and our target variable.\
When we compare KNN (K-Nearest neighbour) classifier and Random forest classifier we can see a dip in the accuracy of the model. Eventhough the drop is not huge when it comes to KNN model, there is a significant drop in accuracy when it comes to Random forest classifer. 
