# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 12.08.25

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
~~~
import numpy as np # linear algebra
import pandas as pd # data processing, CSV file I/O (e.g. pd.read_csv)
import os
for dirname, _, filenames in os.walk('/kaggle/input'):
    for filename in filenames:
        print(os.path.join(dirname, filename))
        df=pd.read_csv("/content/housing_price_dataset.csv.zip")
df.head()
df.info()
df.isnull().sum()
df.duplicated().sum()
df.describe()
# Plot the top 15 most frequent neighborhoods (including NaNs if present)
top_neighborhoods = df['YearBuilt'].value_counts().nlargest(15).index
filtered_df = df[df['YearBuilt'].isin(top_neighborhoods)]

# Plot
import seaborn as sns
import matplotlib.pyplot as plt
plt.figure(figsize=(14, 6))
sns.countplot(data=filtered_df, x='YearBuilt', order=top_neighborhoods, palette='pastel')
plt.xlabel('Yearbuilt')
plt.ylabel('Price')
plt.xticks(rotation=45, ha='right')
plt.tight_layout()
plt.show()
plt.figure(figsize=(10, 6))
sns.scatterplot(data=df, x='YearBuilt', y='Price', color='darkorange', alpha=0.7)
plt.title('Relationship Between YearBuilt and Price')
plt.xlabel('YearBuilt')
plt.ylabel('Price')
plt.tight_layout()
plt.show()

~~~

# OUTPUT:
<img width="1135" height="674" alt="image" src="https://github.com/user-attachments/assets/349352f3-5ef7-4120-ae00-8cc909729156" />






# RESULT:
Thus we have created the python code for plotting the time series of given data.
