- ![[Pasted image 20250106162254.png]]
- games using unreal engine- need libraries (backend libraries)

> [!Find the error in below code]
```cpp
#include<iostream>
int main(){
    int favourite_number;
    std::cout<<"Enter your favourite number between 1 to 100 :";
    std::cin>>favourite_number;
    std::cout<<favourite_number+ "That's my favourite number too!!" << std::endl;
    return 0;
}
```
- Ans : - can't concatenate int (favourite_number) with string , so just do
```cpp
std::cout << favourite_number << " is my favourite number too!!";
```
## Basic structure
- ![[Pasted image 20250106181019.png]]
## Keywords (reserved words)
- can't change the keywords 
- cpp - 90 keywords 
- java - 50
- c - 32
- python - 33
- ![[Pasted image 20250106181132.png]]
- most used 
	- int 
	- return
- main , std, cout, cin - not keywords -> "Identifiers"
- +,-, * , / , :: -> operators
-  ; at the end , { } -> punctuation of cpp
## Preprocessor 
- processes the source code before the compiler sees it
- 1. strips comments and replaces with single space
- 2. looks for preprocessor directives(that start with #) and executes them
- ![[Pasted image 20250106181654.png]]
- it just makes the code ready for the compiler
## Comments
- compiler never sees comments
- two types 
```cpp
// single line comment
 int i=0; // integer i
 
 /* multi 
    line 
 comment*/

/*******************************
    mostly used at 
    the top of the code
    * 11/12/2024 bug fixed  -> don't do this , use version control system
********************************/
```
## main()
- must always return integer (doesn't matter which one)
- ![[Pasted image 20250106182946.png]]
- 2nd typa main is used in command line
	- argc- argument count  - no of arguments
	- char * argv [] - type of arguments -> here character array
## Namespace
- different companies can have different version of cout
```cpp
std::cout   -> standard cpp namespace cout
Frank::cout -> Frank's version of cout
```
- ![[Pasted image 20250106183520.png]]
- use namespace std -> means the entire thing is in standard cpp
	- not suitable for large codes
	- ![[Pasted image 20250106183757.png]]
- standardizing only particular ones
	- ![[Pasted image 20250106183743.png]]
## Basic input / output
- must use "iostream" to use cin and cout, cerr, clog
- ![[Pasted image 20250106183944.png]]
- ![[Pasted image 20250106184042.png]]
- ![[Pasted image 20250106184412.png]]
- ![[Pasted image 20250106184127.png]]
- You can press "Enter", "Space bar" , "Tab" to conform the input
	- if you press "space", you can enter the next input in the same cin
	- ![[Pasted image 20250106184841.png]]
	- the no of "spaces" doesn't matter, just the stream, only if the data type is same(both r int), 
	- if one of it is double or something , it won't work "normally"
	- ![[Pasted image 20250106185130.png]]
	- ![[Pasted image 20250106201613.png]]
```cpp
void date_of_birth() {
    int m {};       // initialize value inside?
    int d {};
    int y {};
```
Q.  guess the output  ???
![[Pasted image 20250402134742.png]]
## Variables and Constants
- ![[Pasted image 20250106202410.png]]
- here, since the memory location has named as "age" we don't have to bother about the memory location no.
	- ![[Pasted image 20250106202702.png]]
- ![[Pasted image 20250106202742.png]]
- ![[Pasted image 20250106202950.png]]
- ![[Pasted image 20250106203007.png]]
- ![[Pasted image 20250106203055.png]]
- use any one way , but only one
	- ![[Pasted image 20250106203211.png]]
- initialize
	- ![[Pasted image 20250106203310.png]]
	- {21} ->most recommended;

> [!Always initialzie a variable, atleast with zero ]
> - int i {0};   -> initialization style 
> - i=10;       -> assignment style
### Global variables
- accessed from any part of the code 
	- so can be changed from any part of the code (debugging difficult)
- are automatically initialized to zero
## Data Types
- Primitive
	- Char                - single ' '
	- Int
		- signed and unsigned
	- Floating
	- Boolean
- Size and precision (of datatypes) depend on compiler
	- ![[Pasted image 20250106204809.png]]
- Int
	- ![[Pasted image 20250106205012.png]]
	- unsigned keyword is needed for unsigned int
	- ![[Pasted image 20250106205217.png]]
- Char
	- ![[Pasted image 20250106205055.png]]
- Float
	- ![[Pasted image 20250106205321.png]]
- Bool
	- 8 bits
- ![[Pasted image 20250107133715.png]]
```cpp
long people{7'000'000};      // '  to represent , in numbers
```
- ![[Pasted image 20250107134809.png]]
## Sizeof
- ![[Pasted image 20250107135007.png]]
-  the two directives need for this are
	- ![[Pasted image 20250107135052.png]]
	- ![[Pasted image 20250107135220.png]]
	- ![[Pasted image 20250107135329.png]]
## Constants
- values can't change once declared
- make a variable if a no. is gonna be used again and again
	- ex : pi, months in a year(12)
- Types of constants
	- Literal Constants
		- ![[Pasted image 20250107155357.png]]
		- ![[Pasted image 20250107155430.png]]
		- ![[Pasted image 20250107155502.png]]
		- ![[Pasted image 20250107155523.png]]
	- Declared Const
		- const keyword
		- try to change the value of declared const -> compiler gives error
		- ![[Pasted image 20250107155629.png]]
	- Constant Expressions
		- constexpr keyword
	- Enumerated const
		- enum keyword
	- Defined const
		- #define
		- ![[Pasted image 20250107155715.png]]
		- dont use them, not recommended
- Refactor - not change the code but improve it (by assigning some variables to consts, like pi to 3.014 etc)
	- easier to read 
	- improved
	- duplication of code is removed
