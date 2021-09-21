# Predicting Drilling Outcomes with Machine Learning

## Overview

[Presentation Deck](https://docs.google.com/presentation/d/1TrmBVhpxC0uwEIJbYaWV1LSWlHm9EZwBkupt1_mkAKs/edit?usp=sharing)

### Selected Topic

We will be utilizing supervised machine learning to predict how successful and efficient a drilling well will be, with efficiency/success determined by rate of penetration, or how far the well drills in feet per hour.

### Reason the Topic was Selected

We selected this topic to evaluate how drilling performance can be improved.

### Description of Data Source

The dataset we used is actual data from sensors on drilling rigs in West Texas.

### Questions we Hope to Answer with the Data

We are trying to answer, or predict if drill bits are damaged or not working correctly if the output falls outside of the predicted y-value.

### Communication Protocols

We will be utilizing slack, as well as Zoom to communicate and collaborate with each other. We will also be sharing notes via Google Docs.

### First Linear Regression Model

![Capture](https://user-images.githubusercontent.com/77767984/132602322-cff08710-bd66-498e-8656-b785fc20bfa8.PNG)


Our first linear regression model was created with an input of Weight on Bit multiplied by Gamma. The relationship between these two is that high Gamma means low rock strength, which is expected to drill faster (higher rate of penetration), and a higher weight on bit means more pressure being applied to the rock, which is also expected to produce higher rate of penetration.
