# Predicting Drilling Outcomes with Machine Learning

## Overview

[Presentation Deck](https://docs.google.com/presentation/d/1TrmBVhpxC0uwEIJbYaWV1LSWlHm9EZwBkupt1_mkAKs/edit?usp=sharing)

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

(insert here)

### First Linear Regression Model

![Capture](https://user-images.githubusercontent.com/77767984/132602322-cff08710-bd66-498e-8656-b785fc20bfa8.PNG)


Our first linear regression model was created with an input of Weight on Bit multiplied by Gamma. The relationship between these two is that high Gamma means low rock strength, which is expected to drill faster (higher rate of penetration), and a higher weight on bit means more pressure being applied to the rock, which is also expected to produce higher rate of penetration. The training and testing data was split up into 6 sets for each oil well in the original datatest, and 5 of those were concatenated to form the training set while the 6th set was the testing set.

#### Accuracy Scores

Accuracy can't be measured from a linear regression model, however mean absolute error and mean absolute percentage error were calculated. Mean squared error calculates the average squared difference between the estimated values and the actual value.

### Second Linear Regression Model


