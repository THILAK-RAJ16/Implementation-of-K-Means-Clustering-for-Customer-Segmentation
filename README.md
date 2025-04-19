# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplotlib.pyplot

2. Read the dataset and transform it

3. Import KMeans and fit the data in the model

4. Plot the Cluster graph

## Program:

Program to implement the K Means Clustering for Customer Segmentation.
```
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv(r"C:\Users\admin\Downloads\Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters=i, init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")

km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred

df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster 0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster 1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster 2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster 3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster 4")

plt.legend()
plt.title("customer segmentation")
```
Developed by: Thilak Raj . P

RegisterNumber:  212224040353


## Output:
![image](https://github.com/user-attachments/assets/ae9bc3f4-75eb-446a-ba2a-f24e7f327791)

![image](https://github.com/user-attachments/assets/acb487db-0041-449c-82ab-39fe6a5d73da)

![image](https://github.com/user-attachments/assets/cc5c836e-ea2b-4471-aa93-51c7e57c9b34)

![image](https://github.com/user-attachments/assets/d9b5012b-5848-4bbe-a9e2-b3c62932a10a)

![image](https://github.com/user-attachments/assets/c6150a31-0252-45a2-b7d5-5b9e2d59c495)

![image](https://github.com/user-attachments/assets/0a7bc5a1-891c-4346-b1e5-981508a8e800)

![image](https://github.com/user-attachments/assets/d6c682f3-5118-4ec2-8a47-466f5e8e50e4)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
