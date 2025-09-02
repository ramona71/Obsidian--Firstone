All operations
- Display()
- Add(x) / Append(x)
- Insert(index, x)
- Delete(index)
- Search(x)
- Get(index)
- Set(index ,x)
- Max()/ Min()
- Reverse()
- Shift()/ Rotate()

## Display()

```cpp
for(int i=0;i<A.length;i++){
	print A[i];
}
```
	TC: O(n)
## Add(x) / Append(x)        
- at the end
```cpp
A[length] = x;
length++;
// code
void Append(struct Array *ar,int x){
    if(ar->length<ar->size){
        ar->A[ar->length]=x;
        ar->length++;
   }
}
Append(&arr,15);
```
	TC : O(1)

- if we do pass by value, it modifies a copy of length and not the original array
```cpp
void Append(struct Array ar, int x) {
    if(ar.length < ar.size) {
        ar.A[ar.length] = x;
        ar.length++; // This modifies a copy of length, not the original
    }
}
```
## Insert(index ,x)    
- first check if index is valid (index shouldn't be out of range)
- also if index is greater than len, then we don't have to shift at all, can just insert
```cpp
	for (int i=length; i>index;i--){
		A[i]=A[i-1];
	}
	A[index]= x;
	length++;
```
	TC: O(n)
## Delete(index)
- step 1 : index shouldn't be out of range
- never leave blank space in array after deleting, always shift the elements
```cpp
x=A[index];
for( int i=index; i<length-1;i++){
	A[i]=A[i+1];
}
A.length--;
```
	TC: O(n)
## Linear Search(x)
- elements should be unique
- key -> value your searching
- result-> index where it's found
- if key element not found- unsuccessful search
```cpp
// pseudo code
for (i=0;i<len;i++){
	if(A[i]==key){
		return i;
		}
}
return -1;             //element not found so we return invalid index

//code
int LinearSearch(struct Array ar, int key){
    for(int i=0;i<ar.length;i++){
        if(ar.A[i]==key){
            return i;
        }
    }
 return -1;
}
```
	TC: O(n)          //worst case in successful and unsuccesful case
	Best case: O(1)   //successful case
 - it's just searching, no changes done in initial array, no need to pass the array to fxn
## Improved Linear Search(x)
#### Transposition
- key element if found, will be swapped with element before
- so if we're searching for it next time, the iterations will be less
```cpp
// pseudo code
for (i=0;i<len;i++){
	if(A[i]==key){
		swap(A[i],A[i-1]);
		return i-1;
		}
}
return -1;     

//code
int ImprovedLinearSearch1(struct Array *arr, int key){
    for(int i=0;i<arr->length;i++){
        if(arr->A[i]==key){
            swap(&arr->A[i],&arr->A[i-1]);
            return i-1;
        }
    }
    return -1;
}
```
	TC: O(n)       
#### Move to head
- we swap the key element in array with first element(index=0)
```cpp
// pseudo code
for (i=0;i<len;i++){
	if(A[i]==key){
		swap(A[i],A[0]);
		return 0;
		}
}
return -1;     

//code
int ImprovedLinearSearch2(struct Array *arr, int key){
    for(int i=0;i<arr->length;i++){
        if(arr->A[i]==key){
            swap(&arr->A[i],&arr->A[0]);             // this is working even if i put the & or not
            return 0;
        }
    }
    return -1;
}
```
- Array changes , so we need to pass array to fxn
## Binary Search

> [!NOTE] MAKE SURE THAT THE FUCKING ARRAY IS SORTED (for binary search only)

- list has to be sorted
- we need 3 index variables (lower, higher and mid)
		$mid = floor ( (l+h)/2)$
		![[Pasted image 20241016000938.png]]
- floor- less the integer (2.4 -> 2)
- if mid == key (element found, return index)
- if mid!= key
	- low = mid+1 
	- high= mid-1  
	- low >high   stop (search is unsuccessful)
```cpp
// pseudo code - iterative
void BinarySearch(l ,h ,key){
	while(l<h){
		mid= floor ((l+h)/2;)
		if(key==A[mid])
			return mid;
		else if(key<A[mid])
			h= mid-1;
		else 
			l=mid+1;
	}
	return -1;
}

//pseudo code - Recursive (tail recursion- uses stack so just go with loop)
void BinarySearch(l,h,key){
	if(l<h){
		mid= floor((l+h)/2);
		if(key==A[mid])
			return mid;
		else if(key<A[mid])
			BinarySearch(l, mid-1,key)
		else
			BinarySearch(mid+1, h, key)
	}
	return -1;
}

//code
int BinarySearch1(Array arr,int key){
    int l, mid, h;
    l=0;
    h=arr.length-1;
    while(l<h){
        mid=(l+h)/2;
        if(key==arr.A[mid])
            return mid;
        else if (key<arr.A[mid])
            h=mid-1;
        else
            l=mid+1;
    }
    return -1;
}
int RecBinSearch(int A[], int l, int h, int key){
    int mid;
    if (l<h){
        mid= (l+h)/2;
        if(A[mid]==key)
            return mid;
        else if(key<A[mid])
            return RecBinSearch(A,l,mid-1,key);
        else
            return RecBinSearch(A,mid+1,h,key);
    }
    return -1;
}
```
	TC : O(log2 n)         // a tree will be formed 
-    if n=16(elements)       TC: log2 16 =4
	if n=17                        TC: log2 17 =4.something = 5
	so ciel(log2 n)
## Get(index)
- see if index is valid or not
- get the element from that index
```cpp
if(index>=0 && index <length)
	return A[index];
```
	TC: O(1)
## Set(index, x)
- replace a value at particular index/ overwriting it
```cpp
if(index>=0 && index <length)
	A[index]= x;
```
	TC: O(1)
## Max()
- unsorted list- check all elements
- sorted list- last element (max)  , first element(min)
```cpp
//Max
max=A[0];
for(i=1;i<length;i++){
	if(max<A[0])
		max=A[0]
}
return max

//Min
min=A[0];
for(i=1;i<length;i++){
	if(min>A[0])
		min=A[0]
}
return min
```
	TC:(0)
## Sum()
- recursive
	![[Pasted image 20241016114410.png]]
```cpp
//iterative
int total=0;
for(i=0;i<length;i++)
	total+=A[i];
return total;

//recursive
int Sum(A,n){
	if(n<0)
		return 0;
	else
		return Sum(A,n-1)+ A[n]
}
Sum(A, length-1);      // calling

//Average
float Avg(Array arr){
    return (float)Sum(arr)/arr.length;
}
```
	  //TC:O(n)
## Reverse()
- two methods
	- take auxiliary array and copy in reverse , and copy back to original array
	- swap first and last in the same array
```cpp
//auxiliary array
for(int i=length-1,j=0; i>=0; i--,j++){
	B[j]=A[i];
}
for(int i=0;i<length;i++){
A[i]=B[i];
}

//swap
for(i=0,j=length-1; i<j; i++,j--){
temp=A[i];
A[i]=B[j];
B[j]=temp;
}

//code
void Reverse(Array *arr){
    int *B;
    int i,j;
    B=new int[20];
    for(i=arr->length-1, j=0; i>=0;i--,j++){
        B[j]=arr->A[i];
    }
    for(i=0;i<arr->length;i++){
        arr->A[i]=B[i];
    }
}
```
	TC: O(n)
## Left Shift()
- shift all elements to left hand side
- we'll loose first element
```cpp
void LeftShift(Array *arr){
    for(int i=0;i<arr->length;i++){
        arr->A[i-1]=arr->A[i];
    }
}

```
	TC: O()
## Left rotation()
- left shift but the first elements is added at all
```cpp
void LeftRotation(Array *arr){
    if(arr->length<=1)
      return;
    int temp=arr->A[0];
    for(int i=1;i<arr->length;i++){
        arr->A[i-1]=arr->A[i];
    }  
    arr->A[arr->length-1]=temp;
}
```
	TC: O()
# Into a sorted Array
- Operations
	- Insertion
	- Checking if sorted
	- Arranging all -ve elements on left side and +ve on right side
## Insertion in Sorted Array()
- we shift from last till to the element that's less or equal to the key
```cpp
x= 18;
i=lenght-1;
while(A[i]>x){
	A[i+1]=A[i];
}
A[i+1]=x;
```
	TC: O()
## Check if sorted list is sorted or not
- every no. is smaller than later element - sorted
```cpp
IsSorted(A){
	for(i=0;i<length-1;i++){
		if(A[i]>A[i+1])
			return false;
		}
	return true;
}
```
	TC: O()
## All -ve no.s to a side and +ve no.s to a side
- won't exactly be in order but just put on two different sides
- two pointers
	- i from beginning- if +ve on left , we send them to right
	- j from last- if -ve on right, send them to right
```cpp
i=0;
j=length-1;
while(i<j){
	while(A[i]<0){i++};
	while(A[j>=0]){j--};
	if(i<j)
		swap(A[i],A[j]);
}
```
	TC: O(n)

