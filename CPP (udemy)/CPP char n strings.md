- use cpp strings in cpp (duh)
- cpp strings r cpp objects
- `<cctype>`  -> for char fxns
	- for testing
	![[Pasted image 20250308155546.png]]
	- for conversion
	![[Pasted image 20250308155616.png]]
## C-style strings
`<cstring>    <cctype>   <cstdlib>`
- C-style string
	- array of `char`
	- ends with `null`
- String literal
	- "frank"
	- constant - can't be change
	- ends with `null` (automatically put at the end)
- ex
	![[Pasted image 20250308160610.png]]
	problem cuz the string won't be null terminated anymore (but compiles fine)
	- ex
	![[Pasted image 20250308160652.png]]
- can't assign a string literal to a c-style string  -> error 
```cpp
char my_name [8];
my_name= "Frank";              // gives error
//do
strcpy(my_name, "Frank");      // string copy fxn
```
- better to use fxn for strings, to concatenate, copy, assign etc
	- `<cstring>`   -> include
	- some fxns
	![[Pasted image 20250308161100.png]]
- `<cstdlib>`  converts c-style strings to int/ float/ long etc
