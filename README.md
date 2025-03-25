# EX NO:2
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
 import pandas as pd
 import numpy as np
 import matplotlib.pyplot as plt
 import seaborn as sns
 df=pd.read_csv("titanic_dataset.csv")
 df
 ![Screenshot 2025-03-25 140738](https://github.com/user-attachments/assets/ebb5d517-a7cd-4a0e-b527-51ab84cb5556)
 
 df.info()
![Screenshot 2025-03-25 140749](https://github.com/user-attachments/assets/0a1a765a-442c-4a4b-a0d3-6496df2ec8a4)

 df.shape
![Screenshot 2025-03-25 140759](https://github.com/user-attachments/assets/85a272ae-6ecc-4fb3-a695-5f3cf31ef876)

 df.set_index("PassengerId",inplace=True)
 df.describe()
![Screenshot 2025-03-25 140810](https://github.com/user-attachments/assets/0ae2e2d9-c8bd-4559-a6c8-7ec353b726ee)

df.nunique()
![Screenshot 2025-03-25 140829](https://github.com/user-attachments/assets/c47b837a-31cb-4bc7-9166-c1ac11af3614)

 df["Survived"].value_counts()
 ![Screenshot 2025-03-25 140840](https://github.com/user-attachments/assets/5a2c5f87-60a1-4203-a40d-71c5f99010c8)

  sns.countplot(data=df,x="Survived")
![Screenshot 2025-03-25 140849](https://github.com/user-attachments/assets/221caf0d-9a85-4c64-9d23-c1ad23055589)

 sns.countplot(data=df,x="Survived")
![Screenshot 2025-03-25 140902](https://github.com/user-attachments/assets/0b47dc0b-2a07-48f9-9128-2e28d5e64434)

df
![Screenshot 2025-03-25 140929](https://github.com/user-attachments/assets/f11b6e21-544a-4254-83f4-6c0a72124298)

 df.Pclass.unique()
![Screenshot 2025-03-25 140937](https://github.com/user-attachments/assets/6a5eb1e4-c129-4063-bd8f-f74b8087a51d)

df.rename(columns={'Sex':'Gender'},inplace=True)
df
![Screenshot 2025-03-25 140951](https://github.com/user-attachments/assets/36e9bc05-4a5c-491b-bd1a-8a69224c5848)

 sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
![Screenshot 2025-03-25 141002](https://github.com/user-attachments/assets/570e5eea-1ad6-416d-a471-15cf0ce35efd)

 sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
![Screenshot 2025-03-25 141012](https://github.com/user-attachments/assets/320ba604-7ada-4b65-8585-950c2ab8a428)

 df.boxplot(column="Age",by="Survived")
 ![Screenshot 2025-03-25 141021](https://github.com/user-attachments/assets/3486e889-581b-41c7-ad4b-12521515463d)


 sns.scatterplot(x=df["Age"],y=df["Fare"])
 
 ![Screenshot 2025-03-25 141028](https://github.com/user-attachments/assets/1102dba5-4fbc-4ca6-b401-355f73b71fd6)


sns.jointplot(x="Age",y="Fare",data=df)
![Uploading Screenshot 2025-03-25 142745.png…]()


fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)

![Screenshot 2025-03-25 142755](https://github.com/user-attachments/assets/9f83fc9d-fdaf-4ee3-b7cb-d302f8b676b2)

 sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
 
![Screenshot 2025-03-25 142808](https://github.com/user-attachments/assets/298b9539-4032-4d9e-9e45-40036ea88642)

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
numerical_df = df.select_dtypes(include=np.number)
corr = numerical_df.corr()
sns.heatmap(corr, annot=True)

![Screenshot 2025-03-25 142816](https://github.com/user-attachments/assets/1b313fd7-de5b-486a-94aa-d20636dd0046)

 sns.pairplot(df)
 



















 







 
 

              

# RESULT
         We have performed Exploratory Data Analysis on the given data set successfully
