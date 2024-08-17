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

## Data Cleaning:
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/user-attachments/assets/9788712e-08dd-411c-970e-78accf0c8de5)

```
df.head()
```
![image](https://github.com/user-attachments/assets/728e7e11-e223-466e-8c9f-5ddd79e8010b)

```
df.tail(4)
```
![image](https://github.com/user-attachments/assets/f8f38a32-81f2-4245-8503-760bdc543349)

```
df.dropna(axis=0)
```
![image](https://github.com/user-attachments/assets/606e1b6e-a352-4206-8b88-38ad6379df61)

```
df.dropna(axis=1)
```
![image](https://github.com/user-attachments/assets/fc61da62-3fe5-427d-9067-a854d05a714d)

```
df.fillna(0)
```
![image](https://github.com/user-attachments/assets/e759dfe0-0cb7-4618-8372-37d4ffc570af)

```
print(df.shape)
```
![image](https://github.com/user-attachments/assets/a8f6898a-49f2-4d34-91f7-c1af1e7c524f)

```
df.describe()
```
![image](https://github.com/user-attachments/assets/800fdaa0-6f71-458a-a736-db1c708a7c36)

```
df.isnull()
```
![image](https://github.com/user-attachments/assets/3beca29a-7e2b-4dc9-9e4e-3af5a0c0f9b5)


 ## IQR(Inter Quartile Range


```
import pandas as pd
import seaborn as sns
ir=pd.read_csv('/iris.csv')
ir
```
![image](https://github.com/user-attachments/assets/27df9793-66fd-41f1-8447-c259380f1b64)

```
ir.describe()
```
![image](https://github.com/user-attachments/assets/4b0f12ed-512d-43fd-9430-12cb8087acf1)

```
sns.boxplot(x='sepal_width',data=ir)
```
![image](https://github.com/user-attachments/assets/3d552bf0-0072-461b-8699-9715d450550c)

```
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```
![image](https://github.com/user-attachments/assets/d306ab06-eaaa-437a-9078-a5a3ee85f0e1)

```
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
```
![image](https://github.com/user-attachments/assets/f60b9291-e4d9-4516-b293-b12b4e7d76ca)

```
sns.boxplot(x='sepal_width',data=delid)
```
![image](https://github.com/user-attachments/assets/8f7bd5cf-2b02-4421-ba80-3e499cb66ab4)

 ## Z-Score:
 
```
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("/heights.csv")
dataset
```
![image](https://github.com/user-attachments/assets/39634bfe-6b09-4a4e-a283-42620a09ebe2)

```
df = pd.read_csv("/heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr
```
![image](https://github.com/user-attachments/assets/57942a64-e4a6-4863-a8f9-8b6236d32685)

```
low = q1 - 1.5*iqr
low
```
![image](https://github.com/user-attachments/assets/6c21ef8f-4f2b-40a4-91ab-4bc670a13815)

```
high = q3 + 1.5*iqr
high
```
![image](https://github.com/user-attachments/assets/44b2d42d-7eee-4205-81da-7411c8a62b98)

```
df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1
```
![image](https://github.com/user-attachments/assets/71163a8f-ed64-4888-bc37-c7d979410fd2)

```
z = np.abs(stats.zscore(df['height']))
z
```
![image](https://github.com/user-attachments/assets/bdac0db1-7b66-4b02-b0b2-c33bcb851925)

```
df1 = df[z<3]
df1
```
![image](https://github.com/user-attachments/assets/9321744a-a2c0-4605-be62-a8adef168ac3)





















## Result
          <<include your Result here>>
