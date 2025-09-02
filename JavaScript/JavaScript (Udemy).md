### Random number
- var n= Math.random( );
	- generated between 0 and 0.9999999999999999999
	- upto a billion random numbers -> generated
- n= Math.floor(n);             -> round to nearest whole number
- love calculator
```js
//prompt("What is your name?");
//prompt("What is their name?");

var lovescore= Math.random()*100;
lovescore=Math.floor(lovescore)+1;          // +1 cuz we need it go to 100, from 1 to 100
console.log(lovescore);

if(lovescore>60){
    alert(`your love score is ${lovescore}%. You love each other like Kanye love Kanye`);
}else{
    alert(`your love score is ${lovescore}%`);
}
```
## Comparators
- ![[Pasted image 20241201154109.png]]
- both == and === checks if the variables are equal or not but == ignores the datatype
- if a= 1 and b= "1"
```js
if (a==b) { console.log("yes")} else console.log("no")
if (a===b) { console.log("yes")} else console.log("no")
```
- == gives yes (it doesn't check the datatype, both 'a' and 'b' are equal to 1)
- === gives no cuz they're not equal (both in value and datatype)
## leap year

> [!NOTE] Title
> If question in tricky to solve, make a flow chart

- ![[Pasted image 20241201160521.png]]
```js
var year=100;
if(year%4===0){
    if(year%100===0){
        if(year%400===0){
            console.log("Leap year");
        }
        else{
            console.log("Not Leap year");
        }
    }else{
        console.log("Leap year");
    }
}else
    console.log("Not leap year");
```
## Array
```js
var guestlist= ["Applejack", "Mymom", "Sukuna", "Largepenis", "CaseOh"];
console.log(guestlist);   // print whole array
console.log(guestlist.length);      // lenght
console.log(guestlist.includes("Applejack"));       // true
console.log(guestlist.push("Smoltatas"));           // always pushes at end
console.log(guestlist.push(6));                     // pushes 6
console.log(guestlist.pop());                       //last one gets deleted
```
-  to see if a person is in guest list or not
```js
var guestlist= ["Applejack", "Mymom", "Sukuna", "Largepenis", "CaseOh"];
var guestname= prompt("What is your name?");
if(guestlist.includes(guestname))
    console.log("Yep he in")
else
    console.log("nah he ain't in")
```
- ![[Pasted image 20241201165104.png]]
```js
var output=[];
var n=1;
function fizbuzz() {
    if(n%3==0 && n%5==0)
        output.push("FizzBuzz");
    else if(n%3==0)
        output.push("Fizz");
    else if(n%5==0)
        output.push("Buzz");
    else
        output.push(n);
    console.log(output);
    n++;
}
```
- use 'count' instead of 'n'
- now to use while loop in above
```js
var output=[];
var n=1;
function fizbuzz() {
   while (n<100){
        if(n%3==0 && n%5==0)
        output.push("FizzBuzz");
        else if(n%3==0)
            output.push("Fizz");
        else if(n%5==0)
            output.push("Buzz");
        else
            output.push(n);
        console.log(output);
        n++;
   }
}
```
- random person gonna buys lunch
```js
const randomIndex = Math.floor(Math.random() * names.length);           // this line
const selectedPerson = names[randomIndex];
return `${selectedPerson} is going to buy lunch today!`;
```
## Fibonacci
- flow charts help
- ![[Pasted image 20241201192341.png]]
```js
function fibonacciGenerator (n) {
var output=[];
if(n==1) {
    output.push(0);
    return output;
}
if(n==2) {
    output.push(0);
    output.push(1);
    return output;
}
if(n>=3){
    var m=2;
    output.push(0);
    output.push(1);
    while(m<n){
    output[m]=output[m-1]+output[m-2];
    m++
    }
}
return output;
}
```
- this took me longer than i thought
- ![[Pasted image 20241201194202.png]]