- expression- sequence of operators and operands, specifies as computation
	- all the below r expressions
	- ![[Pasted image 20250113160911.png]]
- statement- complete line of code with semi colon at end
	- expression is also a type of statement
	- ![[Pasted image 20250113161040.png]]
	- below is null statement
	- ![[Pasted image 20250113161241.png]]
	- does nothing but can be handy sometimes
# Operators
- operators 
	- unary
	- binary
	- ternary
- types
	- assignment (=)
	- arithmetic
	- increments/ decrement- works as assignment/ arithmetic
	- relational- comparing  (>, <,  != )
	- logical (&&,|| )
	- member access  
	-  other
# Assignment
- `=`
- more than one variable can be assigned in single statement
- int num{5};  -> initialization
- int num=5;  -> assignment
- lhs= rhs
	- lhs should be compatible with rhs(type checking by compiler before assigning)
- num1=num2=100; 
	-  num1 <- num2 <- 100;           from   L <-  R
# Arithmetic
-  +, -,` *`, / , %
- all work with all data types 
> % -> works only with integers
 be alert when dividing integers 
- int c= 100/200 ; what is c?     
 	    Ans : 0   (.5 is just removed)

> [!cpp compiler doesn't automatically convert int to float when dividing]
> 
# Increment/ decrement
- used on  -> int, double, pointers
- prefix  -> ++num
- postfix -> num++
Q  .  int counter =10;
	result= ++counter +10;
	result =??      
	                  
	ans: 21
Q . result = counter++ +10;
	result ? 
# Mixed (data) type expressions
- all operands should be of same type, if not cpp automatically converts (coercion) 
- if doesn't -> shows compiler error
- type coercion- conversion of one operand to another data type
- order
	- long double, double, float, unsigned long, long, unsigned int, int
	- short ,char -> always converted to int
- Promotion- lower to higher conversion
- Demotion - higher to lower conversion
>[!NOTE] lower is converted to higher automatically!!! 
> 2 * 5.2      (2 promoted to 2.0)

> u have to manually do higher to lower
> int num=0;
> num= 100.2                 (100.2 is demoted to 100)
## Casting
- to convert to a specific type that we want
`static_cast <type>`
- `double a= static_cast<double>(total)/ count;`         // converts total to double
c style cast is
- `double c=(double) total/count; `
- what do you think will be the `average` in both images?
- ![[Pasted image 20250402164507.png]]
- ![[Pasted image 20250402164622.png]]
-  1st -> integer , 2nd-> double
- ![[Pasted image 20250605101709.png]]
- it won't print as 2.0 because .0 is ignored unless specified with `setprecision`
- # relational operators
- `==     !=`
- compares values of 2 expressions (works for int, char, expressions, bool etc)
	- expr1 == expr2 
	- ex : 100 == 50+50
	- 'a'!= 'b'
- ways to use
	- ![[Pasted image 20250605102003.png]]
- boolalpha -> to show as true/false
- noboolalpha -> to show as 0/1
> compiler stores floating points as approximations
- ![[Pasted image 20250605102559.png]]4
	- so these two will be equal
- ![[Pasted image 20250605102718.png]]
## Relational operators 
- `> , >= , < , <= , <=> three way comparision`
- `<=>`
	- ![[Pasted image 20250605103310.png]]
# compound operators
- most used
- ![[Pasted image 20250605103348.png]]
# Logical Operators
- not !
- and &&
- or ||
- evaluated boolean algebra
- Precedence order (high to low)
	-  not , and , or
![[Pasted image 20250622104614.png]]
## Short Circuit
 - evaluation of logical expression stops as soon as result is know
	 - `expr1 && expr2 && expr3`   if false, won't perform the second and
	 - `expr1 || expr2 || expr3`   if true, won't perform second or
- logical operators are the best method to check if input is within the boundaries or not
# Operator Precedence and Associativity
- (not finished)
- same row has same precedence
![[Pasted image 20250622110011.png]]


```cpp
```
- m
```cpp
```