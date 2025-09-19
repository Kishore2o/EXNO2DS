## Name : Kishore S
## Reg No : 212222240050
# EX NO : 2 DS
# AIM:
To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
# output 
<img width="1352" height="735" alt="image" src="https://github.com/user-attachments/assets/ea30ac40-4fef-4017-b2e5-f3ece4a68465" />

```
df.info()
```
# output
<img width="652" height="477" alt="image" src="https://github.com/user-attachments/assets/b3963ffa-d1f6-4228-8839-3355d589548e" />

```
df.describe()
```
# output
<img width="1033" height="412" alt="image" src="https://github.com/user-attachments/assets/fa3f41ac-ccf5-4df1-9990-2e7878c0514e" />

```
df.dtypes
```

# output
<img width="681" height="622" alt="image" src="https://github.com/user-attachments/assets/24bd803d-b90c-4652-93fb-ac5f69d889fc" />

```
df.shape
```
# output
<img width="577" height="92" alt="image" src="https://github.com/user-attachments/assets/89feb14f-6ac1-4bf0-a866-e748c0b0fd59" />


```
df.value_counts()
```
# output
<img width="1335" height="720" alt="image" src="https://github.com/user-attachments/assets/2b3c4b33-1ad3-4cea-8f3e-5e93c4610070" />

```
df['Age'].value_counts()
```
# output 
<img width="946" height="657" alt="image" src="https://github.com/user-attachments/assets/b78e654d-7d3b-40a7-b282-30b65236ca0c" />

```
df.set_index("PassengerId", inplace=True)
df
```
# output
<img width="1367" height="702" alt="image" src="https://github.com/user-attachments/assets/e0960a81-5f4f-4b2a-99c7-22cf3909f445" />

```
df.nunique()
```
# output
<img width="782" height="597" alt="image" src="https://github.com/user-attachments/assets/c7e0b586-59e4-49f1-902b-48ebf3e4d612" />

```
sns.countplot(data=df,x='Survived')
```
# output
<img width="958" height="637" alt="image" src="https://github.com/user-attachments/assets/ea9db84d-fd1b-41bd-bdbe-18553184ae7a" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
# output
<img width="1357" height="701" alt="image" src="https://github.com/user-attachments/assets/ca7446a4-a716-49df-8fb3-e02b5311af58" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
# output
<img width="990" height="701" alt="image" src="https://github.com/user-attachments/assets/268a1a8b-241c-4be9-8294-638d1a70d331" />

```
df.boxplot(column="Age",by="Survived")
```
# output
<img width="991" height="672" alt="image" src="https://github.com/user-attachments/assets/62671f7e-d5a9-4851-8e37-8ea345c87a1e" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
# output
<img width="956" height="643" alt="image" src="https://github.com/user-attachments/assets/ca4e6478-7727-4827-873a-82799cf4f217" />

```
fig, axl=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=axl,x='Pclass',y='Age',hue='Gender',data=df)
```
# output
<img width="1027" height="666" alt="image" src="https://github.com/user-attachments/assets/32204f98-3a49-4f07-8547-423252bf5448" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
# output
<img width="977" height="617" alt="image" src="https://github.com/user-attachments/assets/0535fb6d-a580-4914-bd0b-9c2201fe7587" />

```
import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)
```
# output
<img width="1397" height="707" alt="image" src="https://github.com/user-attachments/assets/7d380e81-9d80-4fab-83f3-6713c01e5118" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue='Pclass',kind="count")
```
# output
<img width="1397" height="705" alt="image" src="https://github.com/user-attachments/assets/a84cd5f5-a719-4571-aa0e-a1ae6c0ce8d7" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
# output
<img width="983" height="647" alt="image" src="https://github.com/user-attachments/assets/c68ab47f-a07d-4621-b45e-6e93638b5514" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```
# output
<img width="975" height="638" alt="image" src="https://github.com/user-attachments/assets/46b955e1-2951-4c76-aca2-9e8b66802d46" />


# RESULT
Thus the program was executed successfully
