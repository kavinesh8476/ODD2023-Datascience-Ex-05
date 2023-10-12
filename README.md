# Ex:05 Feature Generation
## AIM
To read the given data and perform  Feature Encoding & Scaling process and save the data to a file.

## Explanation

Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

## ALGORITHM

STEP 1

Read the given Data.

STEP 2

Clean the Data Set using Data Cleaning Process.

STEP 3

Apply Feature Generation techniques to all the feature of the data set.

STEP 4

Save the data to the file.
## PROGRAM
```
import pandas as pd
df=pd.read_csv("Encoding Data.csv")
df

from sklearn.preprocessing import LabelEncoder ,OrdinalEncoder
pm=['Hot','Warm','Cold']
e1=OrdinalEncoder(categories=[pm ])
e1.fit_transform(df[["ord_2"]])
df['bo2']=e1.fit_transform(df[["ord_2"]])
df
le=LabelEncoder()
dfc=df.copy()
dfc['ord_2']=le.fit_transform(dfc['ord_2'])
dfc

from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
df2=df.copy()
enc=pd.DataFrame(ohe.fit_transform(df2[['nom_0']]))
df2=pd.concat([df2,enc],axis=1)
df2

from category_encoders import BinaryEncoder
df=pd.read_csv("data (1).csv")
be=BinaryEncoder()
dfb=df.copy()
nd=be.fit_transform(df['Ord_2'])
dfb=pd.concat([df,nd],axis=1)
dfb

from category_encoders import TargetEncoder
te=TargetEncoder()
cc=df.copy()
new=te.fit_transform(X=cc["City"],y=cc["Target"])
cc=pd.concat([cc,new],axis=1)
cc





```
