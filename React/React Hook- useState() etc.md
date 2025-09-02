- **react hook**- special fxns that allow fxnal components to use react features without writing class components 
- mostly everthing that starts with "use"
	- useState , useEffect, useContext, useReducer, useCallback etc
- used in FXN based component, not class based component

> [!NOTE] Need to import to use hooks
> `import React, {useState} from 'react';`
## useState()
- react hook
- creates stateful variables n setter fxn to update it's value in virtual DOM
- `[name, setName]`
Q ) tell why this code doesn't update the name?
```js
import React, {useState} from 'react';
function MyComponent(){
    const [name, setName]= useState();
    const updateName= ()=> {
        name= "Spongebob";
    }
    return (<div>
        <p>Name: {name}</p>
        <button onClick={()=> {updateName}}>Update name</button>
    </div>);
}
export default MyComponent;
```
	cuz setName is not used to update name
```js
import React, {useState} from 'react';
function MyComponent(){
    const [name, setName]= useState("Guest");    // initial state is "Guest"
    const [age,setAge]= useState(0);
    const updateName= ()=> {          // all r arrow fxns
        setName("Sponge");
    }
    const updateAge=()=>{
        setAge(age+2);
    }
    return (<div>
        <p>Name: {name}</p>
        <button onClick={()=>updateName()}>Update name</button>
        <p>Age: {age}</p>
        <button onClick={()=>updateAge()}>Update age</button>
    </div>);
}
export default MyComponent;
```
# onChange
- event handler (for form elements)
	- `<input>  <textarea> <select> <radio>`
- triggers fxn every time value of input changes
```js
import { func } from "prop-types";
import React,{useState} from "react";
function OnChangeHandler(){

    const [name,setName]= useState();
    const[quantity,setQuantity]= useState(1);
    const[comment,setComment]= useState("");
    const[payment, setPayment]=useState("");
    const[shipping, setShipping] =useState("delivery");

    function handleName(event){
        setName(event.target.value);
    }
    function handleQuantity(e){
        setQuantity(e.target.value);
    }
    function handleComment(e){
        setComment(e.target.value);
    }
    function handlePayment(e){
        setPayment(e.target.value);
    }
    function handleShipping(e){
        setShipping(e.target.value);
    }

    return(<div>
        <input value={name} onChange={handleName}/>
        <p>Name: {name}</p>
        <input value={quantity} type="number" onChange={handleQuantity}/>
        <p>Quantity: {quantity}</p>

        <textarea value={comment} onChange={handleComment} placeholder="Enter delivery instns" ></textarea>
        <p>Comment : {comment}</p>

        <select value={payment} onChange={handlePayment}>
            <option value="">Select an option</option>
            <option value="visa">Visa</option>
            <option value="mastercard">MasterCard</option>
        </select>
        <p>Payment: {payment}</p>

        <label>
            <input type="radio" value="pickup" checked={shipping==="pickup"} onChange={handleShipping}></input>
            Pick up</label>
        <label>
            <input type="radio" value="delivery" checked={shipping==="delivery"} onChange={handleShipping}></input>
            Delivery</label>
            <p>Shipping: {shipping}</p>
    </div>);
}
export default OnChangeHandler;
```
# Color picker
without css
```js
import React,{useState} from "react";
function ColorPicker(){
    const [color, setcolor]= useState();
    function handleColor(e){
        setcolor(e.target.value);
    }

    return(<div className="colorPickerContainer">
        <h1>Color Picker</h1>
        <div className="colorDisplay" style={{backgroundColor: color}}>   
            <p>Selected Color:{color}</p>   
        </div>
        <label>Select color</label>
        <input type="color" value={color} onChange={handleColor}></input>
    </div>);
}
export default ColorPicker;
```
