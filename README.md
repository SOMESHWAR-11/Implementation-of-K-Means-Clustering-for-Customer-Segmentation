# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3. Import KMeans and use for loop to cluster the data.

4. Predict the cluster and plot data graphs.

5. Print the outputs and end the program.
## Program:

```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SOMESHWAR S
Register Number:  212224040322
*/
```
```


import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('Mall_Customers.csv')

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = [] #Within-Cluster Sum of Square.
#It is the sum of squared distance between each point & the centroid in a cluster

for i in range(1,11):
    kmeans = KMeans(n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11), wcss)
plt.xlabel("Number of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])
KMeans(n_clusters = 5)

y_pred = km.predict(data.iloc[:, 3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:

![Screenshot 2025-05-18 143308](https://github.com/user-attachments/assets/6ac61ff8-2859-4c94-9ed1-e227036f6fc2)

![Screenshot 2025-05-18 143315](https://github.com/user-attachments/assets/24daad55-c1ae-4ba8-bd83-cb23529b9d2b)

![Screenshot 2025-05-18 143326](https://github.com/user-attachments/assets/04a1ee65-bc03-4e69-9ab9-34d76d2041a4)

![Screenshot 2025-05-18 143338](https://github.com/user-attachments/assets/cd977b3a-7291-4894-a4ce-250a75c69418)

![Screenshot 2025-05-18 143348](https://github.com/user-attachments/assets/5fc7806d-e120-42af-9772-49983233fa0a)

![Screenshot 2025-05-18 143406](https://github.com/user-attachments/assets/c97f9748-20d1-4c3a-a9a7-703872e4c90f)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
