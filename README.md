# Ex-01_DS_Data_Cleansing


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE and OUTPUT
```py
DEveloped by:Kanishka.V.S
Register no:212222230061
```
```py
import pandas as pd
df = pd.read_csv("SAMPLEDS - Sheet1.csv")
df.shape
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/31158b5d-8ae4-4e64-a27b-68d9265fbdab)
```py
df.head()
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/84eb4cd2-8bb6-4af6-8e3e-ff6fa636b87b)
```py
df.tail()
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/d3d1ecd0-2451-43d7-9669-c250f442f320)
```py
df.dropna(how='any').shape
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/e9f4f819-cb40-4227-9917-64ff93e26862)
```py
x=df.dropna(how='any')
x
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/5f7ea8b6-1f74-4a6e-b22f-510819c105f6)
```py
df.dropna(how='all').shape
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/397529ce-6590-40a6-bee1-9019a717f1f6)
```py
tot=df.dropna(subset=['TOTAL'],how='any')
tot
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/61167456-24c7-418c-b6b4-fcd64f498e67)
```py
tot=df.dropna(subset=['M1','M2','M3','M4'],how='any')
tot
``
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/d47474ed-9262-48b1-aac6-092464d32ede)
```py
df.fillna(0)
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/edefe631-0bc0-4d1b-8b5c-5d2e80fea0be)
```py
df.fillna(method='ffill')
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/aaf1234a-c963-4c38-a011-b739dac20814)
```py
df.fillna(method='bfill')
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/70e76d1a-3788-4569-acb6-f9bddcb7dc94)
```py
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/de7c50a0-b1d6-4f36-b999-fe9127f4f637)
```py
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/12e36e4b-b766-4bf1-bb34-80ca1920e7df)
```py
df.duplicated()
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/26659c91-14b6-420e-9466-45193a49b034)
```py
df.drop_duplicates(inplace=True)
df
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/0f024713-1085-45e8-8dad-693ac0824f0b)
```py
df['cd']=pd.to_datetime(df['DOB'])
df
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/68afca58-4f87-4eb8-a785-c9b3ee1d9ab6)
```py
for x in df.index:
  if df.loc[x,"AVG"]>100:
    df.drop(x,inplace=True)
df
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/136b6297-3dc3-489d-95b4-dadb4e0e38e0)
```py
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex01/assets/113497357/b09f607d-5898-4ecb-88e5-af1bf51b5405)
# Result:
Thus,the given data is read,cleansed and the cleaned data is saved into the file.
