- allows a new class to inherit properties n methods from existing class
- parent -> child
- code reusability
```js
class Animal{
    alive= true;
    eat(){
        console.log(`this ${this.name} is eating`);
    }
    sleep(){
       console.log(`this ${this.name} is sleeping`);
    }
}
class Rabbit extends Animal{
    name="rabbit";
    hop(){
        console.log(`this ${this.name} is hopping`);
    }
}
class Hawk extends Animal{
    name="hawk";
    fly(){
        console.log(`this ${this.hawk} is flying`);
    }
}
const newRabbit= new Rabbit();
console.log(newRabbit.name);
newRabbit.eat();
newRabbit.sleep();
newRabbit.hop();
```
# Super
- keyword (reference) , used in class to call constructor or access properties n methods of parent (superclass)
- this -> this obj
- super-> the parent
```js
class Animal{
    constructor(name,age){
        this.name=name;
        this.age=age;
    }
    move(speed){
        console.log(`the ${this.name} moves at a speed of ${speed}mph`);
    }
}
class Rabbit extends Animal{
    constructor(name, age,runspeed){
        super(name,age);
        this.runspeed=runspeed;
    }
    hop(){
        console.log(`the ${this.name} hop at a speed of ${this.runspeed}mph`);
        super.move(this.runspeed);
    }
}
class Hawk extends Animal{
    constructor(name, age,flyspeed){
        super(name,age);
        this.flyspeed=flyspeed;
    }
    fly(){
        console.log(`the ${this.name} fly at a speed of ${this.flyspeed}mph`);
        super.move(this.flyspeed);
    }
}
const newRabbit1= new Rabbit("ruby", 2, 20);
const newHawk1= new Hawk("hawky", 6,50);
console.log(newRabbit1.age);
newHawk1.fly();
```
# getter, setter
- validate and modify a value when reading/ writing a prop
- getter- special method -> makes a prop readable
- setter- special method-> makes a prop writable
- `this._width` -> underscore tell the developers that this is a private prop, and different from standard width
```js
class Rectangle{
    constructor(width, height){
        this.width=width;
        this.height=height;
    }
    set width(newWidth){           // writable but not readable
        if(newWidth>0){
            this._width= newWidth;
        }else{
            console.log(`Width must be a positive number`);
        }
    }
    set height(newHeight){
        if(newHeight>0){
            this._height= newHeight;
        }else{
            console.log(`Height must be a positive number`);
        }
    }
    get height(){
        return this._height;
    }
    get width(){
        return this._width;
    }
    get area(){
        return `${(this._width*this._height).toFixed(2)} cm`;
    }
}
//const newRect= new Rectangle(-100000, "pizza"); // users be typing this shit
const newRect= new Rectangle(3, 4); // users be typing this shit
console.log(newRect.width);
console.log(newRect.height);
console.log(newRect.area);
```
- ex 2
```js
class Person{
    constructor(firstName, lastName,age){
        this.firstName=firstName;
        this.lastName=lastName;
        this.age=age;
    }
    set firstName(newFirstName){
        if(typeof newFirstName==="string" && newFirstName.length>0){
            this._firstName=newFirstName;
        }
        else{
            console.log(`Enter a non empty string as FirstName`);
        }
    }
    set lastName(newLastName){
        if(typeof newLastName==="string" && newLastName.length>0){
            this._lastName=newLastName;
        }
        else{
            console.log(`Enter a non empty string as LastName`);
        }
    }
    set age(newAge){
        if(typeof newAge==="number"&& newAge>0){
            this._age=newAge;
        }
        else{
            console.log(`Enter a non empty number as age`);
        }
    }
    get firstName(){
        return this._firstName;
    }
    get lastName(){
        return this._lastName;
    }
    get fullName(){
        return this._firstName+" "+this._lastName;
    }
    get age(){
        return this._age;
    }
}
const per1= new Person("mona", "lisa", 23);
console.log(per1.age);
console.log(per1.fullName);
```