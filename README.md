# Predicting Drilling Outcomes with Machine Learning

## Overview

[Presentation Deck](https://docs.google.com/presentation/d/1TrmBVhpxC0uwEIJbYaWV1LSWlHm9EZwBkupt1_mkAKs/edit?usp=sharing)
[Dashboard Link](https://public.tableau.com/app/profile/cory.mccoy/viz/DrillingDashboard/DrillingStory?publish=yes)

### Selected Topic

Oil exploration and drilling is a big deal in Texas and other regions around the world. It is a source of income for a number of large, multinational companies employing thousands of people. As the world transitions to greener energy sources, the need to maximize profits and efficiency in fossil fuel production will only continue to increase.
Oil companies are constantly looking for new and innovative ways to drill more safely and efficiently. The goal of any company is to extract as much oil as quickly as they can, while maintaining both a safe work environment, as well as equipment integrity.


### Reason the Topic was Selected

We selected this topic to evaluate how drilling performance can be improved.

### Description of Data Source

The dataset we used is actual data from sensors on drilling rigs in West Texas. It includes five separate wells, the bit RPM, bit torque, depth of cut, gamma, mechanical specific energy, rate of penetration, and weight on bit.

The data in this set we are concerned with is the weight on bit (weight applied to the well’s drill bit), the gamma (the strength of the rock being drilled into, higher gamma equals lower rock strength). These two multiplied will be our X-variable. Our y-variable, that we are trying to predict, is the rate of penetration (how many feet the well drills per hour). 


### Questions we Hope to Answer with the Data

Determine if drill bits, the piece of the well that drills into the ground, are damaged or not working properly if the output of the well falls outside of the predicted y-value of our model, which is the well’s rate of penetration, or how many feet the well drills per hour.


### Initial Assessment of Data

After cleaning out null values and outliers from the initial dataset, we are left with 24,331 data points across five wells. The outliers were determined by what was considered normal parameters for the drill bit to be in good condition.
Null values and outliers were removed from the original datatest. 
For one of our models, we took our 6 original datasets, concatenated 5 of them and cleaned them, and used them for our training set. For the remaining dataset, it was cleaned and used as the testing set. 
For the other model, we imported the cleaned dataset and split it into 80% training data, and 20% testing data using scikitlearn.

### Tools Used

#### Database

We used AWS SQL database to connect and store our data. Within the files, the file name "Connect data to database" is the code we used to connect our csv data to the SQL database. We picked AWS because it is a cloud base SQL database that allowed each team member to access the data through PgAdmin. PgAdmin is a free database program that each member has to download on their local machine. There are a couple steps that need to be taken to link the AWS server to PgAdmin. Below are the steps below. 

1. Download and open PgAdmin 
2. Right click on server and click create new 
3. Fill out the infomation in the screenshot below

![Database Config]()

#### Tablau 

We used Tablau Desktop to display our findings as a dashboard. The main reason we used Tablau is because we wanted to system that can be accessed by the public. This will help with future interation. For example, if we want to model to be interactive with real time drilling parameters, we will need a dashboard that can be accessed in the field with limited technology so the employees on location can monitor their progress. Many dashboards require a computer and local host which isn't always possible in remote locations. 

1. Walking through the story of the dashboard, we have 3 main decks. The first desk is a quick visualzation on how certain inputs influance ROP. The inputs we studied were Weight on Bit (WOB) and Gamma. We ran out of time to study RPM (how fast the bit is turning) within our machine learning module. As you can see, there is a strong linear cooralation between ROP and WOB and a linear coorelation between ROP and Gamma.

![Sheet1]()

2. The 2nd sheet breaks down and identifies a range of input parameters where the highest ROP is observed. This is important in our study to know and understand where high ROP can be achieved as well as a QA/QC tool to make sure they data going into the model is correct. 

![sheet2]()
3. The 3rd sheets shows a predicted linear line of WOB and ROP. Additionally, we a set against a test well and our predicted ROP matches up very well with the actual ROP on a test well. This gives us confidence in our model.

![sheet3]()

### First Linear Regression Model

![Capture](https://user-images.githubusercontent.com/77767984/132602322-cff08710-bd66-498e-8656-b785fc20bfa8.PNG)


Our first linear regression model was created with an input of Weight on Bit multiplied by Gamma. The relationship between these two is that high Gamma means low rock strength, which is expected to drill faster (higher rate of penetration), and a higher weight on bit means more pressure being applied to the rock, which is also expected to produce higher rate of penetration. The training and testing data was split up into 6 sets for each oil well in the original datatest, and 5 of those were concatenated to form the training set while the 6th set was the testing set.

#### Accuracy Scores

Accuracy can't be measured from a linear regression model, however mean absolute error and mean absolute percentage error were calculated.

#### Mean Absolute Error

![MAE_model1](https://user-images.githubusercontent.com/77767984/134611003-e4f5487c-bc29-4744-8d89-e67dfdf217c6.PNG)

#### Mean Absolute Percentage Error

![MAPE_model1](https://user-images.githubusercontent.com/77767984/134611027-e9898dca-6dea-4cb2-bcdb-f4f74fd507e7.PNG)


### Second Linear Regression Model


![test_model](https://user-images.githubusercontent.com/77767984/134607084-29190854-6099-4bc0-8733-31f83b13edb7.PNG)

The second linear regression model used the same variables, however the original dataset was split into training and testing sets more traditionally, by using sklearn to split the data 80 % training, and 20% testing.

#### Mean Absolute Error

![mean_absolute_error_2](https://user-images.githubusercontent.com/77767984/134610136-3d1815f6-9502-4ab2-8f12-e234576c8a88.PNG)

(insert description)

#### Mean Absolute Percentage Error
![mean_absolute_percentage_error_2](https://user-images.githubusercontent.com/77767984/134610170-1f124959-121b-4539-beff-c7873ef57469.PNG)

(insert description)





