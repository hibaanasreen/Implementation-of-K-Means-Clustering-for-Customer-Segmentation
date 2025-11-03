# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load and preprocess data: Import data, inspect it, and handle missing values if any.

2.Determine optimal clusters: Use the Elbow Method to identify the number of clusters by plotting WCSS against cluster numbers.

3.Fit the K-Means model: Apply K-Means with the chosen number of clusters to the selected features.

4.Assign cluster labels to each data point.


## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Hiba Nasreen M
RegisterNumber:212224040117  

```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
```
```
data.head()

data.info()

data.isnull().sum()
```
```
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++",n_init=10)
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
```
```
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
```
```
km = KMeans(n_clusters=5, n_init=10)
km.fit(data.iloc[:, 3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
```
```
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
```
```
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster1")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster2")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster4")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster5")
plt.legend()
plt.title("Customer Segments")
```
## Output:

<img width="836" height="255" alt="image" src="https://github.com/user-attachments/assets/0581cc54-ee38-435f-a22d-681e609eddfd" />


<img width="720" height="279" alt="image" src="https://github.com/user-attachments/assets/8a0c2299-5ceb-424f-9d15-e86a476589f5" />


<img width="400" height="291" alt="image" src="https://github.com/user-attachments/assets/cd49ae2c-4694-4972-9313-69567873f7fc" />


<img width="1234" height="601" alt="image" src="https://github.com/user-attachments/assets/2d4932fa-cf62-4e49-a12b-a92cfbb6d7d2" />


<img width="827" height="239" alt="image" src="https://github.com/user-attachments/assets/4d2b1768-90f2-4c12-945e-6bb8332d6aff" />


<img width="1035" height="584" alt="image" src="https://github.com/user-attachments/assets/5590139b-c497-4108-b552-c4e751784a9d" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
