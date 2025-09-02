- document obj
- another built in obj like jason and localstorage
```js
document.body.innerHTML='hello';
document.title='DOM- js';
console.log(document.title);
document.body.innerHTML='<button>Good job </button>';
```
- directly changes the webpage
- document. body takes body and puts it in js
```js
console.log(document.body);
```
- with this we have html elements inside js, gives control to js
	- html is converted to js, into a js object
	- so we can use properties on it

> [!NOTE] Onlick doesn't have brackets ( ) dumbahh
> myBtn.onclick= function(){
## Methods
- querySelector()- let's us get any element from the page and put it in js
- every html element has .innerHTML prop
- if html is inside js, it's just js object now
```js
document.querySelector('button')
console.log(document.querySelector('button').innerHTML);
document.querySelector('button').innerHTML= 'changed agin'; // the button is an object now

const buttonElement=document.querySelector('.js-b2');
console.log(buttonElement);
```
## Methods to keep JS in code
- 1. Inline
	- not prefered
```js
</head>
<body onload="alert('Hello')";>          // inline
</body>
</html>
```
- 2. Internal
	- 'script'  tag is used
```js
<body>
    <script type="text/javascript">
        alert('Hello');
    </script>
</body>
```
- 3. External file
	- we keep css file inside 'head ' tag and js inside 'body' tag 
	- where we put it matters- cuz  the compiler reads code line by line, order matters
	- always keep css first- inside 'head' 
	- js at the last - inside 'body' on last line
```js
<body>
    <h1>EHllp</h1>
  
    <script src="index.js" charaset="UTF-8"></script>
</body>
```
# DOMS
![[Pasted image 20250102154016.png]]
- doms model (organization structure )- tree str
- Objects inside dom have properties and methods
	- main difference is " ( ) "
- ![[Pasted image 20250102155305.png]]
- diff between fxn and methods
	- methods- related to object (classes)
- document.firstElementChild  is always html 
- document.firstElementChild.firstElementChild -> head
- document.firstElementChild.lastElementChild-> body
- u just store them in a variable
`var body1 = document.firstElementChild.firstElementChild; `
- document.firstElementChild.lastElementChild.querySelector("ul").lastElementChild.innerHTML = "Angela";
- document.firstElementChild( HTML FILE ).lastElementChild( BODY TAG ) .querySelector("ul").lastElementChild.innerHTML = "Angela";
## Some doms properties
- `firstElementChild`
- `lastElementChild`
- `querySelector` -> works like css
	- `document.querySelector("h1");`  -> direct selection
	- `document.querySelector(".btn");` ->selecting a class
	- `document.querySelector("#myh1");` -> selecting by id
	- `document.querySelector("li a");`  -> selecting anchor inside list element
	- `document.querySelector("#list a")` ->  same but diff representation
	- `document.querySelector("li.item");`  -> both r in same element (list of class name item)
- `getElementById`
- `getElementsByTagname`     -> an array
- `getElementsByClassName`   -> an array

> [!NOTE] If a same selector matches two elements then only first one prints
> if you want all the instances to print use `document.querySelectorAll();`
> gives array of things that suit this selector, so use it like array
> `document.querySelectorAll("list")[2];`
- make sure to keep id in "" 
	- "myh1" like that, don't forget  " "
```js
document.getElementById("myh1").textContent= "Hello man";
document.getElementById("myp").textContent="I like your mom";
```
- Project -> b_rolldice
- 
```js
```
- i
```js
```
