-  <mark style="background: #ABF7F7A6;">make function for each sub task</mark>
- arrow fxns   , use arrow fxns
- test a fxn if ur done coding it IMMEDIATELY
- add `get` before a fxn name to differenciate it from variable
- `getDepositAmount`  -> fxn   `depositAmount` -> variable
- doesn't matter the order of fxns as long as they're above the calling of that fxn
- if there's a limit on the no. user needs to input, mention it in the prompt
	- `"Enter the no of lines to bet on (1-3): "`
- the steps
	1. get all input fxns and verify them
	2. process the output
- define all variables that won't change as global variables
	- ex: size of slot machine, the symbols, cards in deck, 6 dice faces etc
	- GLOBAL VARIABLES THAT ARE CONST'S -> WRITE THEM IN CAPS
- 

# Technical 
- `const prompt= require("prompt-sync")();`   to give access to the fxn
- `node project.js` to run a project in node
- input is always a sting  , DON'T FORGET TO CHANGE IT INTO A NUMBER
- `const arr= [];`    allows to add/ delete variables inside it despite being const cuz the const will apply to the reference of array(address) and not to the elements inside it
Q 
```js
const SYMBOLS_COUNT = {
    A: 2,
    B: 4,
    C: 6,
    D: 8
};
don't i have to write "A"? why is the code working despite it?
```
A :  JavaScript automatically treats unquoted keys as **strings** when they follow identifier naming rules. The keys (`A`, `B`, `C`, `D`) are automatically interpreted as `"A"`, `"B"`, `"C"`, and `"D"`.
- **No quotes needed** if the key follows valid identifier naming rules (`A`, `name`, `_var`, `camelCase`).
- **Quotes required** for keys with spaces, special characters, or numbers at the start
```js
const obj = {
    "key with space": 42, // ✅ Must use quotes
    "!invalid-key": 10     // ✅ Must use quotes
};
console.log(obj["key with space"]); // ✅ Works

const obj = {
    key with space: 42  // ❌ Syntax Error
};
```
- so , don't actually need quotation marks for keys in js, need them in python tho
- 5X5 grid array
```js
const grid = [];
for (let i = 0; i < 5; i++) {
    grid.push(symbols.slice(i * 5, (i + 1) * 5));
}
console.log(grid);
```
- notice how it's `const grid=[]`  const , even tho we add to array? 
	- in js we can declare array as const and still add elements to it
	- `const` refers to the reference to the array and not the elements of array

> [!NOTE] dont understand

```js
for(let i=0;i< COLS; i++){
        reels.push([]);
        const reelSymbols= [...symbols];
        for(let j=0;j<ROWS; j++){
            const randomIndex= Math.floor(Math.random()*reelSymbols.length);
            const selectedSymbol= reelSymbols[randomIndex];
            reels[i].push(selectedSymbol);
            reelSymbols.splice(randomIndex,1);
        }
    }
```
why can't i just switch up `ROWS` with `COLS` , bruh ???