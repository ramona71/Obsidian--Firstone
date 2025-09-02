 - section of re usable code
 ```js
 function isEven(number){
    return number%2==0 ? true: false;
}
console.log(isEven(12));
  
function isValidEmail(email){
     return (email.includes("@")) ? true : false;
}
console.log(isValidEmail("man@mail"));
console.log(isValidEmail("man.mail"));
```
- use camelCase for naming fxns
- ![[Pasted image 20240818150945.png]]
- u can return anything from a fxn, int, string or the below
- ![[Pasted image 20240818151901.png]]
- return statement is not compulsory 
```js
<button onclick="
console.log(funct1());         // prints rock
<\button>

<script>
function funct1(){
return 'rock';           
}
// return can have anything inside, string , number, math , etc
return cost%5;
```
- returns undefined if
```js
return;            //returns undefined
```
- returning a variable is prefered over global variable- to prevent naming conflicts
	![[Pasted image 20240818160529.png]]
## Parameters
```js
function fxnName(parameters){
	block
}
fxnName(arguments);
```
- make sure arguments passed are in same order of parameters
```js
function student(name, age){
	block
}
student(12, "Mani");            // the order is wrong
```

![[Pasted image 20240818161137.png]]
- ![[Pasted image 20240818161203.png]]
- if parameter is not passed, it gives undefined
```js
 function calcutateTax(parameter1,percent){
	console.log(percent);
	console.log(parameter1* percent);
  }
 calcutateTax(5000 );
```
![[Pasted image 20240818161541.png]]
- add default value to parameter
```js
function calcutateTax(percent=0.1){ }
```
# Arrays
- some shit udk here
```js
const images=[];      // hoe remember the syntax, intializing array
let fruits=["apple", "orange", "banana"];
console.log(fruits);    // prints whole array with size
console.log(fruits[2]);
// addin
fruits[3]="coconut";
console.log(fruits[3]);
fruits.push("melon");    // also adding
fruits.pop();            //last one
fruits.unshift("mango");  // adds in the beginning
fruits.shift();           // removed from the beginning
  
let n=fruits.length;               //length
let index=fruits.indexOf("apple"); // -1 if not found
  
for(let x of fruits)
    console.log(x);
fruits.sort();      // alphabetical order main sort hoga
fruits.sort().reverse();   // reverse
```
# Spread operator
- `...` spreads the elements of iterables ( arrays, strings) into separate elements
```js
let numbers= [1,2,3,4,5,6];
//let maximun= Math.max(numbers);  // can't directly put the array
let maximun= Math.max(...numbers);  // gives max no
let minimum=Math.min(...numbers);
console.log(maximun);
  
let userName= "Mona lisa";
let letters= [...userName];         // makes a array
let name=[...userName]. join("-");   // joins the array
console.log(letters);       // array
console.log(name);          // string
  
// shallow copy of array using spread operator
let fruits=["apple", "orange", "banana"];
let newFruits= [...fruits];
console.log(newFruits);
  
//can join two arrays
let vegies=["carrot", "brinjal", " potato"];
let food= [...fruits, ...vegies, "milk" , "curd"];
```
# Rest parameter
- bundles separate elements into a single array
	- mostly in functions
```js
function openFridge(...foods){    // variable no of paramenters
    console.log(foods);
}
const food1="pizza";
const food2="hamburger";
const food3="ramen";
const food4="coke";
openFridge(food1,food2,food3,food4, "maggi");
```
- yea tbh
```js
function combineStrings(...strings){
   return strings.join(" ");
}
  
const fullName= combineStrings("Mr.", "Spongebob", "III");
console.log(fullName);
```
# Call Back
- fxn that's passed as parameter to another fxn
- so that the second fxn is called after the first function even if the first fxn takes time
- js usually don't wait for a fxn to execute , it goes to next fxn if it's taking time
	- used to handle asynchronous operations (takes variable amount of time)
		- 1. reading a file
		- 2. network requests
		- 3. interacting with databases
```js
function hello(callback){
    console.log("hello");
    callback();
}
function wait(){
    console.log('wait');
}
hello(wait);        // wait will execute after hello
hello(wait());     -> nuh uh XXX  // syntax error
```
- ex
```js
function sum(callback, x, y){
    let result= x+y;
    callback(result);
}
function displaysum(result){
    console.log(result);
}
sum(displaysum, 65 ,6);
```
# forEach( )
- `forEach()` -> method, to apply a specific fxn (callback) to each element of array
- `array.forEach(callback)` -> syntax
```js
// doubling each element before displaying it
let number=[1,2,3,5,6,7];
number.forEach(display);
  
function display(element){
   console.log(element*2);
}
```
- cube elements 
```js
let number=[1,2,3,5,6,7];
number.forEach(cube);
number.forEach(display);
  
function cube(element, index, array){    // need to pass these parameters for array  // 
// the order is imp!! (element, index, array)
    array[index]= Math.pow(element,3);
}
  
function display(element){
    console.log(element*2);
 }
```
# `.map()`
- accepts a call back, applies that to each element of array and returns a new array
- make sure to `return` the element
```js
const fruits =["apple", "banana", "cocoNut"];
const newFruits= fruits.map(capitalize);
console.log(newFruits);
  
function capitalize(element,index, array){
    return element.charAt(0).toUpperCase() + element.slice(1).toLowerCase();
}   // make sure to return, not just assign
```
- more ex
```js
const dates=["2024-5-23", "2024-12-31", " 2022-8-14"];
const fomattedDates= dates.map(format);
console.log(fomattedDates);
  
function format(element){
    const parts= element.split("-");
    return `${parts[2]}/ ${parts[1]} /${parts[0]}`;
}
```
# `.filter()`
- creates a new array by filtering out elements
```js
let number=[1,2,3,5,6,7];
let evenNO= number.filter(findEven);
console.log(evenNO);
  
function findEven(element){
    return element%2==0;
}
```
# `.reduce()`
- reduce the elements of array to a single value
	- to find sum of array elements 
	- find min/max
```js
let number=[1,2,3,5,6,7];
const sum= number.reduce(getSum);
console.log(sum);
const maxElement= number.reduce(getMax);
console.log(maxElement);
  
function getSum(accumulator, element){
    return accumulator+element;
}
function getMax(accumulator,element){
    return Math.max(accumulator, element)
}
```
# Function expression
- fxn declaration -> declaring a fxn
```js
function hello() {
	clg('hello');
}
```
- fxn expression-> storing a function as variable / passing whole fxn as variable
	- used as
		- callbacks in asynchronous operations
		- High- order function
		- closures
		- event listeners
```js
const greet = function() {
    console.log("Hello");
}
greet();         // storing fxn in 'greet' variable
```
- fxn after a timeout
```js
//setTimeout(callback, time)
setTimeout(greet, 2000);
```
- instead of this, in js , you can send entire fxn as argument
```js
setTimeout(function() {
    console.log('hello');  
}, 2000);
```
- ex -> instead of defining a fxn for map, just do
```js
const numbers=[1,2,3,5,6,7];
const squares=numbers.map(function(element){
    return Math.pow(element,2);
});
```
# Arrow function
- for fxn expressions you only once 
- `(parameter)=> some code`
```js
const hello = (name) => console.log(`Hello ${name}`);
hello('mona');
```
- as callbacks
```js
setTimeout(() => {
    console.log("hello");
}, 2000);
```
- more ex
```js
const numbers=[1,2,3,5,6,7];
const squares= numbers.map( (element)=> Math.pow(element,2) );
const isEven=numbers.filter((element)=> element%2==0 );
const total=numbers.reduce((accumulator,element)=> accumulator+element);
console.log(total);
```