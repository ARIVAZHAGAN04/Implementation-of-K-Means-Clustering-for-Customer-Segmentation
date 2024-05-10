# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset
2.check for null values
3.Import kmeans and fit it to the dataset
4.Plot the graph using elbow method
5.Print the predicted array
6.Plot the customer segments

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: ARIVAZHAGAN G R
RegisterNumber:  212223040020
*/
```

import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0=data[data["cluster"]==0]

df1=data[data["cluster"]==1]

df2=data[data["cluster"]==2]

df3=data[data["cluster"]==3]

df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segment")

## Output:
![image](https://github.com/ARIVAZHAGAN04/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/161414455/a5d37232-b292-4e40-b267-0608941ad15b)
![image](https://github.com/ARIVAZHAGAN04/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/161414455/f9f9b491-70c5-489e-a3ae-379971f697e5)
![image](https://github.com/ARIVAZHAGAN04/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/161414455/62e5588d-914a-4176-b1be-e49c3eae7c04)
![image](https://github.com/ARIVAZHAGAN04/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/161414455/b139a7d7-f265-4a2a-93b9-ed7d72c85541)
![image](https://github.com/ARIVAZHAGAN04/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/161414455/98052ae4-0650-46b3-914b-846ac0f00055)
![image](https://github.com/ARIVAZHAGAN04/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/161414455/40f0486f-6c5a-443d-9b8c-92a8e67f6008)
![image](https://github.com/ARIVAZHAGAN04/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/161414455/4fff88e1-d1fb-4a91-833a-27ed09ff63ec)




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
