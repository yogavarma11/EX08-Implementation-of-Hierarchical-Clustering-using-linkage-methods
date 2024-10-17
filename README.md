# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:
1.compute the distance between every pair of data points,resulting in a distance matrix

2.assign each data point to its own individual cluster

3.using a linkage criterion,find the two closest cluster and merge them

4.visualize the hierarchical clustering as a dendrogram


## Program:
```

Program to implement Hierarchical Clustering using single and complete linkage method
Developed by: YOGAVARMA B
RegisterNumber:2305002029

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage,fcluster
from sklearn.preprocessing import StandardScaler
df = pd.read_csv("/content/Hclus_EX8.csv")
df.head()
x = df[['StudentID','Marks']].values
x
z=linkage(x,method='complete')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
max_cluster=2
clusters=fcluster(z,max_cluster,criterion='maxclust')
clusters
plt.figure(figsize=(5,2))
plt.scatter(x[:,0],x[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student segmented(Hierarchical clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
z=linkage(x,method='single')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()


```

## Output:
![image](https://github.com/user-attachments/assets/0508573b-436b-4110-aa31-eb1b0cab1c99)
![image](https://github.com/user-attachments/assets/4865aa37-ef41-446b-932a-127c9e759df9)
![image](https://github.com/user-attachments/assets/c341525c-c871-4055-9873-6cb4c51f0b73)






## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.
