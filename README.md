# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed 
   using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the output and end the program.



## Program:

```py
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: PRIYANKA.A
RegisterNumber:  212222230113
*/

import numpy as np
import pandas as pd

import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range (1,11):
kmeans=KMeans(n_clusters = i,init="k-means++")
kmeans.fit(data.iloc[:,3:])
wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow matter")
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
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-
100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-
100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-
100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-
100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-
100)"],c="magenta",label="cluster4")

plt.legend()
plt.title("Customer Segmets")

```

## Output:
## DATASET:
![281975354-8c29a6e1-9f13-49ec-ad7f-52a2a6ceae0b](https://github.com/DhanalakshmiCSE/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477832/d40d7994-05c8-4fc8-a325-1c155027e8cc)
## data.head():
![281975377-28f86f70-eaaa-49a5-8534-b8c8e69d7d31](https://github.com/DhanalakshmiCSE/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477832/deb74fb4-afb0-418a-83ca-0ecfa11f11b1)
## data.info():
![281975413-91a49a82-871f-4aa3-8c9f-75644fd911d2](https://github.com/DhanalakshmiCSE/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477832/2c77531a-5348-4721-a1ca-253d0e0fe4ac)
## data.isnull() & sum():
![281975438-723f23ce-744b-4357-8873-6c48a81e17a6](https://github.com/DhanalakshmiCSE/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477832/f8479871-7b6b-48ba-b213-c8d10444439f)
## Elbow method graph:
![281975465-af124f8a-c6a7-42a7-8623-4e3bcd2a1ab7](https://github.com/DhanalakshmiCSE/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477832/2eb45380-b82a-4564-9e80-ee5823d0c3d3)
## K means cluster:
![281975484-c1e5241d-e46f-4a0b-ba7d-a2034dcdb4e6](https://github.com/DhanalakshmiCSE/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477832/d618eb9d-0dda-4109-82cd-bf2260450359)
## Y_prediction value:
![281975504-7209528d-b484-4b0c-9961-9f3af99f1eb9](https://github.com/DhanalakshmiCSE/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477832/23b83724-e69d-45fe-be8b-d2ec32d0f0b4)
## Customers Segments Graph:
![281975518-3aa6d9ca-b7a2-4d93-8ac2-98a4e2ccaaea](https://github.com/DhanalakshmiCSE/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477832/3c71ecbc-4392-4249-bc58-52b02353e955)




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
