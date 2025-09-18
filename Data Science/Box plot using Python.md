- min , max, median, Q1, Q3  (IQR)
- easy - seaborn / matplotlib
```python
import seaborn as sns

lst=[35,40,56,89,65,63,85,97,200]
sns.boxplot(lst)                   # vertical boxplot

# or
import matplotlib.pyplot as plt
plt.boxplot(lst, vert=False, showmeans=True)
plt.title("Boxplot of lst")
plt.show()
```
- finding all values manually (not needed at all)
```python
import numpy as np
lst=[35,40,56,89,65,63,85,97,200]
minimum,q1, median, q3, maximum= np.quantile(lst,[0,0.25,0.5,0.75,1.0])
IQR= q3-q1
lower_fence= q1-IQR*1.5
higher_fence=q3+1.5*IQR
```