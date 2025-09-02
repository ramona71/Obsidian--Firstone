- click event-An interaction when a user clicks on specific element
	- respond to click -> callback to onClick event handler
- if onClick has a parameter, then we need to wrap this in a fxn expression or arrow fxn
- html elements have onClick event handler
```js
function Button(){
    const handleClick= ()=> console.log("Ouch");
    const handleClick2 =(name)=> console.log(`${name} stop clicking me`);
    return(<button onClick={handleClick2("mona")}>Click me</button>)
}
```
	- this immediatly exectutes the fxn without even clicking
-  to execute after clicking
```js
return(<button onClick={()=> handleClick2("mona")}>Click me</button>)
```
## event parameter (e)
- obj , it's a parameter
- `event` but ppl just use `e`
```js
// to display the methods this parameter has
function Button(){
    const handleClick =(e)=> console.log(e);
    return (<button onClick={(e)=>handleClick(e)}>Click me</button>)
}
// to change text on click to "ouch"
const handleClick =(e)=> e.target.textContent="Ouch";
```
## Doubleclick
- doubleclick gng
- `onDoubleClick` instead of `onClick` yk
```js
<button onDoubleClick={(e)=>handleClick(e)}>Click me</button>
```
- to make a image disapear on clicking
```js
  

function ProfilePicture(){
    const imageUrl ="./src/assets/react.svg";
    const handleClick= (e)=> e.target.style.display="none";
    return(<img onClick={(e)=> handleClick(e)} src={imageUrl}></img>);
}
export default ProfilePicture
```
