- <mark style="background: #FFF3A3A6;"> Supervised ML- > Regression</mark>
- ![[Pasted image 20250918105232.png]] single i/p -> model -> single o/p
- <mark style="background: #FFF3A3A6;">finds best fit line by changing slope and intercept with minimal error</mark> -> sum of distance from all points to the line should me minimal
- ![[Pasted image 20250918110000.png]]
	- x -> independent feature (i/p)
	- theta 0-> Intercept
	- theta1->slope / coefficient
- Error -  ![[Pasted image 20250918110050.png]]  (original - predicted datapoint)
# Cost fxn / Loss fxn 
- mean squared error
	- ![[Pasted image 20250918110325.png]]
	- m= no.of data points
- ## **What is the cost function used for?**
- The **cost function** (also called **loss function**) tells us **how wrong** our model’s predictions are compared to the actual values.
- It’s the objective we try to **minimize** during training.
- Linear Regression → Mean Squared Error
$$
J(w,b) = \frac{1}{m} \sum_{i=1}^m \big( y_i - \hat{y}_i \big)^2
$$
- Logistic Regression → Log Loss (Binary Cross-Entropy)
$$ J(w,b) = -\frac{1}{m} \sum_{i=1}^m \Big[ y_i \log(\hat{y}_i) + (1-y_i)\log(1-\hat{y}_i) \Big] $$
- Slope and Intercept

- Line equation:  
$$ \hat{y} = w x + b$$
- \(w\) = slope (steepness)  
- \(b\) = intercept (shift up/down)  

- Updated using gradient descent:  
$$
w := w - \alpha \frac{\partial J}{\partial w}, \quad b := b - \alpha \frac{\partial J}{\partial b}
\
$$
alpha- learning rate
- intuition
	- cost function is like error score
	- gradient descent nudges slope and intercept to reduce error until best fit line is found
- ![[Pasted image 20250918115021.png]] 
	- slope vs loss fxn (finding a slope where error is minimum)
# Convergence algo
- optimize changes of w/ theta 1 value (slope) to reach global minima on gradient slope
- 