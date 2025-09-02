- needs two arrays
- Merging - can only be done on sorted arrays
	- Append- same array is updated
	- Concat - into same or other array
	- Compare
	- Copy
- for merging we def need 3rd array
- whatever element is smaller from A/ B copy it and move the pointer to next element
- if an array is over, copy all the elements from the second as it is(since both r already sorted)
```cpp
i = 0;
j = 0;
k = 0;
while (i < m && j < n) {
    if (A[i] < B[j])
        C[k++] = A[i++];
    else
        C[k++] = B[j++];
}
for (; i < m; i++)
    C[k++] = A[i];

for (; j < n; j++)
    C[k++] = B[j];
```
	 TC:ʘ(m+n)

> [!NOTE]
> - go through the code once 
# Set Operations
- 4
	- Union
	- Intersection
	- Difference
	- Set Membership - searching
## Union
- if array is not sorted
	- copy first array as it is
	- from second ,see if the element is already present, if yes? don't copy, if no? copy it
	- TC:O(m*n)
- if sorted arrays
	- merging
	- TC:O(m+n) -> O(n)
## Intersection
- if arrays r unsorted
	- check first element in second array, if present ? copy in third array
	- TC:O(m*n)
- if arrays r sorted
	- similar to merging
	- TC:O(m+n) -> O(n)
## Difference
- if arrays r unsorted
	- check first element in B , if not present in B? copy in third array
	- TC:O(m*n)
- if arrays r sorted
	- similar to merging
	- TC:O(m+n) -> O(n
	