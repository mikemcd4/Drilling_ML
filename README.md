# Predicting Drilling Outcomes with Machine Learning

## Overview

We will be utilizing supervised machine learning to predict how successful and efficient a drilling well will be, with efficiency/success determined by rate of penetration, or how far the well drills in feet per hour.

## Communication Protocols

We will be utilizing slack, as well as Zoom to communicate and collaborate with each other. We will also be sharing notes via Google Docs.

### First Linear Regression Model

![first_model](https://user-images.githubusercontent.com/77767984/132428693-593f56f9-73e3-4ce3-af1c-6a3e2a0763d0.PNG)

Our first linear regression model was created with an input of Weight on Bit multiplied by Gamma. The relationship between these two is that high Gamma means low rock strength, which is expected to drill faster (higher rate of penetration), and a higher weight on bit means more pressure being applied to the rock, which is also expected to produce higher rate of penetration.

Judging the outcome of our first model, it is clear that additional data cleaning will be required.

### Second Linear Regression Model

![2nd_model](https://user-images.githubusercontent.com/77767984/132431107-75fd1b6c-4c3f-4fb4-ac45-bbf49ec055b0.PNG)

