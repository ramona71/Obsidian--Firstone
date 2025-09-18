- ex:  during classification, we gonna find fraud transactions , but dataset has 1000 correct ones and 2 fraud one's . how tf is ur model gonna identify frauds if there r little af frauds to train on ?? -> by handling imbalanced datasets
- Two methods 
	1. Up sampling - increase minority
	2. Down Sampling- reduce majority
```python
import pandas as pd
import numpy as np
np.random.seed(123)
  
n_samples= 1000
clas0_ratio= 0.9
n_class0=int(n_samples*clas0_ratio)
n_class1= n_samples-n_class0
n_class0,n_class1

# Create class 0 data
class_0 = pd.DataFrame({
    'feature_1': np.random.normal(loc=0, scale=1, size=n_class_0),
    'feature_2': np.random.normal(loc=0, scale=1, size=n_class_0),
    'target': [0] * n_class_0   # label all rows as class 0
})

# Create class 1 data
class_1 = pd.DataFrame({
    'feature_1': np.random.normal(loc=2, scale=1, size=n_class_1),
    'feature_2': np.random.normal(loc=2, scale=1, size=n_class_1),
    'target': [1] * n_class_1   # label all rows as class 1
})

df = pd.concat([class_0, class_1], ignore_index=True)
print(df['target'].value_counts())  # check imbalance
```
- **`np.random.normal(loc, scale, size)`**
	- Generates numbers from a **normal distribution**.
	- `loc` = mean of the distribution.
	- `scale` = standard deviation.
	- `size` = how many numbers to generate.
# Up Sampling
- create two data frames - separating minority and majority
```python
df_minor= df[df['target']==0]
df_major= df[df['target']==1]
df_major,df_minor

from sklearn.utils import resample
df_minor_upsampled=resample( df_minor,
         replace=True,            # sample with replacement
         n_samples= len(df_major), # size
         random_state=42)   # seed
df_upsampled =pd.concat([df_major, df_minor_upsampled])
df_upsampled['target'].value_count()    # will be same as major's size
```
# Down Sampling
- not recommended cuz you lose data 
```python
df_minor= df[df['target']==0]
df_major= df[df['target']==1]
df_major,df_minor

from sklearn.utils import resample
df_major_downsampled=resample( df_major,
         replace=False,            # to reduce datapoints
         n_samples= len(df_minor),
         random_state=42)   # seed
df_downsampled =pd.concat([df_minor, df_major_upsampled])
df_downsampled['target'].value_count()    # will be same as major's size
```