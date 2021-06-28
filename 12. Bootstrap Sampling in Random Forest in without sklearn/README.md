# Implementing Bootstrap Sampling in Random Forest using python

## There are three task 

### Task 1

#### Step-1:
- __Creating Samples:__
  Randomly create 30 samples from the whole boston data points
  - Creating each sample: Consider any random 303(60% of 506) data points from whole data set and then replicate any 203 points from
the sampled points.
  - For better understanding of this procedure lets check this examples, assume we have 10 data points [1,2,3,4,5,6,7,8,9,10], first we
take 6 data points randomly , consider we have selected [4, 5, 7, 8, 9, 3] now we will replicate 4 points from [4, 5, 7, 8, 9, 3], consder
they are [5, 8, 3,7] so our final sample will be [4, 5, 7, 8, 9, 3, 5, 8, 3,7].
- __Create 30 samples:__
  - Note that as a part of the Bagging, when you are taking the random samples make sure each of the sample will have different set of
columns.

  Ex: Assume we have 10 columns[1 ,2 ,3 ,4 ,5 ,6 ,7 ,8 ,9 ,10] for the first sample we will select [3, 4, 5, 9, 1, 2] and for the second
sample [7, 9, 1, 4, 5, 6, 2] and so on... Make sure each sample will have atleast 3 feautres/columns/attributes.

#### Step-2:
__Building High Variance Models on each of the sample and finding train MSE(Mean Square Error) value__

- Build a regression tree on each of 30 samples.
- Compute the predicted values of each data point(506 data points) in your corpus.
- Predict house price of ith data point yi_pred = average of all 30 predicted values of all 30 different models
- Now calculate the Mean Square Error(MSE)/ L2 Error.

#### Step-3"
__Calculating the OOB Score:__
- Predict house price of ith data point yi_pred = average of predicted values by model which was not trained on samples not included xi.
- Now calculate the OOBScore = It is also L2 Error but predicted value is like mentioned above.

### Task 2
- __Computing CI(Confidence Interval) of OOB Score and Train MSE__
  - Repeat Task 1 for 35 times, and for each iteration store the Train MSE and OOB Score.
  - After this, we'll have 35 TRAIN values and 35 OOB scores.
  - Using these 35 values(assume like a sample) find the confidence intervals of MSE and OOB score.
  - You need to report Confidence Interval(CI)  of MSE and CI of OOB score.
  - NOTE: Refer the `Central_Limit_theorem.ipynb` to check how to find the confidence interval.

### Task 3
- __Given a single query point, predict the price of house.__

Consider xq= [0.18,20.0,5.00,0.0,0.421,5.60,72.2,7.95,7.0,30.0,19.1,372.13,18.60] Predict the house price for this point as mentioned in the step
2 of Task 1.



## Credit
- [Applied AI Course](https://www.appliedaicourse.com): For teaching in-depth Machine Learning and Deep Learning.

