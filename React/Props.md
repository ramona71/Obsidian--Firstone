- read-only properties that are shared between components
- parent component can send data to child component
- `< Component  key=value />`
- reuse the component but have unique data
- props - js object
- in props for any datatype that's not string gets { }
	- ex "sponge bob" , {30} , {false}
# Prop Types
- mechanism that ensures that passed value is of correct datatype
	- ex `age: PropTypes:number`
- !!!  import it , it's present in node modules
Since react 15.5, PropTypes is included in a separate package, 'prop-types'. So this line will help

```javascript
npm install --save prop-types
```
- if PropTypes is not the correct datatype , then a warning will be shown in console (good for debugging as program will run normally)
# defaultProps  (react deprecates this)
- default values in case props are not passed from parent component

> [!NOTE] defaultprops not woking in my case 
```js
//App
import Student from "./Student";
function App(){
    return (
        <>
        <Student name="spongeBob" age={30} isStudent={false}/>
        <Student name="Patrick" age={42} isStudent={true}/>
        <Student/>
        </>
    );
}
export default App

//Student
import PropTypes from 'prop-types'         // make sure to import
function Student({ name, age, isStudent }) {
    return (
        <div className="student">
            <p> Name: {name} </p>
            <p> Age: {age} </p>
            <p> Is Student: {isStudent ? "Yes" : "No"} </p>
        </div>
    );
}
  
Student.propTypes={
    name: PropTypes.string,
    age: PropTypes.number,
    isStudent: PropTypes.bool,
}
Student.defaultProps={         // not woking instea use the below
    name: "Guest",
    age: 0,
    isStudent: false,
}
export default Student;
```
- instead of defaultprops, use the js default parameters
```js
import PropTypes from 'prop-types';

function Student({ name = "Guest", age = 0, isStudent = false }) {  //here
    return (
        <div className="student">
            <p> Name: {name} </p>
            <p> Age: {age} </p>
            <p> Is Student: {isStudent ? "Yes" : "No"} </p>
        </div>
    );
}

Student.propTypes = {
    name: PropTypes.string,
    age: PropTypes.number,
    isStudent: PropTypes.bool,
};

export default Student;

```
