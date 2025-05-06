# EXNO2DS

Name: Ravikrishnamoorthy D

Register No: 212224040271

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
```
```
dt = pd.read_csv("/content/titanic_dataset.csv")
dt
```
![image](https://github.com/user-attachments/assets/10166bb3-8bf4-4c24-a746-a6b5bbaa472e)

```
dt.info()
```
![image](https://github.com/user-attachments/assets/c64507c4-274a-48a2-83f8-6f0f2d40a8f1)

```
dt.shape
```
![image](https://github.com/user-attachments/assets/561c2c34-c52f-4654-b160-ac02a70a3f8e)

```
dt.set_index("PassengerId",inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/d89ccfba-5d73-475c-9913-9e98595e8fb1)

```
dt.describe()
```
![image](https://github.com/user-attachments/assets/6be4dea9-b1f2-45f3-83db-70d19d880897)

```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/843ca808-a249-4d98-8d7f-be7773843a57)

```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/bfd12044-e96c-4fea-a3f6-c9422976e09f)

```
per = (dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/08161b6c-af51-45a4-8b85-19d8577ceb99)

```
sns.countplot(data = dt, x = "Survived", hue = "Survived")
```
![image](https://github.com/user-attachments/assets/cd783b68-467b-428d-87b5-a23952b8638c)

```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/39e5a118-d7d1-4257-9f85-19ea33843a08)

```
dt.rename(columns = {'Sex' : 'Gender'}, inplace = True)
dt
```
![image](https://github.com/user-attachments/assets/bbab270e-83fe-45e0-b15d-94ee580fc94c)

```
sns.catplot(x = "Gender", hue = "Gender", col = "Survived", kind = "count", data=dt,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/90a38cf6-c569-4ec6-9583-65020746d503)

```
sns.catplot(x = "Survived", hue = "Gender", data=dt,kind = "count")
```
![image](https://github.com/user-attachments/assets/029c4425-93ad-4f9c-9dcc-3119db560749)

```
dt.boxplot(column = "Age", by="Survived")
```
![image](https://github.com/user-attachments/assets/a7ce6bc6-fe1b-4a71-bfdb-9dd159f848de)

```
sns.scatterplot(x = dt["Age"], y =dt["Fare"])
```
![image](https://github.com/user-attachments/assets/74e0fee0-f903-4863-9e30-b7ed4b085785)

```
sns.jointplot(x = 'Age', y = 'Fare', data = dt)
```
![image](https://github.com/user-attachments/assets/b3e318ef-02d9-4a6a-9392-dd38a47daf2e)

```
fig, ax1 = plt.subplots(figsize = (8,5))
pt = sns.boxplot(ax = ax1, x = 'Pclass', y = 'Age', hue = 'Gender', data = dt)
```
![image](https://github.com/user-attachments/assets/22bb2e9f-50a6-4325-ad56-73033b0b131e)

```
sns.catplot(data = dt, col = "Survived", x = 'Gender', hue = "Pclass", kind = 'count')
```
![image](https://github.com/user-attachments/assets/88cbeb24-5941-459b-abf7-8d7af141e85c)

```
data = dt[['Survived','Pclass','Age','SibSp','Parch','Fare']]
correlation = data.corr()
sns.heatmap(correlation,annot=True)
```
![image](https://github.com/user-attachments/assets/5da7cf88-b231-4453-8135-81b837c1de1e)

```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/12f9f905-2926-41ae-a8ed-dd3660dd1d0d)

# RESULT

Thus, the Performed Exploratory Data Analysis on the given data set executed successfully.
