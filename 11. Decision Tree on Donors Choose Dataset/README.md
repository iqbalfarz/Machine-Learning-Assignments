# Decision Tree on Donors Choose Dataset

## Problem Statement
- Predict whether the proposal will be accepted or not on Official Donors Choose website.
- This is a Binary Classification task.(accepted OR rejected)


## Dataset
There are two files `preprocessed_data.csv` and `glove_vectors.txt`.

Download dataset from here: [Click to download glove vectors!](https://drive.google.com/file/d/1JdyOFAFmYNzCLOzWGu2Y9s063FGnFKh6/view?usp=sharing), [Click to download preprocessed_data.csv](https://drive.google.com/file/d/1upmTSogWSWZ3s10Zg5QqO0-BKNFKT6--/view?usp=sharing)

- For this assignment data set is preprocessed.

## Machine Learning Modeling
Applying Decision Tree on two types of further processed dataset.

__SET 1:__
- categorical
- numerical features + preprocessed_essay(TFIDF)
- sentiment scores of preprocessed_essay

__SET 2:__
- categorical
- numerical features + preprocessed_essay(TFIDF W2V)
- sentiment scores of preprocessed_essay

## Results
__SET 1:__
- Heatmap of AUC of Training data of SET 1
![image](https://user-images.githubusercontent.com/32350208/123643872-7a866000-d842-11eb-9af2-6e7d1f879875.png)

- Heatmap of AUC of Test data of SET 1
![image](https://user-images.githubusercontent.com/32350208/123643938-8c680300-d842-11eb-964e-25fd20783ea5.png)

- Reciever Operating Characteristic Curve of SET 1
![image](https://user-images.githubusercontent.com/32350208/123644063-a7d30e00-d842-11eb-9478-f1489e57e1d7.png)

- confusion matrix of SET 1
![image](https://user-images.githubusercontent.com/32350208/123644129-b7525700-d842-11eb-86c7-a48010d94ec4.png)


## Credit
- [Applied AI Course](https://www.appliedaicourse.com): For teaching in-depth Machine Learning, Deep Learning, Computer Vision, NLP, and end-to-end problem solving.

- [Machine Learning Mastery](https://www.machinelearningmastery.com): For best Machine Learning blogs.
