```python
import pandas as pd
df=pd.read_csv('dataset.csv')
df.head()

df.info()      # Summary of dataset
df.describe()  #descriptive summary of the dataset
df.shape
df.columns     # all column names
df['quality'].unique()   # the actual categories in that category column
df.isnull().sum()

df.duplicated()          # duplicate recodes - > True/ False
df['df.duplicated()']    #duplicates in table format
df.drop_duplicates(inplace= True)   # Permanent deletion

df.corr()                # correlation 

# for the heatmap
import matplotlib.pyplot as plt
import seaborn as sns
plt.figure(figsize(110,6))
sns.heatmap(df.corr(), annot=True)  # correlation heatmap

# visualize to find if it's imbalanced or not (it's imbalanced here)

df.quality.value_count()   # count of values of feature 
df.quality.value_count().plot(kind='bar')   # plot the values of a feature

for column in df.columns:         # a overlapping hist plot of all features
    sns.histplot(df[column],kde=True)
    
sns.histplot(df['alcohol'])    # hist plot of individual features

#univariate,bivariate,multivariate analysis (plots all features against all other features)
sns.pairplot(df)

##categorical Plot
sns.catplot(x='quality', y='alcohol', data=df, kind="box") # box plot

sns.scatterplot(x='alcohol',y='pH',data=df, hue='quality')
```
