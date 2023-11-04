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
DEVELOPED BY:KAVINESH M
REGISTER NO:212222230064
```
```python
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

import pandas as pd
df=pd.read_csv("bmi.csv")
df

import scipy as stats
import numpy as np

df.head()

max_vals=np.max(np.abs(df[['Height','Weight']]))
max_vals

min_vals=np.min(np.abs(df[['Height','Weight']]))
min_vals
df1=df.copy()

from sklearn.preprocessing import StandardScaler
ss=StandardScaler()
df1[['Height','Weight']]=ss.fit_transform(df1[['Height','Weight']])
df1.head(10)

from sklearn.preprocessing import MinMaxScaler

df2=df.copy()

scaler=MinMaxScaler()
df2[['Height','Weight']]=scaler.fit_transform (df2[['Height','Weight']])
df2.head(10)

from sklearn.preprocessing import Normalizer
df3=df.copy()

scaler=Normalizer()
df3[['Height','Weight']]=scaler.fit_transform(df3[['Height','Weight']])
df3

df4=df.copy()
from sklearn.preprocessing import MaxAbsScaler
scaler=MaxAbsScaler()

df4[['Height','Weight']]=scaler.fit_transform(df4[['Height','Weight']])
df4.head(10)

df5=df.copy()
from sklearn.preprocessing import RobustScaler
scaler=RobustScaler()

df5[['Height','Weight']]=scaler.fit_transform(df5[['Height','Weight']])
df5.head()
```
## OUTPUT
![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/86d6c7e0-4ccb-444e-be21-007d564961eb)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/a211ea1e-7038-4cd4-8a27-20d93a4c5df5)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/ceac1dd8-6c23-4830-bd95-a678b62da9ff)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/f6118f33-5421-4919-827a-b71863175989)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/03dbc217-e5e2-4f56-8348-0ecc9d256e33)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/558919ec-29d5-49fa-a271-153e833bd4fd)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/c9c8de9d-f5fb-444a-916a-ff4a06a9177a)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/f7f98c23-fe3d-429a-990d-dde89ad5f94a)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/3b72a6b8-a2bb-4f48-b781-583a21944aae)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/bd3b50d7-646a-4e55-ba01-7c8df83f2c65)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/7b70713e-537f-4228-9711-ccca210124fb)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/850891f4-dca7-45d1-9715-69cbf0054688)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/b4783f73-d90c-484d-80f9-daca467615ee)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/1ec063c6-7b05-4d50-a922-1a054049741b)

![image](https://github.com/kavinesh8476/ODD2023-Datascience-Ex-05/assets/118466561/467a6e3c-213e-48e6-8653-8d0d7dafba90)

## RESULT
The Feature Generation process was performed and saved the data to a file.

