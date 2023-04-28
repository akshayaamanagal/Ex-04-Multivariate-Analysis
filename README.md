# Ex-04-Multivariate-Analysis
# AIM:
To perform Multivariate EDA on the given data set.
# EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset.
This technique involves many iterative processes to ensure that the cleaned data
is further sorted to better understand the useful meaning.The primary aim with
exploratory analysis is to examine the data for distribution, outliers and
anomalies to direct specific testing of your hypothesis.
# ALGORITHM:
### STEP 1
Import the built libraries required to perform EDA and outlier removal.
### STEP 2
Read the given csv file
### STEP 3
Convert the file into a dataframe and get information of the data.
### STEP 4
Return the objects containing counts of unique values using (value_counts()).
### STEP 5
Plot the counts in the form of Histogram or Bar Graph.
### STEP 6
Use seaborn the bar graph comparison of data can be viewed.
### STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()
### STEP 8
Save the final data set into the file
# PROGRAM
```
Developed by: Akshayaa M
Register Number: 212222230009
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("SuperStore.csv")
data
data.head()
data.info()
data.describe()
data.dtypes
data.isnull().sum()
data['Postal Code']=data['Postal Code'].fillna(data['Postal Code'].mode()[0])
data.isnull().sum()

sns.scatterplot(x=data['Country'],y=data['Sales'],data=data)

states=data.loc[:,["Region","Sales"]]
states=states.groupby(by=["Region"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("REGION")
plt.ylabel=("SALES")
plt.show()

states=data.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SALES")
plt.ylabel=("STATES")
plt.show()

states=data.loc[:,["Category","Sales"]]
states=states.groupby(by=["Category"]).sum().sort_values(by="Sales")
plt.figure(figsize=(10,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("CATEGORY")
plt.ylabel=("SALES")
plt.show()

data.corr()

sns.heatmap(data.corr(),annot=True)
```
# OUTPUT:
![Ex-04-Multivariate-Analysis](1.png)
![Ex-04-Multivariate-Analysis](2.png)
![Ex-04-Multivariate-Analysis](3.png)
![Ex-04-Multivariate-Analysis](4.png)
![Ex-04-Multivariate-Analysis](5.png)
![Ex-04-Multivariate-Analysis](6.png)
![Ex-04-Multivariate-Analysis](7.png)
![Ex-04-Multivariate-Analysis](8.png)
![Ex-04-Multivariate-Analysis](9.png)
# RESULT:
Hence The Performance of the Multivariate EDA on the given data set is verified