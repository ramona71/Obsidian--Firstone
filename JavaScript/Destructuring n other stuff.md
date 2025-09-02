- destructuring- extract values from arrays n objs , the assign them to variables in a convenient way
	- `[]` for array destructuring
	- `{}` for obj destructuring
- in arrays
```js
// swap elements
let a=1;
let b=2;
[b,a]=[a,b];
console.log(a);
console.log(b);
// swap elements in array
let numbers=["white", "blue", "black", "pink"];
[numbers[0], numbers[3]]= [numbers[3], numbers[0]];
console.log(numbers);
  
//assign array elements to variables
const colors=["white", "blue", "black", "pink"];
const [color1, color2, ...extracolors]= colors;
console.log(color1);
console.log(color2);
console.log(extracolors);     // forms a new array with remaining colors
```
- in objs
```js
//extract variables from objs
const person1={
    firstName: "spongebob",
    lastName:"spuarepants",
    age: 30,
    job: "cook"
}
const person2={
    firstName: "Patrick",
    lastName:"Star",
    age: 30,
}
  
const{ firstName, lastname1, age1, profession1="unemployed"}= person1; // unemployed is default value
const{ name2, lastname2, age2, profession2="unemployed"}= person2;
console.log(age1);
console.log(firstName);
console.log(lastname1);         // undefined, use the same names defined in obj
console.log(profession2);
```
- instead of `lastname1` use `lastName` as defined in obj -> else it'll print `undefined`
- in fxn paramenters
```js
function displayPerson({firstName, lastName, age, job="umemoloyed"}){ // in parameters, destructuring
    console.log(firstName+lastName+age+job);
}
displayPerson(person1);
```
# Nested Objects
- obj inside obj (child obj inside parent obj)
- complex data structure
```js
const person= {
    fullName : "sponge up my ass pants",
    age: 30,
    address:{                         // obj inside obj
        street: "123 colony",
        city: "bikini bottoms",
        country :"water?"
    }
}
console.log(person.fullName);
console.log(person.address.city);
//or
for(const property in person.address){
    console.log(person.address[property]);
}
```
- complex
```js
class Person{
    constructor(name, age, ...address){        // rest paramenter
        this.name=name;
        this.age=age;
       this.address= new Address(...address)  // rest paramenter // obj in obj
    }
}
class Address{
    constructor(street, city, country, address){
        this.street=street;
        this.city=city;
        this.country=country;
    }
}
const person1= new Person("sponge", 30, "123 street", "biking bottom", "water?");
console.log(person1.address.city);
```
# Array of objects
- yea
```js
const fruits= [{name:"apple", color:"red", calories: "95"},
            {name:"banana", color:"white", calories: "105"},
            {name:"cocounut", color:"green", calories: "195"},
            {name:"pinapple", color:"yellow", calories: "37"}]
console.log(fruits[1].color);
console.log(fruits[0].name);
fruits.pop();
fruits.push({name:"grapes", color:"purple", calories: "80"});
fruits.splice(1,2);     // removes element at certain indexes, at 1,2 r removed
console.log(fruits);
  
//forEach
fruits.forEach(fruit=> console.log(fruit));    // to loop through array
fruits.forEach(fruit=> console.log(fruit.name));
  
// map
const fruitNames= fruits.map(fruit => fruit.name);   // as array
console.log(fruitNames);
  
//filter
const yellowFruits =fruits.filter(fruit =>fruit.color==="yellow");
const lowCalFruits =fruits.filter(fruit =>fruit.calories<100);
console.log(yellowFruits);
console.log(lowCalFruits);
  
//reduce -> not working idk why , too tired
const maxCalFruit= fruits.reduce((max, fruit)=>
                                   fruit.calories > max.calories? fruit: max);
console.log(maxCalFruit);
  
const minCalFruit= fruits.reduce((min, fruit)=>
            fruit.calories < min.calories? fruit: min);
console.log(minCalFruit);
```
# Sort
- sort elements in array, in place
- sorts elements in string in lexicographic order ( alphabet +number +symbols)