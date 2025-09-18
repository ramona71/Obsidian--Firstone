- visualization library based on Matplotlib
```python
!pip install seaborn

import seaborn as sns
tips=sns.load_dataset('tips')

# create scatter plot
import matplotlib.pyplot as plt
sns.scatterplot(x='total_bill', y='tip', data=tips)
plt.show()

# line plot
sns.lineplot(y='tip', x='total_bill', data=tips)
plt.title("How much they're tipiing based on bill")

# categorical plot
  
# Bar plot
sns.barplot(x='day', y='total_bill', data=tips)
# violin plot
sns.violinplot(x='day', y='total_bill', data=tips)

# histogram
sns.histplot(tips['total_bill'], bins=10, kde=True)
# kde plot
sns.kdeplot(tips['total_bill'], fill=True)
```
- for outliers
```python
# box plot
sns.boxplot(x='day', y='total_bill', data=tips)
```
- kde if for the graph line 
- corr is to find correlation of one feature with other / entire dataset
	- only takes numerical values (can't take strings)
	- tabular output
-  pair plot does the same too
	- visual output
```python
corr# pair plot
sns.pairplot(tips)    # relation of every column with all other colms

## heatmap
corr=tips[['total_bill','tip','size']].corr()   #table format 
												#(only numerical features)
sns.heatmap(corr,annot=True,cmap='coolwarm')
```
- in sales dataset
```python
## Plot total sales by product
plt.figure(figsize=(10,6))
sns.barplot(x='Product Category',y="Total Revenue" ,data=sales_df, estimator = sum)
plt.title('Total Sales by Product')
plt.xlabel('Product')
plt.ylabel('Total Sales')
plt.show()

## Plot total sales by Region
plt.figure(figsize=(10,6))
sns.barplot(x='Region',y="Total Revenue",data=sales_df,estimator=sum)
plt.title('Total Sales by Region')
plt.xlabel('Region')
plt.ylabel('Total Sales')
plt.show()
```