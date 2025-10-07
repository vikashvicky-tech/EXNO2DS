# EXNO2DS
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
 df=pd.read_csv('titanic_dataset.csv')
 print(df)
```
<img width="1045" height="780" alt="{9539A3C0-B6C2-4BBE-B903-9F000C9D49E8}" src="https://github.com/user-attachments/assets/b1bcf12a-9a77-4e6d-8df0-6bd73316f649" />

```
df.shape
```
<img width="192" height="35" alt="{E474F002-716C-46F2-B9D1-566AB7531258}" src="https://github.com/user-attachments/assets/0e6c184f-c1ab-438b-bafd-387a6cc0a68b" />

```
df.nunique()
```
<img width="357" height="291" alt="{0774801C-FDAB-4240-8BB4-E27D14E9D589}" src="https://github.com/user-attachments/assets/1b1baa0b-b5de-45ee-917c-1cec6e9caf94" />

```
df['Sex'].value_counts()
```
<img width="243" height="79" alt="image" src="https://github.com/user-attachments/assets/b3e9cc27-cb7e-405f-9307-e92f3da69fa6" />

```
df.set_index("PassengerId",inplace=True)
df
```
<img width="1329" height="472" alt="{AF60493E-DE00-4304-814E-D7E44A4B329F}" src="https://github.com/user-attachments/assets/c0826f75-161b-4342-84a7-ebfaccde84f7" />

```
df.Survived.unique()
```
<img width="334" height="32" alt="image" src="https://github.com/user-attachments/assets/427000f3-5388-4600-b4cb-81e918eeddd5" />

```
df.rename(columns={"Sex":"Gender"},inplace=True)
df
```
<img width="1253" height="473" alt="{B4F62900-48F1-45F4-9C96-A8165638D08D}" src="https://github.com/user-attachments/assets/b7b29f1b-c476-462a-bc3c-64882d1a1840" />

```
import seaborn as sns
sns.countplot(data=df)
```
<img width="885" height="563" alt="{AE6FD991-7384-419A-B1F2-0BD6DB3C4493}" src="https://github.com/user-attachments/assets/19642918-7b26-4d04-86b3-c4844cb7bb01" />

```
sns.countplot(x="Survived",hue="Gender",data=df)
```
<img width="830" height="601" alt="{A55DA061-CA04-49FC-9A88-21118937FB85}" src="https://github.com/user-attachments/assets/8e12a8a0-7d7b-4c65-8fe9-4988d72e5daf" />

```
sns.boxplot(data=df)
```
<img width="853" height="559" alt="{605D036D-6078-41FC-A8B9-8761E0EAA3B1}" src="https://github.com/user-attachments/assets/595c0cc2-e00e-47c2-a72b-17a1b1d03afc" />

```
df.boxplot(column="Survived",by="Gender")
```
<img width="933" height="630" alt="{F3BA1003-44F2-4184-91BD-B0348E9D73F2}" src="https://github.com/user-attachments/assets/6c1ffc26-4082-4442-bd61-736f8b9a0f0c" />

```
sns.scatterplot(data=df)
```
<img width="920" height="591" alt="{C23DF09F-D5E0-4D25-A9E1-440B77ED633E}" src="https://github.com/user-attachments/assets/331498b4-a39b-4c00-b7e6-28eb6ea370b6" />

```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
<img width="966" height="582" alt="{DE18F950-EAA1-4AD5-A06E-5E0E57CA2342}" src="https://github.com/user-attachments/assets/6b25728f-09d1-4b6d-b5d1-50670757cf22" />

```
sns.jointplot(x='Age',y='Fare',data=df)
```
<img width="881" height="785" alt="{9942A2CA-412B-41EC-BB71-E19C16A13303}" src="https://github.com/user-attachments/assets/d4f6f736-4efa-42bc-a5f4-6d7c09b3ed33" />

```
sns.jointplot(x='Age',y='Fare',data=df,kind="kde")
```
<img width="1028" height="779" alt="{B314F21D-EC96-41CD-8BCB-D6C5C3B79102}" src="https://github.com/user-attachments/assets/dc140620-5d11-4885-8985-1fcae5d46de4" />

```
 sns.jointplot(x='Age',y='Fare',data=df,kind="hist")
```
<img width="1008" height="777" alt="{C1BFB1AC-D31B-48B9-BF23-DF68512D5F59}" src="https://github.com/user-attachments/assets/909540d4-0687-4190-891d-cd43d3787bf0" />

```
sns.pairplot(data=df)
```
<img width="1414" height="775" alt="{E9A983A3-CE43-4A59-8B86-4A01817BB5FC}" src="https://github.com/user-attachments/assets/23b3e655-f188-47e7-a5c8-3cc0a7d4a6e1" />

```
 corr1=df.select_dtypes(include=['number']).corr()
 sns.heatmap(corr1, annot=True)
```
<img width="888" height="578" alt="{38EB1E6A-753E-4785-BC56-52FF6DCFDC95}" src="https://github.com/user-attachments/assets/901243f9-253f-456f-88f2-30113bb063cb" />

```
sns.catplot(x='Gender',col='Survived',data=df,kind='count',color='green')
```
<img width="1323" height="659" alt="{18199155-EAD3-4610-8293-DF27ABB63AF2}" src="https://github.com/user-attachments/assets/bff57b28-48df-4ba3-8db4-22071691b63f" />



# RESULT
Exploratory Data Analysis on the given data set was executed successfully

