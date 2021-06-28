# SGD for Recommender System

## SGD Algorithm to predict movie ratings

1. Download the data from here: [Click to download](https://drive.google.com/file/d/1-1z7iDB52cB6_JpO7Dqa-eOYSs-mivpq/view)
2. The data will be of this format, each data point is represented as a triplet of `user_id`, `movie_id` and `rating`.

| user_id | movie_id | rating |
| :--     | :--:     |  --:   |
|  77 | 236 | 3 |
| 471 |208 |5 |
| 641 | 401| 4|
|31 |298 | 4|
|58 |504 |5 |
|235|727 | 5|

__Predict the rating for a given(user_id, movie_id) pair__

Predicted rating yij_predicted for user i, movied j pair is calculated as yij_predicted=mu+bi+cj+uiTvj, here we will be finding the best values of bi and cj using SGD algorithm with the optimization problem for N users and M  movies is defined as 

![image](https://user-images.githubusercontent.com/32350208/123702625-ff906a00-d880-11eb-9737-60704be8c454.png)

![image](https://user-images.githubusercontent.com/32350208/123703044-834a5680-d881-11eb-8442-3409418aff5a.png)

__For further details, see the PDF file of the assignment before running the notebook.__


## Credit 
- [Applied AI Course](https://www.appliedaicourse.com): For teaching in-depth Machine Learning and Deep Learning.
