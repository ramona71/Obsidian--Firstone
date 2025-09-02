- Standard Template Library (LIBRARY!!)- set of container, iterators and algos
- library for generic class and fxns (templates)
- has
1. Containers
	1. array, vectors, deque, stack , set , map etc
2. Algos
	1. fxns for processing elements from containers
	2. find, max, count, sort etc
	3. has 60 algos
3. Iterators
	1. generate sequence of element from containers
	2. forward, reverse, by value , by reference , constant etc
- all three are created seperately but work together perfectly

> [!NOTE] Use headers !!! to use STL
> `#include<vector>`
> `#include<algorithm>`
- `sort(v.begin(), v.end()) `- >entire vector/ any STL
	- can sort a part of vector too (subset of vector)
- `reverse(v.begin(), v.end())`
- range based `for` loop is an iterator
- double sum = `accumulate(v.begin(), v.end(), 0.0)`
	- the starting sum is 0.0
# Types of containers
1. Sequence  - all elmts stored in seq
	1. array, vector, list , forward_list, deque
2. Associative -  no order  / pre defined order
	1. set, multi set, map (dict), multi map
3. Container adapters - doesn't support iterators -> can't use with other STL algos
	1. stack , queue, priority queue

![[Pasted image 20250402152731.png]]
- 60 algos 
	- non modifying algos
	- modifying algos
# Generic Programming (Templates)
- Macros - work with any types of arguments 
- CCP- static -> needs the type of variable written , so need templates