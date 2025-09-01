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
import numpy as np     
import matplotlib.pyplot as plt     
import seaborn as sns       
df=pd.read_csv("titanic_dataset.csv")   
df
```
![image](https://github.com/user-attachments/assets/ac126d0e-3187-4497-84fc-5601a2c40a93)
```
df.info()
```
![image](https://github.com/user-attachments/assets/82773ab4-6404-4a53-9632-ad3e0d2fa3b1)

```
df.shape
```
![image](https://github.com/user-attachments/assets/bb857e27-d9e6-4465-a06d-a17ebb5caaa2)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/fdd17cff-328e-4277-8ac9-da6e865ac122)


```
df.nunique()
```
![image](https://github.com/user-attachments/assets/80338951-a00a-4070-8495-e7a232a34f13)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/463b20ab-1ccb-45ad-b486-2e455c7a9324)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/b12f0c80-2ee7-42b9-8091-a31308387eec)

```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/df708221-0004-49b8-ba9e-1558f1bae3f7)

```
df
```
![image](https://github.com/user-attachments/assets/a40109c8-971a-40dc-aec5-db548fe31c8f)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/b21bbbeb-792b-4a98-b943-fb5ce74c2e94)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/33f15439-3d49-4ca6-924f-c0e8c0072598)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/f09af095-94d8-4a64-a87b-c54d47abc752)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```

![image](https://github.com/user-attachments/assets/b906db91-aa35-4b25-8c53-7df4a185a3b1)
```

df.boxplot(column="Age",by="Survived")
```

![image](https://github.com/user-attachments/assets/8353a8a5-b56f-491f-8963-8a9aa687464e)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

![image](https://github.com/user-attachments/assets/043a5b9b-4b05-41b8-bda7-b617955c2887)
```
sns.jointplot(x="Age",y="Fare",data=df)
```

![image](https://github.com/user-attachments/assets/862a5eea-3094-437c-b31e-6416ce01a67f)

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

![image](https://github.com/user-attachments/assets/f2070cca-8495-494c-bf3b-4174cee89ae5)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/user-attachments/assets/4a39f318-f955-4d94-858c-d3a32a5dacd3)
```
df_numeric = df.select_dtypes(include=['number'])
corr=df_numeric.corr()
sns.heatmap(corr,annot=True)
plt.show()
```

![image](https://github.com/user-attachments/assets/d1eadf67-650e-4f97-a460-ff879dce8ebd)
```
sns.pairplot(df)
```

![image](https://github.com/user-attachments/assets/4beba7fd-e03c-4069-88b1-c84abbef9d2a)


# RESULT
Thus the given program executed successfully.
