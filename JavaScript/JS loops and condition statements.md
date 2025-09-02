# Logical Operators
- used to combine/ manipulate boolean values
- AND &&
- OR  ||
- NOT  !
```js
if(temp>0 && temp<=30) console.log(`Weather good`);
```
- NOT can flip boolean from true to false or false to true
```js
if(!rainy) console.log("Weather is good");
```
# condition statements
- if (condition) {
     block }
- else if (condition) {
	block}
- else{
	block }
```js
if(age>=18 && age<100) console.log(`Can enter the site`);
else if(age==0) console.log(`Hoe is you jsut born?`);
else if(age<0) console.log(`Age less that 0 hoe wtf`);
else if(age>=100) console.log(`Old ass hoe how you still alive?`);
else console.log(`Hoe you young`);
```
## Ternary Operator
- `condn ? codeIftrue : codeIffalse`
```js
let age=25;
age>18 ? console.log(`old ahh`) : console.log(`minor ahh`);
```
- can assign this value to a variable
```js
let message = age>18 ? console.log(`old ahh`) : console.log(`minor ahh`);
```
- ex
```js
let price=100;
let discount= price>50 ? 10 :0;
console.log(`The total amount is ${price + price*(discount/100)}`);
```
## Switch
- Best instead of if else statements
```js
let day=2;
switch(day){
    case 1:
        console.log(`Monday`);
        break;
    case 2:
        console.log(`tuesday`);
        break;
    case 3:
        console.log(`Wednesday`);
        break;
    default:                         // in case there are not matches
        console.log(`Whatever you typed is not a day`);
}
```
- default-> executes no matter what
	- like else statement

> [!NOTE] Dont forget 'break' statement after every case
- if no `break` -> all cases after the matched case will execute
```js
let testScore=92;
let letterGrade;
switch(true){
    case testScore>=90:
        letterGrade ="A";
        break;
    case testScore>=80:
        letterGrade ="B";
    break;
    case testScore>=70:
        letterGrade ="C";
        break;

    case testScore>=60:
        letterGrade ="D";
        break;
    default :
        letterGrade="F";    
}
```
# While
- executes code infinetly , till the condns r met
```js
while(condn) {
	block
}
```
- repeat the code until the condition in no long true
	- good incase of inputting something from the user
```js
let username="";
while(username==="" || username===null){
    username=window.prompt("Enter your name:");
}
console.log(username);
```
 runs the loop till a valid is entered
# DO While
- execute the code first and then check the condition
	- so executes the code at least once
```js
let username;
do{
    username=window.prompt("Enter your name:");
}while(username===""|| username===null)
```
find the difference between these two
hint: the initialization of username
# For loop
- executes code limited no of time
```js
for(){
	block
}
```
- man it's the basic for loop dawgg
```js
for(let i=0;i<=20;i++){
    if(i==13) continue;      // skips an iteration
    else
    console.log(i);
}
```

> [!NOTE] To skip an iteration in loop
> use `continue`     
> To get outta loop `break`
- Check out Number Guessing project-> brocode Js
```js
isNaN(guess)       // checks if guess is a number or not
```
