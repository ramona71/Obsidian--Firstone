## Single missing element in sorted Array       -O(n)
- in sequence of first n natural nos- use n(n+1)/2  and find the missing one
 ![[Pasted image 20241021132546.png]]
- here n=12
```cpp
//Iteratively
for(int i=0;i<11;i++){
	sum=sum+A[i];
}
s= n*(n+1)/2;
missingno=s-sum;
```
- if sequence is not first n natural nos- we gotta know first and last number
 ![[Pasted image 20241021132902.png]]
 - diff of indices will help
	 - 6-0=6
	 - 7-1=6
	 - 8-2=6
	 - and so on
	 - 13-6=7                   not 6 so we gotta add 6 to the index 6=12 is the missing no
```cpp
diff=A[0]-0;
for(int i=0;i<n;i++){
	if(A[i]-i!=diff)
		cout<<"missing no"<<diff+i; 
}
```
## Multiple missing elements in sorted array  -O(n)
- here after finding the first missing element, we gotta update the new difference
```cpp
for(int i=0;i<n;i++){
	if(A[i]-i!=diff){
		while(diff<A[i]-i){
			cout<<"missing no"<<i+diff;
			diff++;
		}
	}
}
```
- TC is O(n)  cuz the no of missing nos is negligable  
## Missing elements in unsorted array  -O(n)
- take an array with index = max element in the unsorted array
	- if max= 12,   max index should be 0 ->12
- initialize this array with all zeros
- if element present in first array, increment zero to 1 in second array
![[Pasted image 20241021134534.png]]
- tho before method is O(n) this is faster method       (Hash table/ Bit set)
- takes a lot of space ( hashing takes a lot of space)
```cpp
for(int i=0;i<n;i++){
	H[A[i]]++;
}
for(int i=l;i<+h;i++){
	if(H[i]==0)
		cout<<"Missing no"<< i;
}
```
## Duplicate elements in sorted array - O(n)
- if i and i+1 are same, then duplicate exist (in sorted array)
- if same no is duplicated more than 2 times, makes sure it's only printed once
	- keep a last duplicate element for it
```cpp
lastDuplicate=0;
for(int i=0;i<n-1;i++){
	if(A[i]==A[i+1]&& lastDuplicate!=A[i])
		cout<<A[i];
		lastDuplicate=A[i];
}
```
- we can count the no of duplicates by another iteration
- we don't consider the loop cuz it's only a part (negligable)
```cpp
for(int i=0;i<n-1;i++){
	if(A[i]==A[i+1]){
		j=i+1;
		while(A[i]==A[i+1])j++;
		cout<<A[i]<<"Appears"<<j-i<<"Times";
		i=j-1;
		}
}
```
## Duplicates in sorted array(hash table)  - O(n)
- increment the value in hast table when an element exist
```cpp
for(int i=0;i<n;i++)
	H[A[i]]++;
for(int i=0;i<maxElement;i++)
	if(H[i]>1) 
		cout<<i<<"Appears"<<<<H[i]<<"Times";
```

## Duplicates in Unsorted Array 
- two loops, when we come across a duplicate make it -1 , so it won't appear again
	- O(n^2)
```cpp
```
## 
```cpp
```

## 
```cpp
```

## 
```cpp
```


