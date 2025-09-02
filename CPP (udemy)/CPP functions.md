- Types
	- CPP standard libraries (functions and classes)
	- Third party libs (just use others man, don't write all that)
	- own fxns and classes

> [!NOTE] Don't care how the fxn works
> just focus on what it does (abstraction)
- Global fxns  `<cmath>`
	- `sqrt(200.00)`
	- `pow(12,2)`
- better to understand previously existing libraries before making own
	- ![[Pasted image 20250308112545.png]]
- ![[Pasted image 20250308113021.png]]
	- 6.54269 x 10 power 8
- random number generator
	- ![[Pasted image 20250308113427.png]]
# fxn prototype  -> use it often
- fxn needs to be declared before it's called -> else gives error
- fxn prototype solve this issue 
	- forward declarations  (fxn declared at the beginning)
	- own header file (.h) 
- ex
	![[Pasted image 20250308121925.png]]
	 - semicolon at end !!!!!!!!!!!!!!  -> dont forger
	- better to include parameters in prototype (for documentation)
- Q
	![[Pasted image 20250308122223.png]]
# fxn parameters
- parameters - fxn definition (formal parameters)
- arguments - fxn call  (actual parameters)
- ![[Pasted image 20250308122927.png]]
	- here, "Frank" is c string literal
	- but cpp compiler converts it into cpp string obj (standard sting) but better to convert it
	- The function expects `std::string`, but `"Frank"` is a `const char*`. This works because `std::string` has a constructor that takes `const char*`, but it is good practice to be explicit.
	- same thing happens when you pass a `int` to a `double`, compiler automatically converts int to double
## Pass by value
- fxns make copy of parameters , so can't change og parameters (pass-by-value)
- formal parameter is copy of actual parameter
	- ![[Pasted image 20250308123449.png]]
- can have any no. of return statements at any point in fxn but better to have only one return statement at last 
## Default arguments
- unless parameter is specifically passed, the default value of it will be considered
![[Pasted image 20250308141608.png]]
- usually default parameters are defined only in fxn prototypes, not in fxn definition
![[Pasted image 20250308141814.png]]
- if first parameter is default, then all gotta be default 
## Fxn overloading (polymorphism- abstraction)
- same name, different parameter lists
![[Pasted image 20250308143554.png]]
- type of polymorphism
- better option -> templets
- can't overload based on return type
![[Pasted image 20250308143639.png]]
	- can only overload based on parameter list
- sometimes the compiler converts the data type to match 
	- like float to double
	- c-style string(array of char)(vector<string /> v) to cpp standard string obj
	- char to ascii int
	- ![[Pasted image 20250308144027.png]]
- when keeping default to overloaded fxn , be a little careful
	- ![[Pasted image 20250308144541.png]]
	- gives error , doesn't take either of the default val
# Passing arrays to fxns
> array is not copied, just adr of first element of array is copied (not even no of elements of array is know, just first adr)
-  so -> WE CAN CHANGE THE ARRAY IN FXNS
	- use cases-> to zero all the elements/ print elements
	- ![[Pasted image 20250605105044.png]]
- recommended to pass size too 
	- ![[Pasted image 20250605104936.png]]
- to not modify array -> use `const`
	- ![[Pasted image 20250605105158.png]]
- U CAN SEND THE ARRAY BY PASS BY VALUE TOO
-  but PASS BY REFERENCE is prefered
# Pass by reference
- default is pass by value
- but with arrays we do pass by reference so we can change it in fxns
- so for other variables, instead of making a copy in the fxn , you can send the address n change the variable value directly
- use `&` to pass by reference
	- ![[Pasted image 20250623073957.png]]
- ex: swap fxn
	- ![[Pasted image 20250623074057.png]]
- U CAN SEND THE ARRAY BY PASS BY VALUE TOO
	- ![[Pasted image 20250623074200.png]]
- but PASS BY REFERENCE is prefered
	-  ![[Pasted image 20250623074252.png]]
- use const to not change the array tho it's passed through pass by reference 
	- ![[Pasted image 20250623074403.png]]
# Scope
- 2 types- local and global
- identifiers n fxns - block scope 
	- int main ()- is also block scoped (it's a fxn)
	- local variables r not preserved between fxn calls
	- nesting- inner blocks can use outer variables but outer blocks cannot use inner one's
	- { } - block 
## Static local variables
- value is PRESERVED btw fxn calls 
- only initialized once
- `static int number=10;`
- static variable is like global variable that can be initialized inside fxns
- GLOBAL CONSTANTS - okay to use
- GLOBAL VARIABLES - don't , not recommended
- if a same variable is declared locally and globally, the local one will be used before the global one
	- below, num is declared both locally n globally, but only local value (1000 and x) will be printed
	- ![[Pasted image 20250623075956.png]]
- global variables can be changed inside fxns, they can be changed anywhere
# Fxn calls