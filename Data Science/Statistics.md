`- field that deals with collection , organization, analysis, interpretation, and presentation of data
	- for decision making, behavior of client
- mean , median, distribution of data  -> analyze data
- charts and graphs
	- histograms
	- pdf
	- cdf
## Usage
- ML
- DA
- DS
- Business analytics
- risk analyst
- every domain
# Types of statistics
1. Descriptive
	- organizing and summarizing data
	1. Measure of central tendencies
		1. mean
		2. median 
		3. mode
	2. Measure of dispersion
		1. variance
		2. standard deviation
2. Inferential
	- collect data(sample data) -> conclude inferences (population data)-> using experiments (z test, t test etc)
	- size of pop data > size of sample data

- EX : heights of students of a single class of 4 students {180, 156, 189, 163} cm. Clg has 1000 students
	- descriptive -> mean, median, mode 
	- inferential -> from a single class (4 students) to average height of 100 students (whole clg)
## Population data (N) vs Sample data(n)
- from an entire population 100k , sample of 10k is taken
- cuz we can't collect data from everyone
# Measure of central tendency
1. Mean
	-  ![[Pasted image 20250703140459.png]]
	-  myu-> for population / generally
	- x dash -> for sample
> age ={1,2,5,8}    -> c/a a distribution
2. Median
	-  helps to identify an outlier if present
		- age ={1,2,5,8, 1000}    -> mean changes a LOT but median is almost same 
	- odd no of elements-> middle one
	- even no of elements -> avg of 2 middle elmts
3. Mode
	- most repeating (max frequency)
# Measure of dispersion
1. Variance
	- gives the spread
	- two distributions can have same mean but different distributions
	- for pop (N)
		- ![[Pasted image 20250703142911.png]]
	- for sample (n):
		- ![[Pasted image 20250703143337.png]]
		-  ==n-1 in sample variance==
	- ex : ![[Pasted image 20250703143123.png]]
		- spread is different 
		- age1 -> less spread
		- age2 -> more spread
2. Standard deviation
	- gives how far a data point is away from the mean
	- sqrt(variance)
	- a data point is 2 units away from mean (+ if right side, - if left side)
- ![[Pasted image 20250704183556.png]]
## why sample variance has n-1
- ![[Pasted image 20250710160357.png]]
- When calculating sample variance, you’re using the **sample mean** x bar instead of the **true population mean** (μ). But x bar is an estimate that’s already based on the data - it "pulls" toward the sample points. This makes the squared deviations **slightly smaller on average** than they would be if you had the actual population mean.
So:
- Dividing by **n** would **underestimate** the true population variance.
- Dividing by **n−1** instead corrects for this underestimation — it's called **Bessel’s correction**.
### child like explanation
- imagine
You and your 4 friends (so 5 kids in total) are playing a game. You each pick a number and write it on paper. Now you want to find out **how different everyone's number is from the average**.

But here's the twist:

To find the average, you **already used all your numbers**. That means the average is based on the group’s own numbers — it's like using your own answers to check your homework.

 What’s the problem?

If you just count how far each number is from that average, your results will **look a little too small** — because the average came from the same numbers. It **“cheats” a little** and makes the group look more similar than they really are.

🎯 So what do we do?

We fix it by **not trusting the group 100%**. We say:

> “Since we used up one number to help us get the average, we only have **4 truly free numbers**, not 5.”

So instead of dividing by **5**, we divide by **4**.  
That’s the **n−1** rule. It's called **losing 1 degree of freedom**.
# Variable
- property that can take up any value
	- age , gender, height
- types of variables
	1. Quantitative
		1. Discrete Quantitative variable        (whole no : 5 kids , never 5.5 kids)
		2. Continuous Quantitative variable  (any values : 165.5 cm height, 165.6 cm )
	2. Qualitative / Categorical                         (not numerical : gender, colors)
# Random variables
- denoted by -> X
- X -> FXN -> whose values r derived from Process/ Experiments
	- ![[Pasted image 20250710162504.png]]
- Random Variables
	1. Discrete
		1. tossing a coin, rolling a dice  -> has fixed values
	2. Continuous
		1. inches of rain tomorrow   -> can have any values 
# Histograms
- discrete and continuous will have different histograms
- below is a discrete histogram
	- ![[Pasted image 20250710163329.png]]
- to get a smoother curve -> kernel density Estimation
# Percentile and Quantiles
- Percentage 
	- (no / total )* 100
- Percentile -> value below which a certain percentage of observations lie
	- (no of values before the value / total) * 100
	- ![[Pasted image 20250710164256.png]]
	- to find value from percentile
		- ![[Pasted image 20250710164416.png]]
		- if u get decimals, get average of the two positions
		- value =3.75?  average 3rd and 4th position values
- Quartile -> percentile, not percentage
	- 25 percentile -> First quartile
	- 50 percentile -> Second quartile
	- 75 percentile -> Third quartile
# 5 no Summary -> to remove outliers
- Minimum
- 1sr Quartile
- Median
- 3rd Quartile
- Maximum

- Also need 
	- Lower fence
	- Higher fence
	- IQR (inter quartile range) 
		- difference between 3rd and 1st Quartile
- anything below or above fences will be outliers
- ![[Pasted image 20250710165025.png]]
- Box plot -> to visualizer outlier
# Covariance and Correlation
- both r statistical measures, determines the relationship btw 2 variables
	- used to understand how one variable change wrt changes in other
1. Covariance
	- if both variables change together (increase/decrease) -> +ve covariance
		- + ve covariance  -> size of house increase, price increase
	- one increase and other decrease -> -ve covariance
	- ![[Pasted image 20250710182152.png]]
	- ![[Pasted image 20250710182209.png]]
	- it's all sample mean and sample size
	- ![[Pasted image 20250710182728.png]]
	- ![[Pasted image 20250710182835.png]]
	- 
- Adv :
	- Quantify relationship btw x and y
- Dis:
	- Covariance doesn't have a specific limit value, u can't say how strong it is from a specific value 
	- let cov (A,B) =30  , and cov(B,C)= 300
	- but we can't say cov(b,c) > cov(a,b)
	- can't compare, here correlation comes in
1. Correlation
	- 2 types
		1. Pearson Correlation Coeff
			- limits `[ -1 to 1] ` 
			- ![[Pasted image 20250710183543.png]]
			- more the value towards +1 -> the more positive correlated x and y is
			- more the value towards -1 -> the more negative correlated x and y is
			- dis -> not able to capture correlation for non linear data
		2. Spearman Rank Correlation
			- ![[Pasted image 20250710184224.png]]
			- doesn't use raw data but ranks of data (like serial no-> 1st data point gets 1, second get 2 and so on)
			- ![[Pasted image 20250710184610.png]]
 - where correlation is used? Feature selection
	 - to determine price of house, size, no of rooms , location plays a role
	 - but no of people that stays? doesn't, so it's correlation will be 0 -> helps to feature select