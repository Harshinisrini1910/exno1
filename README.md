# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
data = pd.read_csv("/content/SAMPLEIDS.csv")
data.head()

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/4cf87d59-d03e-416b-b2b5-6762eaeb3b04)

df.head(10)

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/19b05941-e167-4f5c-9f74-39dd95905a14)

df.tail(10)

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/daee1ffa-1b04-4c1b-94b2-c113bfa0a411)

df.info()

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/8499cdb8-4b29-4859-9b4f-bf8c73e3fdb8)

df.describe()

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/42ecf78f-016f-4a74-ac02-bbec9a1abcf1)

df.shape

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/fd0a598c-3d7b-4a9f-827d-30e766069149)

df.isnull().sum()

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/e0521987-3a12-4812-9464-3280b1b96a2f)

df.nunique()

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/9f659dcb-f822-41c5-9628-780afe27de72)

df['GENDER'].value_counts()

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/27bd885f-ec49-4ac4-bc39-8f491350a7bc)

mn=df.TOTAL.mean()
mn

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/babd9d34-4c04-4dc5-a8b9-a08c18619b7d)

df.TOTAL.fillna(mn,inplace=True)
df.M4.fillna(0)

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/ab563853-c829-4a2f-8a27-86953082f875)

min=df.M4.min()
min

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/0a1f3078-ba4a-4d5a-a6bc-00a11537d596)

df.M4.fillna(min,inplace=True)
df

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/c2955511-ca0f-4a60-819d-a05b2dd54ae4)

df.isnull()

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/7ebb5fbc-aa3f-4735-bac8-a7f81634a96f)

import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/46821f9c-0d14-43a4-9c1a-f2f8d820cb4e)

sns.boxplot(data=af)

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/e1e8fb5f-222d-453a-b5a4-3e6e92c9cd5f)

sns.scatterplot(data=af)

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/fb14dc1f-4deb-4bfc-9fd0-8488547318f4)

q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
iqr

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/0f12ab01-5dee-42d7-8310-7c87e9936dee)

low=q1-1.5*iqr
low

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/db56274f-2026-49ca-91e5-de8c2ae9feac)

high=q3+1.5*iqr
high

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/d2dd0113-8646-4bdf-8fbc-6c10abfcf7f4)

af=af[((af>=low)&(af<=high))]
af

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/8c2cbbac-4c6a-4294-893a-716ea9596bfb)

af.dropna()

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/44afdc08-d603-48db-8498-36302ca39b8c)

sns.boxplot(data=af)

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/7f7df35e-d35b-42c0-b395-fb579213df22)

data=[1,12,15,18,21,24,27,20,30,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,158]
df=pd.DataFrame(data)
df

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/6683d5df-83be-44f9-9039-c2873ca43d2f)

import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z

![image](https://github.com/Harshinisrini1910/exno1/assets/161415847/fd8cf8a2-cf2b-4df2-a179-2bc89f2f81f7)

# Result
 Thus we read the given data and perform data cleaning and save the cleaned data to a file.

         
