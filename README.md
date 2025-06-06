# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import dataset and print head,info of the dataset
2. check for null values
3. Import kmeans and fit it to the dataset
4. Plot the graph using elbow method
5. Print the predicted array
6. Plot the customer segments

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: V.Shriyha
RegisterNumber: 212224230267
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
```

## Output:

# DATA.HEAD():
![image](https://github.com/user-attachments/assets/7366e2b3-4cfa-467b-b7ed-84f5cf84fd91)

# DATA.INF0():
![image](https://github.com/user-attachments/assets/2066ecff-087e-4e31-9ec3-f012efb9a07b)

# DATA.ISNULL().SUM():
![image](https://github.com/user-attachments/assets/2f6816d8-a9d5-4060-b0d2-06747c89a160)

# PLOT USING ELBOW METHOD:
![image](https://github.com/user-attachments/assets/2fe94dda-35fd-4440-97f6-bdfe74243059)

# K-MEANS CLUSTERING:
![image](https://github.com/user-attachments/assets/376c6835-65b4-4a67-a8c8-67120ddb5c25)

# Y_PRED ARRAY:
![image](https://github.com/user-attachments/assets/3617ae0c-b152-44b2-a8cf-79e3364d91ce)

# CUSTOMER SEGMENT:
![image](https://github.com/user-attachments/assets/259d3a6e-038d-47a2-b7a5-ea523e3bd403)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
