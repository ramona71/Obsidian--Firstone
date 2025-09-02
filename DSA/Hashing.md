- TC: O(1)
- Linear search - unsorted list works
- Binary search- to less TC( log n) , needs sorted list (takes extra effort)
## Hashing Techniques
- Hash function   $h(x)=x$
- Fxn supports two types of mapping
	- one to one
	- many to one
### Ideal hashing
- put the element in the same index
	- put 8 in index 8
	- put 35 in index 35
- Advantages
	- fastest searching
- Disadvantages
	- array size is more
		- 5 ,200 are elements, array size will be 201 (2 elements, 201 array size) (waste of memory)
	![[Pasted image 20241016132026.png]]
### Modulus hash function
- hash function is changed       h(x)= x%10
	![[Pasted image 20241016133834.png]]
- Disadvantages
	- if we have 25, since 15 is already there, we can't map it- collision
- collision occurs if we try to modify the ideal hash function
#### To resolve collision
- open hashing- we will consume extra space , more than hash table
	- chaining
- closed hashing- not increase the size of hash table, utilize whatever is there
	- open addressing - store in other address, which is not given by hash fxn
		- Linear Probing
		- Quadratic Probing
		- Double Hashing

## Chaining  - Open hashing
- 