-   Three ways you can write string, using ' ' or " " or ` `` -> called templete literals`
- But both single n double quote gives single quote
	- ![[Pasted image 20240730124725.png]]
	- so just use single quote in js
- Single quote have exceptions , there use double quote
	- ![[Pasted image 20240730124905.png]]
- use escape character
	- ![[Pasted image 20240730125057.png]]
- using backticks ` `
	- ![[Pasted image 20240730125826.png]]
	- backticks works like f in printf , using { } c/a interpolation
	- instead of f we use $ here
	- ![[Pasted image 20240730130528.png]]	
	- ![[Pasted image 20240730131050.png]] 
- using backticks we can do multi lines
	- ![[Pasted image 20240730130625.png]]
- prefer single quotes over backticks
- Can add strings like in python
```javascript
'some'+ ' text'    -> sometext
"Hi" + name + "How are you?"
```
- 'typeof' gives the type of data
	- ![[Pasted image 20240730112022.png]]
#### Type Coercion
- Automatic type conversion, when concatinating string with number ,all of it converts to string
	- ![[Pasted image 20240730112212.png]]
- JS adds from left to right, (strings follow the order of operations)
	- ![[Pasted image 20240730112356.png]]
	- which means it adds $ and 20.95 first, so addition doesnt occur 
	- ![[Pasted image 20240730112446.png]]
	- here the addn occured
- U can add strings and do math in between 
	- ![[Pasted image 20240730124308.png]]
	- ![[Pasted image 20240730124532.png]]

- use slash n to make new line
	- ![[Pasted image 20240730125326.png]]
	- ![[Pasted image 20240730125305.png]]
- to make them upper or lowecase , just type upper/lower , vs code will fill it for u
- to repeat a string
```js
const greet= 'HEllo!!';
const repeat= greet.repeat(3);
```
- length of string (spaces are also consider as a character , so no on spaces are also counted in lenght)
```js
var name="Kali Jaya";
print(name.length);
```
## Upper and lower case
```js
name.toUpperCase()
name.toLowerCase()
```
# All String Methods
- white space in sting will be considered as a char
- `let userName="   Mona lisa";`
- here M will be at index 3
- from index 0 to 2 -> it's white space 
```js
let userName="   Mona lisa";

console.log(userName.charAt(3));           // returns char at that index
console.log(userName.indexOf("o"));        // returns index of first occurence of that char
console.log(userName.lastIndexOf("o"));    // returns last occurence index of  that char
console.log(userName.length);              // NOT  a method
console.log(userName);
console.log(userName.trim());              // removes white space, from front and last not in the middle
console.log(userName.toUpperCase());
console.log(userName.toLowerCase());
let a=userName.repeat(3);                  // to repeat the string
console.log(a);
let result= userName.startsWith(" ");      //check if string starts wiht white space , returns boolean
console.log(result);
let result2= userName.endsWith("A");      //check if string end wiht 'A', returns boolean
console.log(result2);
let result3= userName.includes(" ");      // if it has empty space
console.log(result3);
```
- the trim( ) method -> front and last white space is removed
	- ![[Pasted image 20250207101412.png]]
- coming to phone numbers -> it's still a STRING (these can be used for char too)
```js
let phoneNo= "123-456-7890";
let phno1=phoneNo.replace("-", "/");
let phno2=phoneNo.padStart(15,"0"); // pad the string with "0"s till it reach 15 char
```
# Slicing
- works like array
- name.slice(0,1)    \[0, 1)       //taking first char from string
```js
const fullName= "Mona lisa";
let firstChar=fullName.slice(0,1);
console.log(firstChar);
let lastChar=fullName.slice(-1);
console.log(lastChar);
  
let firstName= fullName.slice(0,4);      // exclusive, index 4 is not included
let lastName=fullName.slice(5,9);
console.log(firstName);
console.log(lastName);       // this only works for this string
  
// better method for all strings would be
firstName=fullName.slice(0, fullName.indexOf(" "));
lastName=fullName.slice(fullName.indexOf(" ")+1);       //didn't specify the ending index so it goes to the end
console.log(firstName);
console.log(lastName);
```
- ex
```js
const email= "Mona1@gmail.com";
let userName= email.slice(0,email.indexOf("@"));
let extension=email.slice(email.indexOf("@")+1);
console.log(userName);
console.log(extension);
```
# Method chaining
- adding one method after another, writing everything in a single line of code
- trim the whitespace and make the first letter uppercase and the rest lowercase to and entered username
```js
let userName= window.prompt("Enter your username:");
userName= userName.trim().slice(0,1).toUpperCase() + userName.trim().slice(1).toLowerCase();
//or
userName= userName.trim().charAt(0).toUpperCase() + userName.trim().slice(1).toLowerCase();
console.log(userName);
```
- don't abuse it tho
