- Node js- not framework
	- it's a runtime environment
- different backends use different frameworks
- frameworks - gives inbuilt stuff so we don't have to write everything from scratch
- Node js- made so that js can be used outside and on local computer and not only on websites
- synchronous- beginning to end , code is compiled line by line
- node js- asynchronous event driven js runtime
	- allows us to use js full stack
	- easy scaling
	- non blocking
	- huge ecosystem
- NODE REPL - Real Eval Print Loop
	- environment, where user inputs r evaluated and output is printed back
- Some commands
	- ![[Pasted image 20250127144442.png]]
```node
node -v          // version
node             // to enter the mode?
.help           // help
.exit           // to exit
```

> [!NOTE] To get out of most REPL s 
> CTR + C  (2 times)    // usually for any processes, a few times
> or CRL + D (here)
- Node works similar to js
	- ![[Pasted image 20250127145240.png]]
- How to run a node file
	- 1. go into the directory using cd
	- 2. `node filename.js` and hit enter
	- the file will run
	- ![[Pasted image 20250127145847.png]]
# Native node Modules
- pre- existing modules
### Modules
- https://nodejs.org/docs/latest-v18.x/api/index.html
- most imp is file system
### File system
-  native node module, that allows us to use local storage (like obsidian?? ohhh)
- https://nodejs.org/docs/latest-v18.x/api/fs.html#filehandlewritefiledata-options 
	- the syntax is available here
- To write into a file
```js
const fs= require("fs");
fs.writeFile("message.txt", "Man fuck you", (err) => {
    if (err) {
      console.error("An error occurred while writing to the file:", err);
      return;
    }
    console.log("File has been written successfully!");
  });
```
 remember the syntax 
 - to read from a file
 ```js
 fs.readFile("message.txt",'utf8',(err, data) => {
    if (err) throw err;
    console.log(data);
  });
```
- here the syntax is
	- ![[Pasted image 20250127152302.png]]
	- but we also need to add `'utf8'` encoding for strings -> don't forget these
	- without encoding it'll print the buffer
	- ![[Pasted image 20250127152444.png]]
## NPM ( node package manager)
- comes with node
- open source and has a lot of modules (native node modules)
- `npm init` to open utility window (in command prompt, not powershell)
	- powershell needs some permissions, fuck that
- json - configuration file
	- ![[Pasted image 20250127153842.png]]
	- reference
	- ![[Pasted image 20250127172343.png]]
	- even if you forget to do this, you can always do it latter with `npm init -y`
- install npm package
	- `npm install <package_1 package_2 etc >`
	- https://www.npmjs.com/   (npm manager) -> find packages here

> [!NOTE] !!!!
> ALWAYS INSTALL IN CMD AND NOT 'CODE ' OR 'POWERSHELL' !!!
- ex 
	- `npm i sillyname`   -> installs sillyname package (type in cmd terminal)
	- ![[Pasted image 20250127181623.png]]
	- ![[Pasted image 20250127181609.png]]
	- ![[Pasted image 20250127181712.png]]
	- the package is installed n added to json file
- [[Convert ESM to CJs]]
## ESM
- CJS- > common js (used in the past ) 
	- uses `require` keyword
	- for ex `var generateName = require('sillyname');
```js
var generateName = require('sillyname');
var name = generateName();
  
console.log(`My name is ${name}`);
```
- ESM - ECMAScript module (modern currently used)
	- imports the modules
- How to use ESM 
	- add `"type" : "module" ` after main in json file
	- ![[Pasted image 20250127182434.png]]
```js
import generateName from "sillyname";
var name= generateName();
  
console.log(`My name is ${name}`);
```

> [!NOTE] !!!
> Make sure type: module is set to use 'import' !!
# Random superhero
- hers
	- ![[Pasted image 20250127183620.png]]
	- bro used .random() -> why did my ass didn't think that
- mine
```js
import {randomSuperhero} from 'superheroes';
  
var name = randomSuperhero();
console.log(`I am ${name}!!!`);
```
