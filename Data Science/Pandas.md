- data manipulation library (data analysis and data cleaning)
- provided two data structures 
	- Series- 1d array like obj (can hold any data type)
	- Data Frame - 2d, size mutable , heterogeneous tabular ds, with axes (rows and columns)
```python
pip install pandas

import pandas as pd
  
data =[1,2,3,4,5]
series= pd.Series(data)
print(series)             # has index
print(type(series))       # pandas.core.series.Series

# series from dict
data={'a':1,'b':2,'c':3}
series= pd.Series(data)     # key becomes index
print(series)

#set custom indices
data1=[18,92,53,84,75]
indices= [10,20,30,40,50]
series=pd.Series(data1, index=indices)
print(series)
```
 - Data Frame- similar to table 
 ```python
# create a data frame from dict of list
data={
    'Name':['Krish','John','Jack'],
    'Age':[25,30,45],
    'City':['Bangalore','New York','Florida']
}
df= pd.DataFrame(data)
print(df)
df
type(df)

import numpy as np
np.array(df)             # can show the df as array too

# create a df from list of dict
data=[
    {'Name':'Krish','Age':32,'City':'Bangalore'},
    {'Name':'John','Age':34,'City':'Bangalore'},
    {'Name':'Bappy','Age':32,'City':'Bangalore'},
    {'Name':'JAck','Age':32,'City':'Bangalore'}
]
df = pd.DataFrame(data)
print(df)
df.loc[0]        # 0th row   # loc for row
  
# accessing
df.iloc[0]       # for column
df['Name']       # also for column
type(df['Name'])  # it's Series (cuz single array(colums))

## specific element
df.iloc[0, 0]
df.iat[1,2]
print(df.at[1,'Age'])

# manipulate like arrays
df['Age']+=1

# add and remove a column
df['Salary']= [200,500,600,200]
df

df.drop(0)                 # drops 0th row,  (axis= 0 by default)
df.drop(0, inplace=True)   # permanent drop

df.drop('Salary', axis=1)     # to drop a column
df.drop('Salary', axis=1, inplace=True)  #to drop a column permanently
# df.drop('Salary')        # gives error cuz axis=0 by default and no row is named 'Salary'
 ```
 -   Four ways to access a single cell in pandas:
1. **`df.loc[row_label, column_label]`** → uses labels (names).
2. **`df.iloc[row_index, column_index]`** → uses numbers (positions).
3. **`df.at[row_label, column_label]`** → same as `loc`, but **faster for one cell**.
4. **`df.iat[row_index, column_index]`** → same as `iloc`, but **faster for one cell**.
## loc Vs Iloc

### 1. `.loc` → **Label-based** (use names)

Think of it as **look up by label (word, name, or index number written in the table)**.

```python
df.loc[0, "name"]   # row with label 0, column "name" # Output: 'Alice' 
df.loc[1, "age"]    # row with label 1, column "age" # Output: 30
```
### 2. `.iloc` → **Index-based** (use positions)

Think of it as **look up by position number** (like list indexing).

```python
df.iloc[0, 0]   # first row, first column # Output: 'Alice' 
df.iloc[1, 1]   # second row, second column # Output: 30
```
 
 -  Read a csv file
 ```python
df= pd.read_csv('sales.csv')
df.head(5)                        # gives top 5 records
 ```
- some other properties
```python
df.describe       # describe the df(count, mean, std, min ,max, quartiles)
df.dtypes        # describe he data types of each column (int64, float64, obj , bool ,datatime64)
df.groupby('Category')['Value'].mean()
```

# Data Manipulation
 ```python
import pandas as pd
df=pd.read_csv('Iris_missingdata.csv')
df.head()  
df.tail()   # last 5

df.dtypes
df.describe()      # stats
df.isnull
df.isnull()        # both r different  # True means missing value

# Handling missing values
df.isnull().any(axis=1)     # if null is present in any column
df.isnull().sum()           # how many null is present in each column

df_zerofill=df.fillna(0)  # fill null with 0
df['SepalLengthCm']= df['SepalLengthCm'].fillna(df['SepalLengthCm'].mean())

# column manipulation   (permanent changes)
df.dtypes
df=df.rename(columns={'SepalWidthCm': 'SepalWidth_cm'}) #rename column
  
#make sure there r no Nan values before u change datatype
df['SepalLengthCm']=df['SepalLengthCm'].astype('int')  #flaot to int

df['NewSepalLengthCm']= df['SepalLengthCm'].apply(lambda x:x*2)

# Data Aggregating and Grouping
grouped_mean= df.groupby('Species')['NewSepalLengthCm'].mean()
group_mean_ofTwoCategories=df.groupby(['NewSepalLengthCm', 'Species'])["SepalLengthCm"].sum()

# Aggregate multiple fxns
grouped_aggr= df.groupby('Species')['SepalLengthCm']. agg(['mean', 'sum','count'])
 ```
## Merging and joining two data frames
```python
df1 = pd.DataFrame({'Key': ['A', 'B', 'C'], 'Value1': [1, 2, 3]})
df2 = pd.DataFrame({'Key': ['A', 'B', 'D'], 'Value2': [4, 5, 6]})

# Merge based on 'Key' column
# pd.merge(df1,df2)   # base
merge=pd.merge(df1,df2, on='Key', how='inner')
merge=pd.merge(df1,df2, on='Key', how='outer')
merge=pd.merge(df1,df2, on='Key', how='left')
merge=pd.merge(df1,df2, on='Key', how='right')
```
# Reading Data from Various Data Sources
- from json
```python
import pandas as pd
from io import StringIO
Data = '{"employee_name": "James", "email": "james@gmail.com", "job_profile": [{"title1":"Team Lead", "title2":"Sr. Developer"}]}'
df=pd.read_json(StringIO(Data))

df.to_json()                   # dict kinda format
df.to_json(orient='index')    
df.to_json(orient='records')   # list of row wise json obj
```
- url 

> [!NOTE] When using web / url related data analysis ud need to install dependencies like html5, lxml etc 

```python
# comma seperated data
df=pd.read_csv("https://archive.ics.uci.edu/ml/machine-learning-databases/wine/wine.data",header=None)  # header= none to make names of colums to just numbers
df.head()

df.to_csv('wine.csv')    # create a csv file 

!pip install lxml
# if the above installation doesn't work
import sys
print(sys.executable)
!{sys.executable} -m pip install lxml

url="https://www.fdic.gov/resources/resolutions/bank-failures/failed-bank-list/"
df =pd.read_html(url)        # read url
df[0]                       # to get in the form of table , not as list

url="https://en.wikipedia.org/wiki/Mobile_country_code"
pd.read_html(url,match="Country",header=0)[0]
```
- excel
```python
!pip install openpyxl       # for excel 
df_excel=pd.read_excel('data.xlsx')

df_excel.to_pickle('df_excel')   # to convert it to pickle file
pd.read_pickle('df_excel')
```