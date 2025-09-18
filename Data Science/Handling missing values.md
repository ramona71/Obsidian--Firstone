- **Imputation = the process of filling in missing data values instead of dropping them.**
- u can remove the rows/ columns with missing value to handle with them
```python
```python
# check missing values
df.isnull()
df.isnull().sum()   # no of missing values column wise

df.dropna()         # to drop all the row with NaN values
df.dropna(axis=1)   #to drop all the colums with NaN values
df.dropna(axis=1, inplace= True)  # to make it permanent 
```
## Mean value imputation
- works well when u have normally distributed data
```python
df['age_mean']= df['age'].fillna(df['age'].mean())
df[['age_mean','age']]  # to display as list
```
- whatif we have outliers?
## Median value imputation
- for when the distribution is not normal and contain outliers
```python
df['age_median']= df['age'].fillna(df['age'].median())
```
## Mode value imputation
- for categorical values / for MCAR
- embarked on adventure or not? we'll find the most common answer and try to fill those Nan values with that category value
```python
df[df['embarked'].isnull()]
df['embarked'].unique()       # find the category values
df['embarked'].notna()   # not nan value are shown as True

mode_value= df[df['embarked'].notna()]['embarked'].mode()[0] # finds the most common embarkation port (ignoring missing values).
df['embarked_mode']= df['embarked'].fillna(mode_value)

df['embarked_mode'].isnull().sum()   # 0
```
- above [0] is used so that MOST FREQ term will be stored in `mode_value` variable to fill in Nan places
- `.mode()` itself → single most frequent value.
- to fill it with random value and not with the most freq
```python
import numpy as np

# get non-null values of embarked
vals = df['embarked'].dropna().values  

# fill NaNs with random choice from existing values (like mode-based but random)
df['embarked'] = df['embarked'].apply(lambda x: np.random.choice(vals) if pd.isna(x) else x)

```
## mean value imputation
```python
```