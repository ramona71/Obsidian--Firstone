- Recursive fxn- a fxn which calls itself (there must be a base condn that terminates the recursion)
```cpp
type fun(parameter)
{
	if (base condn)
	{
		fun(parameter)
	}
}
```
- recursive functions are traced in a tree (ref note )
- Recursion in two stages
	- Ascending
	- Descending
- loops has only ascending phase
```cpp
void fxn(int n){
	if(n>0){
	1. calling time     // Asc
	2. fxn(n-1)  *2     // Any computations following this occur at returning time
	3. returning time   //Desc
	4. }
}
```
	TC:O(n)
- Recursive functions are memory consuming fxns (uses stack)
	- ![[Pasted image 20241018195251.png]]