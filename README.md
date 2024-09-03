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

## CODING AND OUTPUT:
```
import pandas as pd
df=pd.read_csv('/content/titanic_dataset.csv')
df
```
![image](https://github.com/user-attachments/assets/b9411f27-2e54-4cb9-97dc-14e6c4df49b5)

```
df.info()
```
![image](https://github.com/user-attachments/assets/0a2f7fac-0804-4098-8346-2a8615edc94a)

```
df.shape()
```
![image](https://github.com/user-attachments/assets/99d2038a-da4c-48ab-9be5-b2c1bd7add67)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/2d8cfd76-bd33-43fd-9c98-bd5f3b3096fd)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/21ace095-dc9a-44fa-a199-4dc393e22dfe)

```
per = (df["Survived"].value_counts() / df.shape[0] * 100).round(2)
per
```
![image](https://github.com/user-attachments/assets/e320e38f-d01b-4c40-92a5-05097f9bc9b5)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/cfbddd57-b940-4ac2-bd17-f83bcc05abba)

```
import seaborn as sns
sns.countplot(data=df,x='Survived')
```
![image](https://github.com/user-attachments/assets/c3a6375f-934d-46be-9762-d0ffedfb66e4)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/de0b7419-8c95-4926-ac7d-8cabdc1c1cbf)

```
df.rename(columns={"Sex":"Gender"},inplace=True)
df.head()
```
![image](https://github.com/user-attachments/assets/afdf6fb8-0bae-4bc9-a682-b623b8e3fe67)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/6dd6a74a-9a1f-4954-883a-75e1f4a9ed91)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/2f340beb-f23a-4cc2-ba5e-3252dab21f08)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/73ae7b47-8837-4e53-947f-4c8a0015232e)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/f1769657-0baf-43cb-b3d0-c3fdf6c240b7)

```
sns.jointplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/ffae6165-6cbd-4350-94bb-84d27a5d5489)

```
import matplotlib.pyplot as plt  # Import the pyplot module and alias it as 'plt'

fig, ax1 = plt.subplots(figsize=(8, 5))
sns.boxplot(x="Pclass", y="Age", hue="Gender", data=df, ax=ax1)
```
![image](https://github.com/user-attachments/assets/90642647-6811-4e97-8649-629c16c41201)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/9b78a4e6-72f4-45fc-b0cb-5cb0dd1d6507)

```
numeric_dt = df.select_dtypes(include=['number'])
corr = numeric_dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/5af8a8cf-2b90-4fc4-96ce-5ef849382e9a)

```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/15fa219c-3369-4364-96f9-d6ce38ad5cf7)


# RESULT:
Thus the code has been executed successfully.

