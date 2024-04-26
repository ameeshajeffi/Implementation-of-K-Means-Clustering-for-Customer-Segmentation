# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program.
```
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Ameesha jeffi J
RegisterNumber: 212223220007 
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans (n_clusters = i, init ="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Metthod")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
# Output:

## Dataset

![324679792-64aa93ee-7b06-4b99-bcf9-eb87160ee2fc](https://github.com/ameeshajeffi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150773598/40dd2c9b-450f-496f-a5ff-7c57ad8dd730)

## Dataset information:

![324679808-20e181e8-519c-4606-93a5-ca6e3fb8c900](https://github.com/ameeshajeffi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150773598/0f1c75a3-365b-4160-8b96-1a2f82706d4d)

![324679821-6bf01c5b-c59a-4a8c-9215-574b53222608](https://github.com/ameeshajeffi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150773598/0e08f7ee-d171-4590-a96c-353e3b7e2a2a)


## Elbow method graph (wcss vs each iteration):

![324679840-fcdb3211-91ef-435e-9284-cdf30c0718b3](https://github.com/ameeshajeffi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150773598/9139f4a7-3479-4c4d-a700-495c6b560c05)

## Cluster represnting customer segments-graph:

![324679896-90dcbe41-bc91-476b-87b5-9747f42a4312](https://github.com/ameeshajeffi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150773598/303c8219-01fc-4949-846f-6b2e16a0231e)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
