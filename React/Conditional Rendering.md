- to control what gets rendered in application based on certain conditions
	- show
	- hide
	- change components
- use 'if else' or ternary operator '?'
```js
function UserGreeting(props){
    if(props.isLoggedIn){
        return (<h2>Welcome {props.username}</h2>);
    }else return <h2>Ur not logged in gng</h2>
}
```
- make it more difficult by using js, if u wish
```js
function UserGreeting(props){
    const welcomeMessage= <h1 className="welcome-message">Welcome {props.username}</h1>;
    const loginPage=<h1 className="login-page">Please login in to continue</h1>;
    return( props.isLoggedIn? welcomeMessage: loginPage)
}
```
# Render List
- method 1 -> list in same function
![[Pasted image 20250314143310.png]]
- method 2 -> list is passed through props
	- ![[Pasted image 20250314143356.png]]
	- ![[Pasted image 20250314143505.png]]
- what if list in empty? short circuit
	- ![[Pasted image 20250314143826.png]]
- what if items / category is missing? defaultProps
	- ![[Pasted image 20250314144142.png]]
	- overall
	- ![[Pasted image 20250314144018.png]]
- don't forget propTypes if ur using 
	- ![[Pasted image 20250314144255.png]]