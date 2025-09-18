- MCAR : missing completely at random -> data is just missing , no particular reason
	- unknowingly, or some error occured
- MAR: missing at random  -> missing cuz of some reason
	- some people r not comfortable telling answers to some questions
		- men about salary, women about weight etc
- MNAR : missing not at random -> missing cuz of specific reason
	- poor people mention income but rich won't
# [[Handling missing values]]
# [[Handling Imbalanced dataset]]
# [[Handling Imbalanced dataset using SMOTE]]
# [[Box plot using Python]]
# [[Data Encoding]]

# Corr
It computes **pairwise correlation coefficients** between **all numeric columns** in your dataframe.
- Each cell `(i, j)` in the correlation matrix is the correlation between **column i** and **column j**.
- Example from red wine dataset:
    
    - `alcohol` vs `quality` → correlation shows whether higher alcohol content is linked to higher wine quality.
        
    - `volatile acidity` vs `citric acid` → shows if wines with more volatile acidity tend to have less citric acid.
        
So it’s basically:
**`df.corr()` = correlation between every feature with every other feature (including the target column if it’s numeric).**

In red wine dataset, since `quality` is numeric (3–8), you also see its correlation with all chemical properties.

<mark style="background: #FFF3A3A6;">That’s why in heatmaps, you often check the **last row/column (quality)** to see which features are most related to wine quality.</mark>