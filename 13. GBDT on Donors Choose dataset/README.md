# Applying GBDT(Gradient Boosting Decision Tree) on Donors Choose dataset.

__NOTE: I have implemented other algorithms also on Donors Choose dataset.__

## Problem Statement
- Predict whether the proposal will be accepted or not on Official Donors Choose website.
- This is a Binary Classification task.(accepted OR rejected)


## Dataset
There are two files `preprocessed_data.csv` and `glove_vectors.txt`.

Download dataset from here: [Click to download glove vectors!](https://drive.google.com/file/d/1JdyOFAFmYNzCLOzWGu2Y9s063FGnFKh6/view?usp=sharing), [Click to download preprocessed_data.csv](https://drive.google.com/file/d/1upmTSogWSWZ3s10Zg5QqO0-BKNFKT6--/view?usp=sharing)

- For this assignment data set is preprocessed.

## Machine Learning Modeling
Applying GBDT on two types of further processed dataset.

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
![image](https://user-images.githubusercontent.com/32350208/123690995-b20d0080-d872-11eb-80bf-0cdf4431caa5.png)

- Heatmap of AUC of Test data of SET 1
![image](https://user-images.githubusercontent.com/32350208/123691006-b76a4b00-d872-11eb-994b-bcd7f869beab.png)

- Reciever Operating Characteristic Curve of SET 1
![image](https://user-images.githubusercontent.com/32350208/123691032-bf29ef80-d872-11eb-86a1-05d84d477031.png)

- confusion matrix of TEST data of SET 1
![image](https://user-images.githubusercontent.com/32350208/123691060-c81ac100-d872-11eb-8321-99ba41be1815.png)

__SET 2:__
- Heatmap of AUC of Training data of SET 2
![image](https://user-images.githubusercontent.com/32350208/123690817-75410980-d872-11eb-8cbb-60ac02c77b34.png)

- Heatmap of AUC of Test data of SET 2
![image](https://user-images.githubusercontent.com/32350208/123690840-7e31db00-d872-11eb-9bf5-f39865d6cfa3.png)

- Reciever Operative Characteristics(ROC-AUC) Curve of SET 2
![image](https://user-images.githubusercontent.com/32350208/123690851-85f17f80-d872-11eb-8b56-05ac8b8ccebb.png)

- Confusion Matrix of TEST data of SET 2
![image](https://user-images.githubusercontent.com/32350208/123690887-9144ab00-d872-11eb-8707-232faa279dc5.png)



## Credit
- [Applied AI Course](https://www.appliedaicourse.com): For teaching in-depth Machine Learning, Deep Learning, Computer Vision, NLP, and end-to-end problem solving.

- [Machine Learning Mastery](https://www.machinelearningmastery.com): For best Machine Learning blogs.
