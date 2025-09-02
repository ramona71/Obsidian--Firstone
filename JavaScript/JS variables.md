- variable- container that stores value  
- Can't use special words ex: let
- can't start with numbers
- can't use special character except $ and _
-  Camel case - cartQuantity    (mostly used)
   Pascal case - CartQuantity
   Kabab-case - cart-quantity (doesn't work in js, only in html and css)
   snake_case - cart_quantity
```
   const z=10;       //can't change value of const	
   z=12;              // gives error
```
- prefer const over let for unchagable values
- var- also used to create variables
- three ways to create variable- let (most used), const and var
```js
let x;
console.log(x);           // outputs undefined
```
![[Pasted image 20250205123026.png]]
- let can take any type of variable(int, double, bool)
```js
let age=25;
let price= 10.99;
let gpa=2.1;
console.log(`You are of age ${age}, and has a gpa of ${gpa}`);
console.log(`The price is $${price}`);         // two $$
```
- typeof - to find type of variable
```js
console.log(typeof gpa);
console.log(typeof age);
console.log(typeof gpa);                   // all r 'number' datatype
```
- dont put variables inside " "
```js
let firstName= "Kingdiddy";
console.log(firstName);          // not "firstName" ykright?
let email="monalisa@gmail.com";
console.log(`Your email is ${email}`);
```
### Boolean
- either true or false
```js
let online= true;           // no " "
console.log(typeof online);
console.log(`Bro is online? ${online}`);
let forsale= false;
console.log(`Is the car for sale? ${forsale}`);
```
- change then by ID
```js
let fullName= " Ramona Nand";
let age=20;
let isStudent = true;
  
document.getElementById("p1"). textContent= `Your full name is ${fullName}`;
document.getElementById("p2").textContent=`Your age is ${age}`;
document.getElementById("p3").textContent=isStudent;
```
### User Input
- 2 ways
	- prompt
	- html txtbox( professional)
- prompt - asks the user for input
```js
userName= window.prompt(`What's ur username>`);
userName= prompt("What is your name?");         
// both are the same 
console.log(userName);                          // in console, not on screen
```
- ex
```js
	<h1 id="myh1">Welcome</h1>
    <label for="userName">userName: </label>
    <input id="userName"><br> <br>
    <button id="mySubmit">Submit</button>

let username;
document.getElementById("mySubmit").onclick= function(){
    username= document.getElementById('userName').value;
    console.log(username);
    document.getElementById("myh1").textContent=`Welcome ${username}`;
}
```
## Type conversion
- btw (strings, numbers, booleans)
- input will be taken in string datatype, always convert it to number
```js
let age= prompt("your age?"); //string
age+=11;                      // appends 11 at end
console.log(age);
```
- so do 
```js
let age= prompt("your age?"); //string
age= Number(age);             //this line
age+=11;                      
console.log(age, typeof age);
```
- convert sting to other
```js
let x ="pizza";
let y ="pizza";
let z ="pizza";
  
x=Number(x);
y=String(y);
z=Boolean(z);
  
console.log(x, typeof x);
console.log(y, typeof y);
console.log(z, typeof z);
```
![[Pasted image 20250205143307.png]]
- NaN-> not a number
```js
let x ="0";
let y ="0";
let z ="0";
  
x=Number(x);
y=String(y);
z=Boolean(z);
```
![[Pasted image 20250205143431.png]]
- "0" still gives boolean as true
- empty sting gives false
```js
let x ="";
let y ="";
let z ="";
  
x=Number(x);
y=String(y);
z=Boolean(z);
```
![[Pasted image 20250205143545.png]]
- undeclared variables?
```js
let x ;
let y ;
let z ;
  
x=Number(x);
y=String(y);
z=Boolean(z);
```
![[Pasted image 20250205143659.png]]
## Const
- variable that can't be changed
- capitalize const variables (only numbers & bools)
	- ex :`const PI`
```js
const PI=3.14;            // dont use 'let' here
let radius;
let circumference;
PI= 3.14568;              //TypeError : can't re assign (exception handling)
radius= window.prompt("Enter the radius of circle");
radius= Number(radius);
circumference= 2*pi*radius;
console.log(circumference);
```
- in code
```js
    <h1 id="myh1">Enter radius hoe</h1>
    <label for="rad">Radius:</label>
    <input id="rad" type="text"><br> <br>
    <button id="submission">Submit</button>
    <h3 id="myh3"></h3>
    
const PI=3.14159;            // dont use let here
let radius;
let circumference;
document.getElementById("submission").onclick= function(){
    radius=document.getElementById("rad").value;
    radius= Number(radius);
    circumference= 2*PI*radius;
    document.getElementById("myh3").textContent=`The circumferece is ${circumference}`
}
```
- buttons are usually assigned as constants
```js
const decreaseBtn= document.getElementById("decreaseBtn");  
const resetBtn=document.getElementById("resetBtn");
const increaseBtn=document.getElementById("increaseBtn");
```
# Variable Scope
- Global vs Local( inside fxns)
```js
let x=1;
let x=2;            // error
```
- You can reuse variable names as long as they're in different scopes (like same variable in diff fxns)
- if global (declared outside all the fxns) it can be assessed from anywhere
	- not advised in large programs (naming conflicts)
- Order of importance
	- 1. local
	- 2. global