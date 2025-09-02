
> [!NOTE] Title
> Convert the fucking string into number if you're gonna do math with user input

- operands -> values, variables, etc
- operators ->+ - * /
* * / are done first and have same priority
- + - are done after
- from left to right ->
   2+5-3       8-3     5
- use brackets to control which  operation gets done first cuz brackets have highest priority
	 - (1+1)* 3
- remember the below would be visible only on console
```js
let student=4;
student+=5;
console.log(student);
```
- main operators
```js
let stu=4;
stu+=5;
stu-=5;
stu*=5;
stu/=5;
stu**=2;     // exponen
stu%=2;      //modulous (reminder)
stu++;
stu--;
```
#### Operator precendence
1. bracket ( )
2. exponents **
3. multi  * , divide / , modulo %
4. addition +, subtraction -
### Advanced meth 
- to calculate 15% of stg , multiple with 0.15
- This is weird behaviour of js where the floats are just fucked
	- ![[Pasted image 20240730103931.png]]
	- this occurs cuz computer stores it with 0/1 , so inaccuracy occurs while storing
	- it happens with some floats, not all
	- to avoid this ,don't add floats, convert them into int and divide later
	- ![[Pasted image 20240730104612.png]]
	- or use Math.round()
* Q (25* 9/5)+32?
* Q  What does `y`  equal?
		1. var x = 3;
		2. var y = x++;
		3. y += 1;
	- A : In this line: var y = x++ the value of x is assigned to y before x is incremented, so y equals 3 on line 2, while x equals 4. There fore on line 3, y now equals 4 instead of 5.
```js
Q
let result1= 1+2*3+4**2;     ??                // 23
let result2= 12%5+8/2;       ??                //6
let result3= 6/2**(2+5);
```
# Math
- got math properties n fxns
## Math.round()
- rounds to integer
	- ![[Pasted image 20240730104913.png]]
	- ![[Pasted image 20240730104923.png]]
	- ![[Pasted image 20240730105102.png]]
- Math.floor()   to round a number down (2.8 -> 2)
- Math.ceil()     to round a number up (2.2 -> 3) 
- some of the 'Math' 
```js
const p=Math.PI;
console.log(Math.PI;
console.log(Math.E);


let x=5.634;
let z=Math.round(x);
let y=Math.floor(x);    // rounds down
let w=Math.ceil(x);     // rounds up
let v=Math.trunc(x);    // removes decimal portion
let q=Math.pow(x,3);
let r=Math.sqrt(x);
let m=Math.log(x);      //natural log, base 'e'
let n=Math.abs(x);      // removes -ve sigh
let o=Math.sign(x);     // +ve (1)/ -ve (-1)   / 0 (0)
let s=Math.sin(x);
let t=Math.cos(x);
let u=Math.tan(x);
  
let max1=Math.max(x,y,z);
let min1=Math.min(x,y,z);
  
console.log(x);
```
# Random no generator
- from 0 to 1 (both exclusive)
- add them if you want them included
```js
let randomNo=Math.floor(Math.random() *6)+1;        
// 0 and 1 exclusive
let randomNo2=Math.floor(Math.random() *100)+1;   // btw 1 and 100
console.log(randomNo);
```
# Operators
-  =  assignment Operator
- == comparison (compare if values r equal)
- === strict equality operator (compare if values & datatype are equal)
	- use this always
- != inequality
- !== strict inequality