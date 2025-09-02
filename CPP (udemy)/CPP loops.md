- looping / iteration/ repetition
- loops
	- 1. loop condn
	- 2. loop body
- types
	- specific no of times
	- each element in collection
	- forever (infinite)
	- till a condn becomes true/ false
# Types
1. for loop
	1. specific no of times
2. range based for loop
	1. one iteration for each element in range/ collection
3. while
	1. checks condn at beginning
	2. runs as long as condn is true
4. do-while
	1. check condn at the end
# for loop
- `for(initiaize ; condn ; increment ){ statements }  `
- `;` is required 
-  statements & expressions -> optional
- ![[Pasted image 20250402143533.png]]
- endless loop
```cpp
for(;;){
	cout<< "Endless loop"<<endl;
}

// don't have to use { } if there is only one statement inside for loop
for(;;)
	cout<< "Endless loop"<<endl;     // this work just as fine
```
- initialization
	- ![[Pasted image 20250622113458.png]]
	- ![[Pasted image 20250622113621.png]]
	- `,` associativity -> right to left, so the output is left most operator
- try to simplify the code, in one line
	- EX: print 10 no in a row and start new row for the next 10 nos, so instead of
	- ![[Pasted image 20250622114531.png]]
	- just do
	- ![[Pasted image 20250622114454.png]]
	- the result will be
	- ![[Pasted image 20250622114641.png]]
# Range based for loop
- for collection of items
- don't have to bother about it's length or indexes
```cpp
for(var_type var_name: sequence) 
	statements
```
- // ex
```cpp
int mark_list [] {90,85,95};
for(int marks :mark_list)
	cout<<marks<<endl;
```
- don't even have to provide var_type  -> use auto
```cpp
for(auto marks :mark_list)     // compiler figures out the type
```
- to calculate sum of array elements
	- ![[Pasted image 20250622115710.png]]
	- or if the elements are known
	- ![[Pasted image 20250622115654.png]]
- can iterate over string
	- ![[Pasted image 20250622120000.png]]
# While loop
- pretest loop - test is done in the beginning , and if that fails it never executes the body 
	- opposite is do while
```cpp
while(expression){    // expression should evalutate to true
	statement
}
```
- loops can be great to validate the input
	- below code won't loop out unless valid input is entered
	- ![[Pasted image 20250622121927.png]]
	- or use boolean
	- ![[Pasted image 20250622122033.png]]
- 

```cpp
```