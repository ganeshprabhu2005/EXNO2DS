# EXNO2DS
## NAME: VIJAYASHREE B
## REG: 212223040238
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
```py
import pandas as pd
import numpy as np
import seaborn as sns
df = pd.read_csv('/content/titanic_dataset.csv')
df
```
<img width="1300" height="476" alt="image" src="https://github.com/user-attachments/assets/730ccb65-e54d-4ce9-a6a4-802336515d34" />


```py
df.info()
```
<img width="380" height="380" alt="image" src="https://github.com/user-attachments/assets/f7f43c75-01d1-41e0-8116-3b00ca8815eb" />

```py
df.describe()
```
<img width="776" height="326" alt="image" src="https://github.com/user-attachments/assets/6ea55f99-bdbf-4695-a905-0c46b46e8702" />


```py
df.dtypes
```
<img width="234" height="509" alt="image" src="https://github.com/user-attachments/assets/1d376e3c-4f90-4c29-8a2b-edbf953018f3" />

```py
df.shape
```
<img width="93" height="40" alt="image" src="https://github.com/user-attachments/assets/b71ec996-9364-48a0-b5fa-06ffd6e46f9e" />


```py
df.value_counts()
```
<img width="190" height="541" alt="image" src="https://github.com/user-attachments/assets/c76236b3-aac8-4485-95c7-ce9d578a98d7" />


```py
df['Age'].value_counts()
```
<img width="1355" height="535" alt="image" src="https://github.com/user-attachments/assets/f4825b2f-59f8-4667-b96f-b228acad52de" />


```py
df.set_index("PassengerId",inplace=True)
df
```
<img width="1250" height="509" alt="image" src="https://github.com/user-attachments/assets/dd39e82c-1ab4-40ff-90ff-a888865a2427" />

```py
df.nunique()
```
<img width="165" height="475" alt="image" src="https://github.com/user-attachments/assets/bc6e9f49-7695-401a-9671-4ed42d728384" />


```py
sns.countplot(data=df,x='Age')
```
<img width="678" height="526" alt="image" src="https://github.com/user-attachments/assets/cd95a2a1-2048-46d3-97e9-f323e49eb38b" />

```py
df.rename(columns = {'Sex' : 'Gender'},inplace = True)
df
```

<img width="1261" height="499" alt="image" src="https://github.com/user-attachments/assets/bf4c3236-e858-48ca-a9f6-9edac1679417" />

```py
sns.catplot(x="Gender",col="Survived",kind = "count",data=df,height=5,aspect=.7)
```
<img width="810" height="587" alt="image" src="https://github.com/user-attachments/assets/e71b4059-8f5c-497d-85cc-216f0b9c901d" />

```py
df.boxplot(column = "Age",by="Survived")
```

<img width="657" height="552" alt="image" src="https://github.com/user-attachments/assets/ab7068bf-f1d8-47cd-9967-cf2f47e1691c" />


```py
sns.scatterplot(x=df['Age'],y=df['Fare'])
```

<img width="649" height="511" alt="image" src="https://github.com/user-attachments/assets/b3680a39-fd80-44b0-993a-5a322c91b3e0" />

```py
plt = sns.boxplot(x='Pclass',y='Age',hue = 'Gender',data=df)
```

<img width="640" height="496" alt="image" src="https://github.com/user-attachments/assets/93d8cb55-059d-415d-885d-63e5e2db3904" />


```py
sns.catplot(x='Pclass',y='Age',hue='Gender',col='Survived',kind='box',data =df)
```

<img width="1256" height="582" alt="image" src="https://github.com/user-attachments/assets/f8d014e1-8f72-43fa-8b48-c362bd35ae0a" />

```py
corr = df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```

<img width="606" height="492" alt="image" src="https://github.com/user-attachments/assets/c1a817be-1f99-4cf9-9b9a-6539a4918f38" />


## RESULT
Hence,exploratory data analysis on the given data set has been executed successfully.

        
