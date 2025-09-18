- Synthetic Minority Oversampling Technique
- Instead of just duplicating minority samples, SMOTE **creates synthetic new ones** by interpolating between existing minority class points.
- How it works
	1. Take a random minority class sample.
	2. Find its _k_ nearest neighbors (usually k=5).
	3. Randomly pick one of those neighbors.
	4. Create a **new synthetic sample** somewhere between them (on the line joining them).
- `make_classification` - create a binary classification/ multi class classification
- `n_redundant=0`   - 
```python
from sklearn.datasets import make_classification

x,y=make_classification(n_samples=1000,n_redundant=0, n_features=2, n_clusters_per_class=1, weights=[0.90], random_state=42)

```