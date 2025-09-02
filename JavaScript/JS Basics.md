-  Technology to make websites
- JS -> interpreted(slow running programs) , java-> compiled(fast)
- JS makes website interactive
- Inspect -> console ,(If copy pasting is not enabled, type 'allow pasting' in console and enter )
- Inspect -> Sources -> Snippets
- console -> runs the code line by line, snippet- runs all the code at once 
- Automatic semicolon insertion at ***end***: code is still working without ; at end 
- But use semicolon to avoid bugs
```javascript
alert('Hello')
document.body.innerHTML='hello'
```
- Can directly do math in console

    ![[Pasted image 20240730102606.png]]
- Anything you do in js won't reflect on screen, it reflects on console
```js
console.log(`HEllo`);
console.log(`My ass too fat`);         // will be outputted on console
```
### Adding JS to html file 

1. JS goes at the end of body 
	- at end cuz even if js has errors , html will render
```js
<body>
    <p>Paragraph man</p>
    
    <script>alert('hello');</script>
</body>
```
 2. you can keep add the js inside as attribute using 'onclick'
```js
<button title="Subscribe button" class="red-button" onclick="alert('Good job you subscribed')">Subscribe</button>
```
- create comments using
```js
// This is a comment
or 
/* Multi line 
   comment*/
```
- In HTML and CSS the comments are 
```HTML
<!--This is a comment-->    in html
/*This is a comment */      in css

// This is a comment        in js
/*This is a comment */      in js
```
- console.log( ); prints output in console , not on screen
## Booleans
- type of values, two types, true and false
- two ways to do equal to, use the === cuz == changes the first one into the second one(type conversion happens)
	![[Pasted image 20240818000814.png]]
## Logical operators 
- used in condition statements like if else
```js
console.log(true && false);         false
console.log(false || true);         true
console.log(!true);                 false
```
- false values
```js
false
0
''
NaN
undefined
null
```
```js
console.log(!0);
console.log(0);
console.log('text'/ 5);      // NaN
let v;
console.log(v);           //undefined
```
- *if you try to find length of null value it gives error*
## Scope
- variables made in curly brackets can't be used outside
```js
if(true){
  const v=10;
}
console.log(v);         //gives error cuz v donesn't exist outside curly brackets
```
- u can have same variable in and out of curly brackets and it won't show error
```js
if(true){
  const v=10;
}
const v=11;           // tho v is defined again, it won't show error
```
- u can change the variable inside by defining it outside first
```js
let v=11;                    // use let cuz variable v is changed later
if(true){
  v=10;
}
console.log(v);                  // 10

```
- reason we don't use var is cuz it desn't follow scope
```js
if(true){
  const v=10;
}
const v=11;                // gives error for initializing again
```
## ? operator
```js
const r=true? 'true man': 'false man';
console.log(r);                              //true man

//words as 
let r;

if(r===true)
r='true man`;

else
r='false man';

```
- ![[Pasted image 20240818135954.png]]
- ![[Pasted image 20240818140023.png]]
## Guard operator
- &&
```js
false && console.log('hello');
```
- can be stored in variable
```js
const message= 5 && 'hello';
console.log(message);                     // hello
```
- ![[Pasted image 20240818140059.png]]
- ![[Pasted image 20240818140125.png]]
## Default operator
- ||        stops if the first condition true
```js
const curr = 'RS' || 'USD';
console.log(curr); 

const cur = undefined || 'USD';
console.log(cur);
```
- ![[Pasted image 20240818140159.png]]
- ![[Pasted image 20240818140341.png]]
- ![[Pasted image 20240823165301.png]]
## Prompt
- asks user for imput
```js
prompt("What is you name?");
```