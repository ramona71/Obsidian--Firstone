#### Selection Statements
- if - else ( nested) statement
- switch statement
- conditional operator ?:
#### Iteration
- for loop  - range based  
- while loop
- do- while loop
- (infinite/ nested) 
- ( continue/ break)
# if statement
- indentation (space) is for us, compiler don't gaf
```cpp
if(condn) :
  statement ;             // easy to read
  
if (condn): statement;      // works the same
```
- draw to flow chart to understand it better
	- ![[Pasted image 20250107172549.png]]
	- ![[Pasted image 20250107184614.png]]
	- ![[Pasted image 20250107185549.png]]
- if you declare a variable inside if block, you can't use it outside
	- here "diff" can only be accessed inside
	- ![[Pasted image 20250107183738.png]]
- The `else` at the end of an `if-else` statement is **not mandatory** in C++. You can use a single `if` or an `if-else` without ending it with an `else`.
```cpp
#include <iostream>
using namespace std;
int main() {
    int score {};     // initialize with 0 
    cout << "Enter your score on the exam (0-100) : ";
    cin >> score;
    char letter_grade {};       // initialize empty
    if (score >= 0 && score <=100) {
        if (score >= 90)
            letter_grade = 'A';
        else if (score >= 80)
            letter_grade = 'B';
        else if (score >= 70)
            letter_grade = 'C';
        else if (score >=60)
            letter_grade = 'D';
        else
            letter_grade = 'F';
        cout << "Your grade is : " << letter_grade << endl;
        if (letter_grade == 'F')
            cout << "Sorry, you must repeat the class" << endl;
        else
            cout << "Congrats!" << endl;
  
    } else {
        cout << "Sorry, " << score << " is not in range" << endl;
    }
    cout  << endl;
    return 0;
}
```
# switch statement
 - `default` executes when none of then are true
	 - if one of them is true, it executes and breaks out of switch(only if `break` is written)
	 - ![[Pasted image 20250107203505.png]]
- once match is made, the code executes until `break` statement is executed
	- ![[Pasted image 20250107203922.png]]
# Conditional operator (ternary operator)
- ternary operator-> operates on 3 operands
- a = `(cond expression) ? expr1 : expr2`
- don't nest ts
![[Pasted image 20250402134252.png]]
- instead of all this
	- ![[Pasted image 20250402134441.png]]
	- just do
	- ![[Pasted image 20250402134456.png]]
- 