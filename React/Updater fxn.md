- fxn passed as argument to setState( )
- safe updates based on previous states
- used with multiple state updates n asynchronous fxns
- good practice to use updater fxns
Q , to increment count by +3 , do you think the below fxn works?
```js
function increment(){
        setCount(count+1);
        setCount(count+1);
        setCount(count+1);
};
```
- Above
	- count only increments by 1, instead of 3 , every time `increment` is called  
	- uses 'current ' state to update 'next' state
	- the code works like
```js
setCount(0+1);
setCount(0+1);
setCount(0+1);
```
- like refresh button
- to so do multiple state update, better to use `updater` fxn
```js
     setCount(count=> count+1);              // updater fxn
```
- but you cannot use `count` and need to use another variable to represent the 'previous state'
```js
     setCount(c => c+1);               // best
```
![[Pasted image 20250314201144.png]]
> [!NOTE] Better to use updater fxn even if ur updating only once
```js
    function decrement(){
        setCount(c=>c-1);
    };
    function increment(){
        setCount(c=>c+1);
        setCount(c=>c+1);
        setCount(c=>c+1);
    };
    function reset(){
        setCount(0); //don't care about previous state here
    };
```
## updater objects
- when you update the obj like this
```js
    function handleyear(e){
        setCar(e.target.value);
    }
```
- only year gets updated and everything else dissapears , so to retain every other key
```js
function handleyear(e){
	setCar({...car , year:e.target.value});
}
// works as 
function handleyear(e){
	setCar({year:2024, model:"mustang" , year:e.target.value});
}
```
- in js, if objects have two properties with same name, it takes the second one
- Updater version of this 
```js
function handleyear(e){
	setCar(c => ({...c, year:e.target.value}));
}
```
- arrow fxn doesnt allow the use of `{}` so enclose them in `()`
# Update state of array 
- 