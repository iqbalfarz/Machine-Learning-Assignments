This folder contains implementing Naive Bayes on Text Data:

**1. Apply Multinomial Naive Bayes on these feature sets:**

* **SET 1**: categorical, numerical features + preprocessed_essays(BOW)
* **SET 2**: categorical, numerical features + preprocessed_essays(TF-IDF)

**2. The hyper-parameter tuning(find best alpha: smoothing parameter)**
* find the best hyper-parameter which gives the maximum AUC score value.
* find the best hyper-parameter using k-fold cross validation(use GridSearchCV or RandomSearchCV or Simple cross-validation).

**3. Representation of results**
* plot the performance model both on train data and cross validation data for each hyper-parameter, like shown in figure below.
![image](https://user-images.githubusercontent.com/32350208/122803898-d736c780-d2e4-11eb-8906-7a0e5e820bb6.png)

* train model on best found parameter and get AUC score.
![image](https://user-images.githubusercontent.com/32350208/122804135-23820780-d2e5-11eb-87ff-1b29f41eaa4d.png)
