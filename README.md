# Mini-Project
# SALARY  VISUALIZATION
# DEVELOPED BY: Lavanya S
# REG NO :212221220030
# AIM
To Perform Data Visualization on the given dataset and save the data to a file.
# Explanation
Data visualization is the graphical representation of information and data. By using visual elements
like charts, graphs, and maps, data visualization tools provide an accessible way to see and
understand trends, outliers, and patterns in data.
# ALGORITHM
STEP 1
Read the given Data
STEP 2
Clean the Data Set using Data Cleaning Process
STEP 3
Apply Feature generation and selection techniques to all the features of the data set
STEP 4
Apply data visualization techniques to identify the patterns of the data.
# program
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/glassdoor-data-engineer.csv",encoding="ISO-8859-1")
df
df.isnull()
df.info()
df.describe()
sns.lineplot(x="company",y="company_rating",data=df,marker='o')
plt.title("company vs company_rating")
plt.xticks(rotation = 90)
plt.show()
sns.barplot(x="company",y="company_rating",data=df)
plt.xticks(rotation = 90)
plt.show()
df.shape
df1 = df[(df.salary_estimate >= 60)]
df1.shape
plt.figure(figsize=(30,8))
states=df1.loc[:,["location","salary_estimate"]]
states=states.groupby(by=["location"]).sum().sort_values(by="salary_estimate")
sns.barplot(x=states.index,y="salary_estimate",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("location")
plt.ylabel=("salary_estimate")
plt.show()
sns.barplot(x="company_type",y="salary_estimate",data=df)
plt.show()
sns.lineplot(x="company_type",y="salary_estimate",data=df)
plt.show()
states=df.loc[:,["company_type","company_rating"]]
states=states.groupby(by=["company_type"]).sum().sort_values(by="company_rating")
sns.barplot(x=states.index,y="company_rating",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("company_type")
plt.ylabel=("company_rating")
plt.show()
df.groupby(['company_type']).sum().plot(kind='pie', y='company_rating',figsize=(6,9),pctdistance=1.7,labeldistance=1.2)
df["company_rating"].corr(df["salary_estimate"])
df_corr = df.copy()
df_corr = df_corr[["company_rating","salary_estimate"]]
df_corr.corr()
sns.pairplot(df_corr, kind="scatter")
plt.show()
grouped_data = df.groupby('company')[['company_rating', 'salary_estimate']].mean()
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['company_rating'], label='company_rating')
ax.bar(grouped_data.index, grouped_data['salary_estimate'], bottom=grouped_data['company_rating'], label='salary_estimate')
ax.set_xlabel('company')
ax.set_ylabel('Value')
ax.legend()
plt.show()
grouped_data = df.groupby('location')[['company_rating', 'salary_estimate']].mean()
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['company_rating'], label='company_rating')
ax.bar(grouped_data.index, grouped_data['salary_estimate'], bottom=grouped_data['company_rating'], label='salary_estimate')
ax.set_xlabel('location')
ax.set_ylabel('Value')
ax.legend()
plt.show()
grouped_data = df.groupby('company_sector')[['company_rating', 'salary_estimate']].mean()
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['company_rating'], label='company_rating')
ax.bar(grouped_data.index, grouped_data['salary_estimate'], bottom=grouped_data['company_rating'], label='salary_estimate')
ax.set_xlabel('company_sector')
ax.set_ylabel('Value')
ax.legend()
plt.show()grouped_data = df.groupby(['company', 'company_type'])[['company_rating', 'salary_estimate']].mean()
pivot_data = grouped_data.reset_index().pivot(index='company', columns='company_type', values=['company_rating', 'salary_estim'])
fig, ax = plt.subplots()
pivot_data.plot(kind='bar', ax=ax)
ax.set_xlabel('company')
ax.set_ylabel('Value')
plt.legend(title='company_type')
plt.show()
```
# output:
![image](https://github.com/LavanyaSIT/Mini-Project/assets/130207418/b1db2271-27a5-4005-9a92-9c3e9dc3140c)
![image](https://github.com/LavanyaSIT/Mini-Project/assets/130207418/e75d85bb-46e3-4ac3-8763-4ce06165fd14)
![image](https://github.com/LavanyaSIT/Mini-Project/assets/130207418/e5368964-645f-4f01-bd5a-4630eb81924e)
![image](https://github.com/LavanyaSIT/Mini-Project/assets/130207418/b6c244ff-b303-4e9f-afb0-f7692963afaf)
![image](https://github.com/LavanyaSIT/Mini-Project/assets/130207418/c8d2784d-dbc0-4f64-b4bb-615766e6fbeb)
![image](https://github.com/LavanyaSIT/Mini-Project/assets/130207418/36634d9f-8cf9-4963-9096-de3cdf42c411)
![image](https://github.com/LavanyaSIT/Mini-Project/assets/130207418/53439a8d-a2a2-45ab-bed4-81bfc305f6d8)
![image](https://github.com/LavanyaSIT/Mini-Project/assets/130207418/f1ff43e6-225e-4c60-94a7-a7834ecf2fe5)
![image](https://github.com/LavanyaSIT/Mini-Project/assets/130207418/1e53d202-f967-4dfe-99db-7623f146cf42)
![image](https://github.com/LavanyaSIT/Mini-Project/assets/130207418/4f2480f4-0272-4fe5-83db-45ecd850e41a)
![image](https://github.com/LavanyaSIT/Mini-Project/assets/130207418/fad0fddf-acec-4469-9314-29591d85defe)





# RESULT: Data Visualization has been performed on a complex dataset and saved the data to a file
