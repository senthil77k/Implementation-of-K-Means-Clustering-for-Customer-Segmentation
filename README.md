# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step 1. Start the program

Step 2. Import the necessary python libraries

Step 3. Read the dataset of Mall_Customers csv file

Step 4. From sklearn libraary select the cluster and import KMeans Clustering

Step 5. Find the sum of squared distance between each points and the centroid in a cluster using Elbow Method

Step 6. Plot the graph x and y as Number of Clusters and wcss respectively

Step 7. Using the matplotlib library draw the scatter plot for the given number of clusters (ie. here n_clusters = 5)

Step 8. Stop the program

## Program:
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: senthil kumaran c
RegisterNumber:  212223220103
*/
```
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("Mall_Customers.csv")
df.head()
df.info()
df.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(df.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No.of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(df.iloc[:,3:])
y_pred = km.predict(df.iloc[:,3:])
print("Predicted values : ")
y_pred
df["cluster"] = y_pred
df0 = df[df["cluster"]==0]
df1 = df[df["cluster"]==1]
df2 = df[df["cluster"]==2]
df3 = df[df["cluster"]==3]
df4 = df[df["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer segments")
```

## Output:
Head:

![376100284-e1d8328a-0ac9-45ee-bc33-c686b77ead99](https://github.com/user-attachments/assets/63f8de99-ffa6-4be4-87e3-6911d8258014)

Info:

![376100303-bd2d38f4-4ed4-4532-bb00-d9463c10b8d3](https://github.com/user-attachments/assets/fadea0b3-fa9d-4bc9-b0e6-f7436181caad)

No.of Null-values:

![376100340-a849602f-d3e3-4ead-9d3d-f08a841400db](https://github.com/user-attachments/assets/a88594b7-55ac-4798-ae14-786615717d3f)

Graph:

![376100367-154cef8e-c91c-44dc-972c-274630f3a75e](https://github.com/user-attachments/assets/e9120384-dc30-4c81-a527-7a88d9faeb52)

No.of cluster:

![376100411-bbd7ca4e-a52a-48b2-bfe2-f1bd4cc369be](https://github.com/user-attachments/assets/8034337e-3852-41d6-a692-5548829cf852)

predicted values:

![376100438-e53b1ffc-bfdc-4773-ae38-ec3d45fe1273](https://github.com/user-attachments/assets/cc3dbcb6-2197-43ec-8286-18c46e3000ac)

customer segments:

![376100478-e22ff6e8-9ebb-44a5-a9bf-2ed1a5a36a4c](https://github.com/user-attachments/assets/e684aed7-63fe-446f-a13c-392e5d7de845)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
