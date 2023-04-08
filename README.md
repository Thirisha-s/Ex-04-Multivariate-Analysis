# Ex-04-Multivariate-Analysis
# AIM
To perform Multivariate EDA on the given data set.

# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
# STEP 1
Import the built libraries required to perform EDA and outlier removal.

# STEP 2
Read the given csv file

# STEP 3
Convert the file into a dataframe and get information of the data.

# STEP 4
Return the objects containing counts of unique values using (value_counts()).

# STEP 5
Plot the counts in the form of Histogram or Bar Graph.

# STEP 6
Use seaborn the bar graph comparison of data can be viewed.

# STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

# STEP 8
Save the final data set into the file

# PROGRAM
Name : s.thirisha
Register Number : 212222230160
```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(df['Row ID'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```
# OUTPUT
# DATA:
![image](https://user-images.githubusercontent.com/120380280/230703454-a65c2639-f49f-4f7c-a030-5fb39b1f5081.png)
# DATA INFORMATION:
![image](https://user-images.githubusercontent.com/120380280/230703466-7a9226a8-b50a-47bf-b39b-18b39d4bb3b3.png)
# DATA DESCRIBE:
![image](https://user-images.githubusercontent.com/120380280/230703477-e8317b3e-b5c1-4bfa-b62f-c6cb3857c975.png)
# Checking the null values and Cleaning it
![image](https://user-images.githubusercontent.com/120380280/230703498-f3fa684b-c874-4c14-a15f-49d89f57dcc3.png)

![image](https://user-images.githubusercontent.com/120380280/230703500-d04eec4f-28fd-47d8-88dd-97040b43cf83.png)
# DATA TYPES
![image](https://user-images.githubusercontent.com/120380280/230703513-d9e9287f-8969-4c17-aa45-168ab4ca4bbb.png)
# SCATTERPLOT
![image](https://user-images.githubusercontent.com/120380280/230703531-9474a30c-0615-4619-b10f-867bdf7a7ed6.png)
# BARPLOT
![image](https://user-images.githubusercontent.com/120380280/230703542-5133ab39-e3f0-4f85-8591-ceb69cf3af75.png)
![image](https://user-images.githubusercontent.com/120380280/230703548-658f8e66-b4e5-48cd-88fa-f4c0a0501507.png)
![image](https://user-images.githubusercontent.com/120380280/230703552-a42ef4af-b50e-44e5-97f0-57b8cb8043e1.png)
![image](https://user-images.githubusercontent.com/120380280/230703559-4ed2edd3-270c-4dbb-9c34-7b2ee52ed624.png)
# CORRELATION COEFFICIENT INTERPRETATION
![image](https://user-images.githubusercontent.com/120380280/230703573-737e54f1-4325-4075-9b00-52a8fdc37133.png)
# HEAT MAP
![image](https://user-images.githubusercontent.com/120380280/230703579-6884c5ca-69d3-4a6c-b633-ebcc057a466e.png)

# RESULT:
Thus we have read the given data and performed the multivariate analysis with different types of plots.

