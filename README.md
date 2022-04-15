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
