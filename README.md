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
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df = pd.read_csv('/content/titanic_dataset.csv')
print(df.head())
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/986e4a63-3918-412a-b0a8-59924206b0d1)

```
df.info()
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/6e7bca94-0ed2-4fd9-9b6a-834a363b43e7)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/8143f8bc-7634-4f26-ad57-a069be2fdb39)

```
df.nunique()
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/d7b9f9d5-959b-4a54-b0b1-aec95fd7a39d)

```
df.shape
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/56c1bddd-ff9a-423d-a53c-250a70e02378)

```
df["Survived"].value_counts()
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/4f296ce9-fb76-42b0-bcfe-1308a1f65582)

```
person=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
person
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/ddc608c8-8c83-456c-8455-7e3c0915b1ba)

```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/84b6b69a-4b25-4e59-8440-15ea60e8d86d)

```
df.Pclass.unique()
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/da4ebb15-1b61-4928-aadd-15f4d7205da6)

```
df.rename(columns ={'Sex': 'Gender'}, inplace = True)
df
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/fb1e07bb-2b87-4387-98f4-f4234f5c819a)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=0.7,color="Lightgreen")
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/5a6a87e7-55d6-4a1e-9e82-b3ee0496eb60)

```
sns. catplot(x='Survived', hue="Gender",data=df, kind = "count" )
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/fa79ad1b-4f59-489b-b523-4812cf8d2861)

```
df.boxplot(column="Age", by="Survived")
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/7afb11d4-e6ea-402a-ac56-9f513cd35984)

```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/7cfee42d-1ea8-4e7a-9250-9f8ffa01a7ba)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/8f4672ba-f7ab-4247-9d7a-135784a8872b)

```
fig, ax1= plt.subplots(figsize=(8,5))
pt=sns.boxplot (ax=ax1,x='Pclass',y='Age' ,hue= 'Gender', data=df)
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/ca409d93-5000-4dfa-9896-26e417c20c0c)

```
sns. catplot(data=df, col = "Survived",x = "Gender", hue="Pclass", kind = "count" )
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/f8c03429-990f-43ee-8a45-8dfc08616ac2)

```
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/d6b3bb02-6806-4f93-aba7-7e30347f84dc)

```
sns.pairplot(df)
```
![image](https://github.com/Sanjay22006832/EXNO2DS/assets/119830477/5fb91471-9196-4525-baa6-6181e8f0ba83)

# RESULT:
  Thus  Exploratory Data Analysis on the given data set executed successfully.
