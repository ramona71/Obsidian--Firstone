- object- collection of related properties and methods 
- obj ={ key: value,    -> properties
        function( ) }  -> methods   of a obj
- !! Two objects can't have same name
```js
const person= {

}
const person={          not allowed XXX // has same name as obj before

}
```
- syntax
```js
const objectname= {
property : value ,
property :value
};

objectname;
objectname.property;
objectname.property= other value;

objectname.newproperty= value;
delete objectname.property;
```
- an example is
```js
const product={
name :'socks',
price :20
};
console.log(product);
console.log(product.name);
product.price= 30;
console.log(product);
product.seller='ravi stores';
console.log(product);
delete product.seller;
console.log(product);
```
- another example
```js
const person1= {
    firstName :"SpongeBob",
    lastName :"SpuarePants",
    age: 30,
    sayHello : function(){
        console.log(`Hi I'm ${this.firstName}`);
    },
    eat:function(){
        console.log(`I'm eating meat!!!`);
    }
}
const person2={
    firstName:"Patrik",
    lastName:"Bateman",
    age:42,
    sayHello:() => console.log(`Hi i'm patrick`),     // interesting way to write fxns
    eat: ()=> console.log(`I'm eating your meat`)
}
console.log(person1.age);
console.log(person2.lastName);
person1.sayHello();
person2.sayHello();
```
- bracket notation 
```js
console.log(product2.name);
console.log(product2['name']);
```
- can keep anything in a bracket
	![[Pasted image 20240819145201.png]]
- bracket notation  - use when accesing properties we cant' access with dot
```js
const product2={
name: 'shirt',
['delivery-time'] : '1day'   // dont have to keep bracket if ur gonna use ''
'delivery-time' : '1day';  // just do this
};

console.log(product2.delivery-time);       // gives error, thinks - is subtactions symbol
console.log(product2['delivery-time']);
```
- object and fxns inside obj
```js
const product2={
rating: {
stars : 4.5,
count: 87
 },
fun : function function1(){
 console.log('function inside object');
  }
};
console.log(product2.rating.stars);
product2.fun();
```
-  objects are references
```js
const obj1={
message: 'hello'
};
const obj2=obj1;
//doesn't copy the object but makes a copy of the referece c/a copy by reference means both point to the same variables
```
- we can change the insides of obj tho it's constant cuz they;re references
```js
obj1.message= 'hi';     // works fine
clg(obj1);
clg(obj2);            // both give hi cuz both r pointing to same reference
```
- can't compare objects
```js
obj3={
message: 'hi';
}
clg(obj1===obj3);      // gives false cuz tho the values r same , the references are different
clg(obj1==obj2);    // true
```
![[Pasted image 20240823170607.png]]
- destructuring
```js
const obj4={
message: 'hello',
price: 733
};
const message= obj4.message;
const {message,price} = obj4;     //both r same
console.log(message);
clg(price);
```
- shorhand property
```js
const obj5={
    message: message,
    //same as above
    message,
    price: 733

    method: function fun1(){
        console.log('method');
    }
    //same as above
    method(){
        console.log('method');
    }
};
```
 - idk more examples
 ```js
 const person= {
        fullName : "sponge up my ass pants",
        age: 30,
        hobbies: ["dance", "play", "cook"],
        address:{
            street: "123 colony",
            city: "bikini bottoms",
            country :"water?"
        }
}
```
# `this` keyword
- reference to obj (immediate context)
```js
const person1= {
    firstName :"SpongeBob",
    lastName :"SpuarePants",
    age: 30,
    sayHello : function(){
        console.log(`Hi!! I'm ${this.firstName}`);  // instead of person1.firstName
    }
}  
person1.sayHello();
```
- `this` doesn't work with arrow fxns (=>)
```js
sayHello : () => console.log(`Hi!! I'm ${this.firstName}`);  //wont work
```
# Constructor
- special method to define properties and methods of objects
- a fxn to define multiple objs
```js
function Car(make ,model, year, color){       // fxn name capital
    this.make=make,
    this.model=model,
    this.year=year,
    this.color=color;
    this.drive= function(){console.log(`You drive ${this.model}`);}
}
const car1=new Car("ford","mustang", 2023,"pink");
const car2=new Car("chavrolet", " camaro" , 2058, "silver");
console.log(car1.year);
car2.drive();
```


# Built in objects - JSON
- JSON and localStorage
- ![[Pasted image 20240823180939.png]]
- JSON
	- doesn't support ' ' only uses " "
	- doesnt support fxns
	- ![[Pasted image 20240819152831.png]]
	- ![[Pasted image 20240819152902.png]]
- convert js object to JSON   use JSON.stringify( )
```js
console.log(JSON.stringify(product2));         // doesn't give fxn cuz it doesn't support it
console.log(typeof JSON.stringify(product2));      //string
```
- convert JSON to js object , use JSON.parse( )
```js
const jsonString = JSON.stringify(product2)
console.log(JSON.parse(jsonString));
console.log(typeof JSON.parse(jsonString));     //object
```
## localStorage
- variables stored in local storage doenn't get deleted when page is refreshed
- localStorage only supports strings- so convert other datatypes to strings using JSON. stingify
```js
localStorage.setItem ('score',JSON.stringify(score));

//convert this back to object
JSON.parse(localStorage.setItem ('score'));
```
- if u try to change the reset the button so that it won't bring previous values when we reset into 
```js
localStorage.removeItem('score')
```
it shows error cuz score gets deleted
```js
score===null 
!score
```
### Other objects
- Auto- boxing-> Java automatically wraps a sting/numbers/ bools into objects
- auto boxing doesn't work with null and undefined
- Strings can have properties and methods
```js
console.log('hello'.length);
console.log('hello'.toUpperCase());
console.log(3.2.toString());
console.log(true.toString());
```
# Class
- cleaner way to work with objs
- ex: static keyword, encapsulation, inheritance

> [!NOTE] Class Product
> Class name stats with Capital letter
```js
class Product{
    constructor(name, price){
        this.name = name,
        this.price= price
    }
    displayProduct(){
        console.log(`Product:${this.name}`);
        console.log(`Price is ${this.price}`);
    }
    calculatTotal(salesTax){
        return this.price+ (this.price* salesTax);
    }
}
const newProduct1=new Product("shirt", 56.99);
newProduct1.displayProduct();
const total=newProduct1.calculatTotal(0.05);
console.log(total.toFixed(2));
```
# Static
- keyword, defines properties / methods, that belong to class (not obj)
- CLASS OWNS ANYTHING STATIC ( not obj)
```js
class MathUtil{
    static PI= 3.1415;
}
console.log(MathUtil.PI);   // since it belongs to class, we call it using class's name
```
- ex
```js
class MathUtil{
    static PI= 3.1415;
    static getDiameter(radius){
        return radius*2;
    }
    static getArea(radius){
        return this.PI*radius*radius;
    }
}
console.log(MathUtil.PI);
console.log(MathUtil.getDiameter(10));
console.log(MathUtil.getArea(10).toFixed(2));
```
- to call a static variable inside a class, u can't use `this` keyword
- `this` -> used to call properties of obj
- static -> doen't belong to obj -> belong to class
```js
class User{
    static usercount=0;
    constructor(username){
        this.username=username;
        User.usercount++;  // `this` is not used here, cuz it doesn't belong to obj  , but to class
    }
    sayHello(){
        console.log(`sup my name is ${this.username}`);
    }
    static getUserCount(){
        console.log(`The usercount is ${User.usercount}`);
    }
}
const user1=new User("spongeBob");
const user2=new User("Sandy");
console.log(user1.username);
console.log(user1.usercount);  // undefined, cuz it's class's property
console.log(User.usercount);
user1.sayHello();
User.getUserCount();
```
[[Inheritance]]
[[Destructuring n other stuff]]

