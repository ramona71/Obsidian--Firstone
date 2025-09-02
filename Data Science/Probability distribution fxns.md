- describe how probabilities r distributed over values of random variable
- right screwed, left screwed
- two types of prob distribution fxns
	1. Prob mass fxns (PMF) 
		- used for discrete random variable
	2. Prob density fxn (PDF)
		- for continuous random variable
- Cumulative distribution fxns (CDF) - for both above fxns
# 1. PMF
- distribution of discrete random variable
- ex : roll a fair dice => Pr(1)=Pr(2)=Pr(3)=Pr(4)=Pr(5)=Pr(6)=1/6
	- ![[Pasted image 20250711111140.png]]
- Cumulative density fxn (CDF) - combine all probs as we go on 
	- pr (1) , pr(1 and 2), pr(1,2 and 3) -> cumulative prob
	- ![[Pasted image 20250711111338.png]]
- where is PMF used?
	- discrete variable
	- Pr (x<=2) = Pr(1)+pr(2)
	- Pr (x<=5) = Pr(1)+pr(2)+pr(3)+pr(4)+pr(5)

> [!NOTE] CDF is always btw 0 and 1
# 2. PDF
- distribution of continuous random variable
	- ![[Pasted image 20250711111905.png]]
	- it's symmetric
	- area under curve =1
		- ![[Pasted image 20250711122734.png]]
	- CDF of this fxn - usually takes a S shape
		-  ![[Pasted image 20250711112020.png]]
		- Pr(x<= 40) ? = 0.5 or 50% from the graph
		- ![[Pasted image 20250711121917.png]]
		- higher the val in PDF , the more the slop in CDf, 40 has highest prob so it has the most slope
		- ![[Pasted image 20250711122216.png]]
		- slope is calculated with it's formula
		- slope=gradient of CDF = Prob density 
>  gradient of CDF = Prob density 
- PDF properties
	- always non negative  ( f(x)>=0 ) for all x
	- The total area under the PDF curve =1 
		- doesn't matter the distribution (right screwed, left screwed)
	- wrt different distribution , f(x) changes
		- gaussian, benoulli, binomial, normal, binomial ,log normal etc
# Types of Prob distribn
> pdf -> continuous random variable
> pmf -> discrete random variable

- Bernoulli distribn  - pmf -> outcomes r binary -> 0/1 -> discrete random variable
- Binomial distribn  - pmf -> discrete random variable
- Normal /Gaussian - pdf -> continuous random variable ->most seen 
	- ![[Pasted image 20250711123250.png]]
- Poisson distribn - pmf
- Log normal distribn - pdf -> continuous random variable
- uniform distribn - pmf

- where r these used?
	- ![[Pasted image 20250711123652.png]]
	- for EDA and FE

# Bernoulli distrbn
- a ==discrete== probability distribution , models a random variable with two possible outcomes, typically labeled as "success" (1) and "failure" (0). 
- ==binary outcomes== -> k = 0/1 
-  p( probability of success) (where 0 ≤ p ≤ 1). 
-  probability of failure is then q= 1-p 
- ex : coin flip , yes/no
- ![[Pasted image 20250711125435.png]]
- ![[Pasted image 20250711130129.png]]
- ==discrete -> so pmf 
- ![[Pasted image 20250711125725.png]]
> ![[Pasted image 20250711125654.png]]
- ![[Pasted image 20250711125942.png]]
### Mean of Bernoulli Distrbn
- ![[Pasted image 20250711130426.png]]
$$
E (x)= ∑ k * p(k)  --->     k=0 -> 1
$$- to find mean of distrbn
### Median
- ![[Pasted image 20250711131123.png]]
### Mode for benoulli
- ![[Pasted image 20250711131148.png]]
### Variance and SD
- variance - how far we're from mean
- ![[Pasted image 20250711131537.png]]
# Binomial distrbn
- n independent experiments , with each having yes/no as outcome
- ex : tossing a coin 10 times in a row
- binomial is bernoulli if n=1
- ==discrete random variables -> so pmf
- B(n,p)
-  n -{0,1,2......... n times}     p ->` [0 ,1]`, q= p-1   , k= {0,1,2,........ } =no of successes
- ![[Pasted image 20250711140959.png]]
- ![[Pasted image 20250711140941.png]]
- where is it used?  ![[Pasted image 20250711141127.png]]
- the question ![[Pasted image 20250711141454.png]]
	 ![[Pasted image 20250711141438.png]]
# Poisson distrbn
- ==discrete== prob disrbn -pmf
- describes no of events occurring in fixed interval of time
	- ex : no of people visiting hospital every hour
- $\lambda$  -> expected no of events occurring at every time interval
	- expected no of people that come every hour , ex: 3
- Prob of a person visiting at 5 pm
	![[Pasted image 20250717142348.png]]
- Prob of a person visiting at4pm and 5 pm
	- ![[Pasted image 20250717142500.png]]
- ![[Pasted image 20250717142057.png]]
	- as $\lambda$ increase, the spread increases
- mean= variance of Poisson distrbn
	![[Pasted image 20250717142614.png]]
# Normal/ Gaussian distbn
- ==continuous== prob distribn  -> continuous random variable - pdf
- ==Bell curve ==
	- ![[Pasted image 20250711144323.png]]
- variance increase , spread increase
- ![[Pasted image 20250711154226.png]]
- ex: heights/ weights of students in class , iris dataset  -> all follow normal distribution
- formula used to calculate pdf ![[Pasted image 20250711154427.png]]
- mean of normal distibution
	![[Pasted image 20250711154512.png]]  ![[Pasted image 20250711154538.png]] 
### Empirical Rule of normal/ gaussian distrbn
- 68 , 95, 99.9 rule
	![[Pasted image 20250711154734.png]]
- to say that a random variable X ,  falls between 
	![[Pasted image 20250711154954.png]]

# Standard Normal Distrbn
- Z- score -> how much standard deviation it is away from mean
> X belongs to Standard normal distrbn if $\mu$ =0  $\sigma$ =1
- can convert any distbn to SND with z-score
	![[Pasted image 20250711155823.png]]
> Z-score can be +ve or -ve 
- convert a random variable X to another random var Y with z-score
	![[Pasted image 20250711155904.png]]![[Pasted image 20250711155938.png]]
- ![[Pasted image 20250711160145.png]]  
	- the area will be the yellow shaded 
		- ![[Pasted image 20250711160207.png]]
	- ![[Pasted image 20250711160355.png]]

> [!NOTE] Z-Score is used to standardize the data
- below , standardization is very much required
	 ![[Pasted image 20250711160608.png]]
	 ![[Pasted image 20250711160702.png]]


# Uniform Distrbn
- two types
	1. Continuous uniform distrbn -> pdf
	2. Discrete uniform distbn  -> pmf
### 1. Continuous uniform distrbn / Rectangular distribn
- continuous random var
- symmetric , and the outcome lies between certain bounds (a (min) ,b(max))
- U (a,b)
	 ![[Pasted image 20250711161514.png]]       ![[Pasted image 20250711161240.png]]
	 ![[Pasted image 20250711161639.png]]
- QQQQ ![[Pasted image 20250711161947.png]]
	![[Pasted image 20250711162009.png]]
	![[Pasted image 20250711162039.png]]
### 2. Discrete uniform distbn 
- discrete random var -> pmf
- rolling a dice
- U (a,b)
	![[Pasted image 20250717142915.png]]
	n= b-a +1

# Log Normal Distrbn
- 
# Central Limit Theorem
- depends on sampling distrbn