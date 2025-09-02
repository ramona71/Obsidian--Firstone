- vector size
	- `v.size();`
	- if v= {10,20,30} returns 3
- string size
	- `s.size();`
# max and min element
- returns max element
- *  so it returns the element n not the iterator
```cpp
int maxi = *max_element(a,a+n);
int mini= *min_element(a,a+n);
```
# Strings

- to remove uppercase and characters n punctuation from a string
```cpp
#include <iostream>

int main() {
    std::string input = "Hello, World! 123";

    std::cout << "Original String: " << input << "\n";
    std::cout << "To Lowercase: " << toLowerCase(input) << "\n";
    std::cout << "To Uppercase: " << toUpperCase(input) << "\n";
    std::cout << "Remove Characters (e,o,!): " << removeCharacters(input, "eo!") << "\n";
    std::cout << "Remove Whitespaces: " << removeWhitespace(input) << "\n";
    std::cout << "Remove Punctuation: " << removePunctuation(input) << "\n";
    std::cout << "Toggle Case: " << toggleCase(input) << "\n";

    return 0;
}
```
## Alpha numeric or not
- A- Z , a-z and 0-9 then alpha numeric
```cpp
isalum('j')   // returns true cuz it is
```
or the fxn is
```cpp
if ((ch >= 'A' && ch <= 'Z') || (ch >= 'a' && ch <= 'z') || (ch >= '0' && ch <= '9')) 
	{ // Character is alphanumeric }
```
# Reverse an array
![[Pasted image 20250120165929.png]]
# Binary Search
```cpp
A[]= {1,4,5,8,9}
bool res= binary_search(a, a+n,3);        // checks 3 in the array 
```
# sort
```cpp
sort(a,a+4)
```
- a-> starting iterator
- a+4 -> end iterator(not included)
- a can start from 0 , or some value like n/2 , if you want the elements after 
- some standard ways of sorting are below
```cpp
sort(a,a+4);
sort(v.start(),v.end());

sort(a+2, a+4);

sort(a,a+n, greater<int>);    // to sort in descending order
```
- to sort in a defined way that we want
```cpp
bool comp(pair<int,int> p1, pair<int,int> p2){
	if(p1.second<p2.second) return true;
	if(p1.second>p2.second) return false;
	//if(p1.second==p2.second)    no need to write this statment
	if(p1.first>p2.first)  return true;
	else return false;
}

pair<int, int> a[] = {{1,2}, {2, 1}, {4, 1}};
// sort it according to second element
// if second element is same, then sort it according to first element but in descending
sort(a, a+n, comp);         // comp is self written comparator(fxn)
// (4,1), (2, 1), (1, 2));
```
# return binary of a number
```cpp

int num = 7;
int cnt =__builtin_popcount();      // 7-> 111  // returns 3, cuz there r three '1's  if 
int num = 6;
int cnt =__builtin_popcount();      // 6 ->110  // returns 2

long long num= 165786578687; 
int cnt =_builtin_popcountll();    // changes a little for long long

```
# All permutations of a string
- prints all permutations in a sorted manner
	- if you start from 123
		- 123 -> 132 -> 213 ->231 ->312 -> 321  -> false
	- if you start from 213
		- 213 ->231 ->312 -> 321  -> false
- so always start from beginning if you want all permutations
- return false if there are none anymore
- 
```cpp
string s = "123";
do {
  cout << s <<< endl;
} while (next_permutation (s.begin(), s.end()));
```
