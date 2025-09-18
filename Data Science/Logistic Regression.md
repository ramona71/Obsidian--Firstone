- to solve <mark style="background: #FFF3A3A6;">binary classification</mark> -> o/p is binary categories
	- ![[Pasted image 20250918102907.png]] 
	- (binary - pass/fail)
- why is it called logistic regression when it's classification? 
	- because we can apply regression
- can we solve it with linear regression?
	- no cuz the presence of outliers will bend the best fit line and it won't accurately classify anymore
- <mark style="background: #FFF3A3A6;">WHY CAN WE NOT USE LINEAR REGRESSION FOR CLASSIFICATION</mark>?
	1. outliers  (best fit line changes )
	2. output >1 or output <0 is possible , to avoid this we need to squash that line (not possible with linear regression)
- squashing line is possible with logistic regression
- Logistic Regression vs Linear Regression
	- In **linear regression**, the model output is a straight line (unbounded, can go from −∞-\infty−∞ to +∞+\infty+∞).
	- In **logistic regression**, instead of fitting a straight line to the target, we apply the **logistic (sigmoid) function** to “squash” that line into the range [0,1].
- Visualization intuition
	- Without sigmoid → you’d just have a line going negative or above 1 (not valid for probabilities).
	- With sigmoid → you get an S-shaped curve, mapping values smoothly into [0,1].
- The sigmoid activation function is:
$$
\sigma(z) = \frac{1}{1 + e^{-z}}
$$
- Input z=wTx+b (a linear function of features, i.e., the line/plane).
- Output is “squashed” between **0 and 1**, so it can be interpreted as a **probability**.
	![[Pasted image 20250918104453.png]]
## Logistic Regression math
- on best fit line , we apply sigmoid activation fxn
- 