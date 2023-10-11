# ODD2023-Datascience-Ex-04
# AIM:
To perform Multivariate EDA on the given data set.

# EXPLANATION:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
# ALGORITHM:

## STEP 1:

Import the built libraries required to perform EDA and outlier removal.
## STEP 2:

Read the given csv file
## STEP 3:

Convert the file into a dataframe and get information of the data.
## STEP 4:

Return the objects containing counts of unique values using (value_counts()).
## STEP 5:

Plot the counts in the form of Histogram or Bar Graph.
## STEP 6:

Use seaborn the bar graph comparison of data can be viewed.
## STEP 7:

Find the pairwise correlation of all columns in the dataframe.corr()
## STEP 8:

Save the final data set into the file
# PROGRAM:
```

# SuperStore.csv file:

import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/SuperStore (1).csv")
df=pd.DataFrame(data)
df.head()
df.info()
df.describe()
df.isnull().sum()
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()

sns.scatterplot(x=df['Region'],y=df['Sales'])

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=states.index,y="Sales",data=states)

states=df.loc[:,["Ship Mode","Row ID"]]
states=states.groupby(by=["Ship Mode"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SHIP MODE")
plt.ylabel=("ROW ID")
plt.show()

sns.boxplot(x=df['Ship Date'],y=df['Sales'])
sns.displot(df, x="Region", hue="Category")
df.corr()
sns.heatmap(df.corr(),annot=True)

# diabetes.csv file:

import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/diabetes (1).csv")
df
df.describe()
df.info
df.isnull().sum()

sns.scatterplot(x=df['Glucose'],y=df['BloodPressure'])

sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])

Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)

Age=df.loc[:,["BloodPressure","Glucose"]]
Age=Age.groupby(by=["BloodPressure"]).sum().sort_values(by="Glucose")
sns.barplot(x=Age.index,y="Glucose",data=Age)
plt.xticks(rotation = 90)
plt.xlabel=("BloodPressure")
plt.ylabel=("Glucose")
plt.show()

sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])

sns.displot(df, x="Glucose", hue="Outcome")

df.corr()

sns.heatmap(df.corr(),annot=True)
```
# OUTPUT:
## SUPERSTORE:
## DATA FRAME OF SUPERSTORE:
![274188403-bb2f1494-3624-41dc-bd38-5d647e469c06](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/8555f7a7-1b02-4a38-8168-843f1c496842)

## Data information:
![274188786-5a220e39-6f0a-4b6d-869d-ffcf189fad24](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/945488f2-6ced-4f22-a454-54ec7295bbca)

## Data describing:
![274192959-b284d438-572d-4346-bc9d-c26ef54d8058](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/cd761777-612e-47ae-849b-16e8fb8f20bb)

## Sum of null values:
![274193029-a48ae8fa-3c1c-43ce-a513-806ed7b31b5d](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/b9f88708-0dd1-436f-b8e5-cb03baa06086)

## After removing null values:
![274193100-dac01647-9ef6-4f43-a55c-9a2fcc205c29](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/09b52cd4-026f-4b67-bd32-6835d6761044)

## Scatter plot:
![274193100-dac01647-9ef6-4f43-a55c-9a2fcc205c29](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/a17454c7-448f-479e-a04d-682cee1771c3)

## Bar plot:
![274193244-a45d5223-b945-4202-b506-986437757ba0](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/bd54994e-ed62-458f-ba41-ded3dc2ccc9e)
![274193270-d8033d46-60d3-4b99-8971-52dd0b669c1f](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/66f4f5e9-fe47-4881-b6da-c5b7c4728268)

## Box plot:
![274193306-422b53c0-08f0-4720-98d4-5c1773e552fa](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/406cb3b3-6766-4b1b-9007-d6ebf3c0805f)

## Dist plot:
![274193361-69f3c8ec-83db-4a92-89f7-2d05c405e68f](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/744d553c-7c7d-43e0-8b19-aed6c9be60dc)

## Correlation coefficient interpretation:
![274193395-14f7335d-06bc-4674-b563-72a3553f445a](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/a8ee1181-e469-48e4-bb60-066753aa88b6)

## Heat map:
![274193510-ebdb8426-8858-4158-9321-c2d1549b7d14](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/0edd3ec8-b215-4faa-9e62-35abae05cac1)

## DIABETES
## DATA FRAME FOR DIABETES:
![274193621-3e9571ab-b205-4569-a67f-e08f4a9a3ae3](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/70ae10a9-1a5d-478c-b3e1-d016a73eb827)

## Data information:
![274193648-b1388c3e-4a1b-4daa-a8b2-667fff07a620](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/d3be9e03-a1bc-4531-8e47-3cd3cdb39dac)

## Data describing:
![274193670-f9e9f6cb-ebf8-4664-8417-af575abe47f0](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/900756ec-e2cd-496d-ba4c-10152153f3cb)

## Sum of null values:
![274193792-3f17eb04-3503-4e8b-945c-dd126bcfe267](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/737d5a4c-74d5-491c-a5e3-de9d80b6d1c1)

## Scatter plot:
![274193828-e3515497-52df-419b-808f-52b574d8dc7b](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/49104079-ef7c-4271-b6ee-22f5d8130fa4)
![274193875-443fedbb-6256-4272-8271-2ec2a5017545](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/24614851-3a46-401f-b16a-e78d72616985)

## Bar plot:
![274193922-548a0c23-90f5-4711-a9e1-2133d87de497](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/a399d576-9758-4dcb-a6c7-fb84a3e9a4b7)
![274193982-60e286da-3a66-48a8-a0ff-b5b38c49282c](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/abaea62f-1f32-4513-8743-645b9bdbc131)

## Box plot:
![274194030-2e42e214-7ed5-4096-b7d8-9405ff76333e](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/a0f796d7-383a-45d2-a600-42192b7a2a4c)

## Dist plot:
![274194062-c26eec48-6d62-419b-9fe1-4fe33c976092](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/f3c06cdb-8198-4d34-ae47-4d6241d807a5)
## Corelation coefficient interpretation:
![274194127-1d18fc4c-00ca-47c5-8e24-dd84a6d009c0](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/dd49e1ad-7d09-4728-b32b-60f02c23823f)

## Heat map:
![274194173-6eab2754-2c5f-46af-8b00-e1b0ccf0f366](https://github.com/vishnupriyaramesh17/ODD2023-Datascience-Ex-04/assets/119393589/fc219ae6-85a8-4b93-b137-1242cc145e33)

# RESULT:
Thus we have read the given data and performed the multivariate analysis with different types of plots.








