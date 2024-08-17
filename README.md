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










## Result
          <<include your Result here>>
