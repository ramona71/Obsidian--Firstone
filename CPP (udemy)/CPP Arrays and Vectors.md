- Vectors are better than arrays
- Compound data types (not primitive)
## Arrays
- collection of elements
	- ![[Pasted image 20250106210102.png]]
	- if you go out of bounds, program ->crash
- Declaration
	- ![[Pasted image 20250106210327.png]]
- Initialization
	- ![[Pasted image 20250106210423.png]]
	- int test_scores [5] { };   ->init all to zero
	-  int test_scores [5] {0};   ->init all to zero
	- int test_scores [5] {100}; -> only first one to 100
- Access
	-  arrayName[0];        
- array name without index returns the address
```cpp
cout<< "Array adress will be printed out" << testScores <<endl;
```
- multi dimensional arrays
	- ![[Pasted image 20250106223132.png]]
- ![[Pasted image 20250107210038.png]]
## Vectors
- Arrays- fixed in size (static)
- Vectors  -> *Objects*
	- (dynamic)
	- CPP object
	- container in Cpp standard template library
	- array can grow and shrink in size at execution
	- bounds checking
	- sort, reverse, find etc
	- elements automatically initialized to zero instead of garbage
	- ![[Pasted image 20250106224102.png]]
- Declaration
```cpp
# include <vector>           -> library
vector<char> vowels;
vector<int> testScores (10);    // constructor initialization (can do cuz it's obj)
```
- Initialization
```cpp
vector <char> vowels {'a', 'e', 'i', 'o', 'u' };
vector<int> test_scores {100, 98, 89, 85, 93};
vector <double> hi_temperatures (365, 80.0);   // 365 doubles declared as 80.0
```
- Accessing - just like arrays
```cpp
vectorName[index];   // [] so no bounds checking will be done (do it urself)
testScores[1];
```
- Accessing - vector method
	- .at fxn  - bounds checking
	- ![[Pasted image 20250106224519.png]]
- size increase
	- the element pushed back has to be of same type
	- ![[Pasted image 20250106224754.png]]
- Bounds checking
	- ![[Pasted image 20250107164600.png]]
	- the program throws the error but better to do exception handling that to depend on the compiler (so the code won't crash)
```cpp
#include<iostream>
#include<vector>        // don't forget this!!!!!
using namespace std;
int main(){
    // vector<char> vowels;      // empty
    // vector<char> vowels {5};  // 5 initialized to 0
    vector<char> vowels {'a','e','i','o','u'};
  
    // ARRAY SYNTAX
    cout<<vowels[0]<<endl;
    cout<<vowels[4]<<endl;   // no bounds checking, will crash without warning
  
    // vector<int> testScores(3);        // 3, all initialized to 0
    // vector<int> testScores(3,100);    // 3, all initialized to 100
      vector<int> testScores{100,98,99};
  
    //VECTOR SYNTAX
    cout<<testScores.at(0)<<endl;
    cout<<testScores.at(1)<<endl;
    cout<<testScores.at(2)<<endl;       // bounds checked
    //cout<<testScores.at(3);     // this crashes code, but with warning
  
    cout<<"Elements in vector: " << testScores.size()<<endl;     // gives no of elements in vector

    // DYNAMIC NATURE OF VECTOR
    cout<<"Enter a test score to add:";
    int toAdd{0};
    cin>>toAdd;
    testScores.push_back(toAdd);
    cout<<"Another test score to add??:";
    cin>>toAdd;
    testScores.push_back(toAdd);
  
    cout<<"Test scores now are: "<<endl;
    cout<<testScores.at(0)<<endl;
    cout<<testScores.at(1)<<endl;
    cout<<testScores.at(2)<<endl;
    cout<<testScores.at(3)<<endl;
    cout<<testScores.at(4)<<endl;
    // cout<<testScores.at(5)<<endl;   //crashes but the code runs, with warning
    cout<<"Elements in vector: " << testScores.size()<<endl;
  
    return 0;
}
```
### Multi dimensional vector
- vector inside vector
```cpp
vector <vector<int>> movie_ratings{
        {1,2,3,4},
        {5,6,7,8},
        {9,10,11,12}
    };
    cout << "\nHere are the movie rating for reviewer #1 using array syntax :"<< endl;
    cout << movie_ratings[0][0] << endl;
    cout << movie_ratings[0][1] << endl;
    cout << movie_ratings[0][2] << endl;
    cout << movie_ratings[0][3] << endl;
  
    cout << "\nHere are the movie rating for reviewer #1 using vector syntax :" << endl;
    cout << movie_ratings.at(0).at(0) << endl;
    cout << movie_ratings.at(0).at(1) << endl;
    cout << movie_ratings.at(0).at(2) << endl;
    cout << movie_ratings.at(0).at(3) << endl;
```
## Differences between Arrays n Vectors
- Differences between sizeof( ) n size( )
	- ![[Pasted image 20250107165921.png]]
```cpp
vector<int> vec{10,20,30,40,50};
// don't mention size -> gives error
vector<int> [5] vec{10,20,30,40,50};     // error
```
- Q 
	- ![[Pasted image 20250107205540.png]]
- Ans : nothing changed in vector 2d
```cpp
#include<iostream>
#include<vector>     // most important part
using namespace std;

int main(){
    vector<int> vector1{};
    vector<int> vector2{};

    vector1.push_back(10);
    vector1.push_back(20);
    cout<<vector1.at(0)<<endl;
    cout<<vector1.at(1)<<endl;
    cout<<vector1.size()<<endl;

    vector2.push_back(100);
    vector2.push_back(200);
    cout<<vector2.at(0)<<endl;
    cout<<vector2.at(1)<<endl;
    cout<<vector2.size()<<endl;

    vector < vector<int> > vector_2d {};      // vector 2d
    vector_2d.push_back(vector1);
    vector_2d.push_back(vector2);

    cout<<vector_2d.at(0).at(0)<<endl;
    cout<<vector_2d.at(0).at(1)<<endl;
    cout<<vector_2d.at(1).at(0)<<endl;
    cout<<vector_2d.at(1).at(1)<<endl;

    vector1.at(0)=1000;
    cout<<vector1.at(0)<<endl;
    cout<<vector1.at(1)<<endl;

    cout<<vector_2d.at(0).at(0)<<endl;
    cout<<vector_2d.at(0).at(1)<<endl;
    cout<<vector_2d.at(1).at(0)<<endl;
    cout<<vector_2d.at(1).at(1)<<endl;

    return 0;
}
```
- nums.size() -> of vector , returns unsigned int