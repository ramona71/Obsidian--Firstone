## Handling missing values
- two methods
	- Imputation (using central tendencies to fill the missing values)
	- Dropping - deleting all rows with missing values (not efficient if dataset is smol)
- NaN is missing values
- Cases to use mean , median and mode
	- there are outliers and most data is distibuted in one region so distribution is called skew- cna't use mean cuz the outliers increase the value
	- so we use median or mode![[Pasted image 20240912225147.png]]
	- If distribution is nomal, fill with mean
```py
dataset['salary'].fillna(dataset['salary'].median(), inplace=True)
dataset['salary'].fillna(dataset['salary'].mean(), inplace=True)
```