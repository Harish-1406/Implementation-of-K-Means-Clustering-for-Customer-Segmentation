# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: HARISH P K
RegisterNumber:  212224040104
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
data = pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.title('The Elbow Method')
plt.xlabel('Number of clusters')
plt.ylabel('WCSS')
plt.show()
km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:]) 
y_pred

data["clusters"]=y_pred
df0=data[data["clusters"]==0]
df1=data[data["clusters"]==1]
df2=data[data["clusters"]==2]
df3=data[data["clusters"]==3]
df4=data[data["clusters"]==4]


plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],color="red")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],color="blue")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],color="green")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],color="yellow")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],color="black")
```
## Output:

![image](https://github.com/user-attachments/assets/514c7b69-e3ca-4446-b860-f605e9f933ab)
![image](https://github.com/user-attachments/assets/a655b3fb-01a4-4211-aea1-9a657da96d94)
![image](https://github.com/user-attachments/assets/a475c9a5-e565-44f3-91f7-e6e866a37893)
![image](https://github.com/user-attachments/assets/6423c112-7430-40c4-8400-a159da29685c)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
