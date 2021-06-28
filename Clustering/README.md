# Apply Clustering to group similar actors and movies

## Problem Statement
There are two main problems
1. __clustering to group similar actors.__
2. __clustering to group similar movies.__


## Dataset
Data set is given in the form of bi-partite graph containing source(actor) and destination(movie) nodes/columns.

- __Example of a bi-partite graph__:
- ![image](https://user-images.githubusercontent.com/32350208/123627665-e57a6b80-d82f-11eb-8b9c-7036bb4d2cce.png)

- __Example of the dataset__:
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>movie</th>
      <th>actor</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>m1</td>
      <td>a1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>m2</td>
      <td>a1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>m2</td>
      <td>a2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>m3</td>
      <td>a1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>m3</td>
      <td>a3</td>
    </tr>
  </tbody>
</table>
</div>

## Instructions to solve the given problem

- Read graph from the given `movie_actor_network.csv`(note that the graph is bipartite graph.)

- Using `stellergaph` and `gensim` packages, get the dense representation(128dimensional vector) of every node in the graph. [Refer: `Clustering_Assignment_Reference.ipynb`]

- Split the dense representation into actor nodes, movies nodes.(Write you code in `def data_split()`)

## ML Modeling
- This is an unsupervised learning problem.
- This is clustering problem
- I used K-Means Algorithm

## Metrics
- I used Custom metrics to judge the ML model.

## Instruction of each problem

### Problem 1:
 1. For this task consider only the actor nodes 
 2. Apply any clustering algorithm of your choice <br>
    Refer : https://scikit-learn.org/stable/modules/clustering.html
 3. Choose the number of clusters for which you have maximum score of <b>$Cost1*Cost2$</b><br>
 4. Cost1 = $\frac{1}{N} \sum_{\text{each cluster i}}  \frac{\text{(number of nodes in the largest connected component in the graph with the actor nodes and its movie neighbours in cluster i)}}{\text{(total number of nodes in that cluster i)}}$ where N= number of clusters 
<br> (Write your code in `def cost1()`<br>
 5. Cost2 = $\frac{1}{N}\sum_{\text{each cluster i}}  \frac{\text{(sum of degress of actor nodes in the graph with the actor nodes and its movie neighbours in cluster i)}}{\text{(number of unique movie nodes in the graph with the actor nodes and its movie neighbours in cluster i)}}$ where N= number of clusters 
 <br> (Write your code in `def cost2()`)<br>
 6. Fit the clustering algorithm with the opimal number_of_clusters and get the cluster number for each node <br>
 7. Convert the d-dimensional dense vectors of nodes into 2-dimensional using dimensionality reduction techniques (preferably TSNE)<br>
 8. Plot the 2d scatter plot, with the node vectors after step e and give colors to nodes such that same cluster nodes will have same color

### Problem 2:


1. For this task consider only the movie nodes
2. Apply any clustering algorithm of your choice
3.Choose the number of clusters for which you have maximum score of <b>$Cost1*Cost2$</b><br>
Cost1 = $\frac{1}{N}\sum_{\text{each cluster i}}  \frac{\text{(number of nodes in the largest connected component in the graph with the movie nodes and its actor neighbours in cluster i)}}{\text{(total number of nodes in that cluster i)}}$ where N= number of clusters <br>
(Write your code in `def cost1()`)<br>
	
4. Cost2 = $\frac{1}{N}\sum_{\text{each cluster i}}  \frac{\text{(sum of degress of movie nodes in the graph with the movie nodes and its actor neighbours in cluster i)}}{\text{(number of unique actor nodes in the graph with the movie nodes and its actor neighbours in cluster i)}}$ 
where N= number of clusters 
<br>(Write your code in `def cost2()`)<br>


## Solved Visualizations

- __cluster of similar actors__:

![image](https://user-images.githubusercontent.com/32350208/123627842-19559100-d830-11eb-8342-dcbead2df49d.png)

- __cluster of similar movies__:

![image](https://user-images.githubusercontent.com/32350208/123627925-325e4200-d830-11eb-9996-f5a2d6a22bc2.png)

## Credit
- [Applied AI Course](https://www.appliedaicourse.com): For teaching in-depth Machine Learning and Deep Learning.
