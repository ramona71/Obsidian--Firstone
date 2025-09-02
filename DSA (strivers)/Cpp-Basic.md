 - 3 5 boxes
```cpp
int arr[3][5];  
// to get length
arr.size();
```
![[Pasted image 20250108163441.png]]
-  String stores char like Arrays , using index
- initialize i outside for loop, so if we have to print it, we can later
```cpp
int i;
for(i=0, ---meh---){
	some shit
}
cout<< i;              // can't print 'i', if you did for(int i=0)
 ```
 - do while - the first time the code block gets executed irrespectively
 ```cpp
 do{
	 cout <<"The no"<< i<<endl;
	 i=i+1;
	 } while(i<=0);

cout<< i<<endl;                      // guess the output
//remember the syntax too, just the basic syntax
```
# Functions that exist in cpp
- inbuilt
```cpp
max();
```
# Pass by val and reference
- for pass by reference , just put & at the end
```cpp
void max ( int &num)           // that's it
```

> [!NOTE] Array always pass by referece
> NO need to put & before array
> vector , maps , list -> put '&' manually

# Cpp STL
- most of the libraries are already present in bits library
```cpp
#include<bits/stdc++.h>             // contains all

//else
#include<iostream>
#include<math.h>
#include<vector>
	#include<string>          and so on , gotta write all of them manually
```
- cpp STL divided into 4 parts
	- Algorithms
	- Containers
	- Fxns
	- Iterators
### pairs
- part of utility library?
- do mfrs even use pairs??? dk tf
```cpp
	pair<int, int> p= {1,3};
    cout<<p.first <<" "<< p.second;
  
    pair<int, pair<int, int> > q = {1,{2,3}};
    cout<< q.first<< " "<< q.second.second <<" "<< q.second.first;
  
    pair<int,int> arr[]={ {1,2},{5,6},{9,7}};
    cout<< arr[0].second;
    cout<<arr[1].first;
```
## Vectors
- used when we don't know the size of data structure, (use array when you know the size)
- push_back - copies element inside the vector
	- for primitive data types
- emplace_back- constructs the obj inside vector
	- for complex/ custom data types
```cpp
#include<vector>              //never forget this dawgggg
using namespace std;
int main(){
    vector<int> v;
    v.push_back(1);
    v.emplace_back(2);         // emplace back faster that push back?
  
    vector<pair <int ,int>> vec;
    vec.push_back({1,2});
    vec.emplace_back(4,5);       // difference in syntax
  
    vector<int> v(5,200);        // container with 5 instances of 200 {200,200,200,200,200}
    vector<int> v(4,20);         // 4 instances of 20
    vector<int> v1(5);           // 5 instances of garbage or 0
    vector<int> v2(v1);          //copy
  
    vector<int> v3(5);           // can increase size with pushback later
```
- access
```cpp
cout<< v[0] << v.at(0);            // can use both to access, difference is in bound checking
cout<< v.back();                   // last element
```
## Iterators
- Iterators- holds on to the 'memory' of first element in the vector
	- to print element in that memory address use ' * ' like in pointers
```cpp
vector<int> v={1,2,3,5,4,6};
    vector<int> :: iterator itera= v.begin();         // stores address of first element
    itera++;
    cout<< *(itera);               // prints element in that memory address
  
    itera = itera +2;
    cout<< *(itera);
```
- in iterators
	- v. begin ( ) - points to first element ( like index 0)
	- v. end( )   - points to space after last elements (index 'n', but last element exist at n-1) just like in arrays
	- v.rend( )- points to -1 in arrays
	- v. rbegin() - points to last elements (n-1)
		-  moves in reverse way
		- iter ++ and it goes to n-2
		- iter ++ to n-3
```cpp
    vector<int> ::iterator itera = v.begin();
    vector<int> ::iterator itera2 = v.end();
    vector<int> ::iterator itera3= v.rend();
    vector<int> ::iterator itera4= v.rbegin();
```
-  auto - automatically assigned type without mentioning
```cpp
int a =5;
auto a=5;       // same shit
auto a="raj";
```
# Access elements of vectors
- to access elements of vectors
	- 1 loop
	- 2 iterators
```cpp
	for( vector<int> :: iterator it =v.begin(); it!=v.end(); it++){
	        cout<< *(it);
	}
    for(auto it= v.begin(); it!= v.end(); it++) {             //makes it simple
        cout<< *(it);        // difference from below
    }
    for( auto it: v){
        cout<< it;           //change from above
    }
```
- deletion
	- `erase()` is used in two ways
		- single element  `erase(index)`
		- start to end `erase(start_index, end_index)`
			- start is included and end is excluded
```cpp
v.erase(v.begin()+1);   // {10,20,30} -> {10,30}
v.erase(v.begin()+2, v.begin()+4);  //{10,20,30,40,50}-> {10,20,50}
```
# Insertion in vectors
- two types
	- `insert(index, element)`
	- `insert(start_index,no.of elements, element)`
```cpp
vector<int> vec(2,100);         // {100,100}
v.insert(vec.begin(), 30);      // {30,100,100}
v.insert(vec.begin()+1, 2,10);  // {30,10,10,100,100}

// copy a vector into another vector
vector<int> vec2(2,40);          // {40,40}
vec2.insert(vec2.begin(), vec.begin(), vec.end());
//vec2= {30, 10, 10, 100, 100, 40, 40}
```
- other fxns of vectors
```cpp

// (10, 20)
cout << v.size(); // 2
//(10, 20)
v.pop_back(); // (10)
// v1-> (10, 20)
// V2->{30,40}
(30, 40)
v1.swap(v2); // v1 (30, 40), v2 (10, 20)
v.clear(); // erases the entire vector

cout << v.empty();   // true-> if vector is empty,false->if a single element
```
# List
- similar to vector
-  `insert` in vector is costly, compared to `push_front` in list(better use this)
	- insert ->  linked list
	- push_front-> singlydoubly LL 
- other fxns are similar to vector
```cpp
void explainList() { 
	list<int> ls;
	ls.push_back(2); // {2}
	1s.emplace_back (4); // {2,4}
	
	ls.push_front(5);  // {5,2,4}    // similar to insert , but less constly
	1s.emplace_front(); // {2, 4};   
// rest functions same as vector
// begin, end, rbegin, rend, clear, insert, size, swap
```
# Deque
- similar to list and vector
```cpp
void explainDeque()) {
	deque<int>dq;
	dq.push_back(1); // (1)
	dq.emplace_back(2); // (1, 2) 
	dq.push_front(4); // (4, 1, 2) 
	dq.emplace_front (3); // (3, 4, 1, 2)
	dq.pop_back(); // (3, 4, 1) 
	dq.pop_front(); // (4, 1)
	dq.back();
	dq.front();
// rest functions same as vector
// begin, end, rbegin, rend, clear, insert, size, swap
```
# Stack
- lifo - last in first out
- `emplace` is similar to `push` here
- no index here
- only 3 fxn here  , all r TC - O(1)
	- top
	- push 
	- pop
```cpp
void explainStack() { 
	Stack<int> st; 
	st.push(1); // (1)
	st.push(2); // (2, 1)
	st.push(3); // (3, 2, 1) 
	st.push(3); // (3, 3, 2, 1)
	st.emplace(5); // (5, 3, 3, 2, 1)
	cout<st.top();// prints 5
	st.pop(); // st looks like (3, 3, 2, 1)
	cout<<st.top(); // 3
	cout << st.size(); // 4
	cout<< st.empty();    // true or false
	
	stack<int>st1, st2; 
	stl.swap(st2);
}
```
# Queue
- fifo - first in first out
```cpp

void explainQueue() { 
	queue<int> q; 
	q.push(1);        // (1) 
	q.push(2);        // (1, 2) 
	q.emplace(4);     // {1, 2, 4)
	q.back() +=5;     
	cout << q.back(); // prints 9     // Q is (1, 2, 9)
	cout<<< q.front(); // prints 1
	q.pop();           // (2, 9)      // fifo             
	cout<<< q.front(); // prints 2
	// size swap empty same as stack
}
```
# Priority Queue
- largest value at the top (front)
- tree data structure
- top - > TC : O(1)
- push- > TC : O(log n)
- pop - > TC : O(log n)
```cpp

void explainPO() { 
	priority_queue<int>pq;
	pq.push(5);             // (5) 
	pq.push(2);             // (5, 2) 
	pq.push(8);             // (8, 5, 2) 
	pq.emplace(10);         // (10, 8, 5, 2)
	cout << pq.top();       // prints 10
	pq.pop();               // (8, 5, 2)
	cout<<< pq.top();       // prints 8
	// size, swap, empty function same as others
	
	// Minimum Heap
	priority queue<int, vector<int>, greater<int>> pq; 
	pq.push(5); // (5)
	pq.push(2); // (2, 5)
	pq.push(8); // (2, 5, 8)
	pq.emplace(10); // (2, 5, 8, 10)
	cout << pq.top(); // prints 2
```
# Set
- stores everything in
	- sorted order
	- unique
- every fxn is TC : O(n)  , insert or erase , everything in O(n)
```cpp

void explainSet() { set<int>st;
	st.insert(1);     // {1} 
	st.emplace(2);    // (1, 2) 
	st.insert(2);     // {1, 2} 
	st.insert(4);     // {1, 2, 4}
	st.insert(3);     // (1, 2, 3, 4)
	
	// begin(), end(), rbegin(), rend(), size(),
	//empty() and swap() are same as those of above
	 
	// (1, 2, 3, 4, 5)
	auto it= st.find(3);      // returns and iterator points to 3
	// (1, 2, 3, 4, 5)
	auto it= st.find(6);      
	// element not in set, so returns st.end() out of bounds
	
	st.erase(5); // erases 5            // takes logarithmic time
	st.erase(it1); // erases iterator   // takes constant time
	st.erase(it1, it2);  // erase from (first ,last)
	
}
```
- look up find( )- > don't understand this at all
```cpp
int cnt= st.count(5) ;       // if 5 exist, returns 1 else 0
```
# Binary search
`binary_search(start, end, element_to_search)`
- searches for element in start to end index
- return 'boolean'
```cpp
bool res= binary_search(a,a+n,3)           
// from index a to a+n(end) searches for 3
```
# Multi Set
- sorted
- but not unique, can repeat
	-  ex: {1,1,1}
- if you use `erase` all the occurences get's erased
- so find the first occurence and delete it , if you want to delete a single occurence of a no.
```cpp
```
# Unsorted set
- unique
- not sorted
- most used cuz all operations are TC: O(1)
	- worst case sometimes is TC : O(n)
```cpp
unordered set<int> st;
```
# Map
- like python dictionary
- keys  (unique)
- values (can have duplicates)
```cpp
map<int,int> mpp;         // first int-> key, second int->value
map<int, pair<int,int>> mpp;     // key is int , val is pair
map<pair<int,int>, int> mpp;     // val is pair, val is int

//insert into map
map[1]= 2;
mmp.emplace({3,1});
mmp.insert({2,4});         // all r same
mmp({2,3})= 10;            // key is {2,3}
```
![[Pasted image 20250120180801.png]]
![[Pasted image 20250120180846.png]]
- map stored unique keys in sorted order  ( same as set )
- so the above insertion are stored as
	- {  {1,2},  {2,4}, {3,1} }
- for iteration
	- either go by key values
	- iterator (best option)
```cpp
for(auto it: mmp){
	cout<< it.first()<< " "<< it.second()<<endl;
}
// accessing
mmp[2]     // gives 4
mmp[5]     // either null or 0

auto it= mmp.find(3);     // key 
cout<< *(it).second;      //it's value

auto it= mmp.find(5);     // points to .end() -> after the map, (n in array)
auto it=mpp.lower_bound(2);
auto it=mmp.upper_bound(3);
// erase, swap, size , empty are all same as above
```
# MultiMap
- can store duplicate keys
- sorted order
# Unordered map
- unique keys
- not sorted
- ADV
	- map-> O(log n)
	- unordered map -> O(1)     , worst worst case O(n)
# Lower n upper bound
- lower_bound returns iterator pointing to the index of found no.
- if we want the index, subtract a from it
- if element not found , return iterator pointing to the next element
	- ![[Pasted image 20250120212704.png]]
- upper_bound , always returns iterator pointing to next element
- to get the index, subtract the first index
	- ![[Pasted image 20250120212832.png]]
	- ![[Pasted image 20250122143931.png]]
- some questions
	- 1 , easy binary search
	- ![[Pasted image 20250122144525.png]]
	- 2 
	- ![[Pasted image 20250122144551.png]]
	- 3
	- ![[Pasted image 20250122144607.png]]
	- 4
	- ![[Pasted image 20250122144624.png]]
	- 5
	- ![[Pasted image 20250122144637.png]]
```cpp
```
