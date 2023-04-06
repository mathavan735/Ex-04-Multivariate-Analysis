# Ex-04-Multivariate-Analysis

## AIM:

To perform Multivariate EDA on the given data set.

## EXPLANATION:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:

Step1:

Import the built libraries required to perform EDA and outlier removal.

Step2:

Read the given csv file.

Step3:

Convert the file into a dataframe and get information of the data.

Step4:

Return the objects containing counts of unique values using (value_counts()).

Step5:

Plot the counts in the form of Histogram or Bar Graph.

Step6:

Use seaborn the bar graph comparison of data can be viewed.

Step7:

Find the pairwise correlation of all columns in the dataframe.corr()

Step8:

Save the final data set into the file.
## PROGRAM:
```
Developed by : MATHAVAN S
Registration Number :212221220031
```
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df.head(6)
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
sns.scatterplot (df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Postal Code"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Postal Code",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("Postal Code")
plt.show()
states=df.loc[:,["Segment","Sales"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")
#plt.figure(figsize=(10,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()
sns.barplot(df['Postal Code'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```

## OUTPUT:

SuperStore.csv

df.head()

![op@](https://user-images.githubusercontent.com/118707079/230075321-a13c1c72-e11e-4463-b343-f10182102e20.png)

df.info()

![outputcolab](https://user-images.githubusercontent.com/118707079/230075538-95c74f11-22fc-4c22-a319-0800c912829c.png)

df.describe()

![describe](https://user-images.githubusercontent.com/118707079/230075739-577de1b9-fb0e-4d77-a0e0-d1b2716e3071.png)

df.isnull().sum()

![df](https://user-images.githubusercontent.com/118707079/230076216-554d064d-95a4-4773-a28c-883d11518b88.png)

AFTER CLEANING:
df.isnull().sum()

![after](https://user-images.githubusercontent.com/118707079/230076495-8e2546dd-90fc-487d-a3f3-27ee018eb056.png)

Scatterplot

![scatter](https://user-images.githubusercontent.com/118707079/230076603-87b58da0-de89-4a98-8417-170acaae4adb.png)

Barplot

![barplot](https://user-images.githubusercontent.com/118707079/230078473-121a08a7-adba-41ba-8ddf-9e59c87fec99.png)
![barplot2](https://user-images.githubusercontent.com/118707079/230076827-588671d8-f001-4c45-8072-fad05f4767e7.png)
![bar3](https://user-images.githubusercontent.com/118707079/230076926-1d1b3ae7-46b4-42f8-b533-50dfe5721a05.png)

HeatMap

![heatmap](https://user-images.githubusercontent.com/118707079/230077105-a6b74637-8d64-498c-b08b-c8bdaf0c3ea8.png)

## RESULT:

Thus the program to perform EDA on the given data set is successfully executed.



















