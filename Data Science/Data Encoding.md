- Converting categorical features to numerical values
	- ex: converting 'phd' or 'B.Tect' into numbers to model can understand and train
# Nominal / OHE encoding
- nominal/ one hot encoding - category data to numerical data (each category represented as binary vector - each bit corresponds to a unique category)
	![[Pasted image 20250917214003.png]]   ![[Pasted image 20250917214013.png]]
- disadvantage 
	- creates 1000 columns if 1000 features r present (not ideal for large datasets)
	- sparse matrix -> causes overfitting 
```python
import pandas as pd
from sklearn.preprocessing import OneHotEncoder

df=pd.DataFrame({
    'color':['red', 'green','green', 'pink', 'blue']
})
# create an instance of onehot encoder
encoder=OneHotEncoder()

#perform fit and transfo
encoder.fit_transform(df[['color']]) # gives sparse matrix
encoded=encoder.fit_transform(df[['color']]).toarray() #gives array
  
# here the categories are first arranged in asc order blue-> green-> red and 1s are assigned after
# any new data should already of present categories, stuff like purple won't be allowed
encoder_df=pd.DataFrame(encoded, columns= encoder.get_feature_names_out())
# can concat with the og table
pd.concat([df,encoder_df], axis=1)
```
- for 'tips' dataset
```python
from sklearn.preprocessing import OneHotEncoder

encoder = OneHotEncoder(drop=None, sparse=False)
encoded = encoder.fit_transform(tips[["sex","smoker","day","time"]])

# Convert back to DataFrame
encoded_df = pd.DataFrame(encoded, columns=encoder.get_feature_names_out(["sex","smoker","day","time"]))
tips_encoded = pd.concat([tips.drop(["sex","smoker","day","time"], axis=1), encoded_df], axis=1)

print(tips_encoded.head())
```
- **`drop=None`**
    - Default = `None` → keeps **all categories**.
    - If you set `drop='first'`, it will drop the first category of each feature → useful to avoid multicollinearity in regression.
    - Example: `sex` → instead of `sex_Female` + `sex_Male`, you only get `sex_Male` (Female is implied).
- **`sparse=False`**
    - Default in modern scikit-learn is `sparse_output=False` (used to be `sparse=True` before v1.2).
    - `sparse=True` → returns a **sparse matrix** (efficient for large datasets).
    - <mark style="background: #FFF3A3A6;">`sparse=False` → returns a normal NumPy array</mark> (easier to convert into pandas DataFrame).
# Label Encoding
- label and ordinal encoding- 2 techniques , category-> numerical data
- assigns unique numerical label to each category in a column ( 0-> len(n)-1)
	- ![[Pasted image 20250917222434.png]]
```python
from sklearn.preprocessing import LabelEncoder

lbl_encoder=LabelEncoder()
lbl_encoder.fit_transform(df['color'])

# try to find the encoded value of a datapoint
lbl_encoder.transform([['red']])    # output: array([3]) - red is assigned 3
```
### Ordinal encoding
- type of label encoding but where ranking is required (ex: phd has more rank than high school)
	- ![[Pasted image 20250917223455.png]]
```python
from sklearn.preprocessing import OrdinalEncoder

# create and instance, fit and transform
# here the order is imp, red -> least rank and green-> highest rank
encoder= OrdinalEncoder(categories=['red', 'blue','green','pink'])
encoder.fit_transform(df[['color']])
```
# Target Guided Ordinal Encoding
- encode categorical variable based on their relationship with the target variable
- useful when categorical variable with large no of unique categories
- we replace it with mean/ median of target variable for that category
```python
import pandas as pd

# Example dataset
data = {
    "city": ["London", "New York", "Paris", "Tokyo", "London", "Paris", "Tokyo", "New York"],
    "price": [100, 200, 300, 250, 200, 320, 250, 180]
}

df = pd.DataFrame(data)

# Step 1: Compute mean price per city
mean_price = df.groupby("city")["price"].mean().to_dict()
print("Mean Price Mapping:", mean_price)

# Step 2: Map city to its mean price
df["city_encoded"] = df["city"].map(mean_price)

# Step 3: View result
print(df[["price", "city_encoded"]])
```