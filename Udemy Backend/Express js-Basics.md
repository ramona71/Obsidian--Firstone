you- Node - not framework but runtime environment
- node enables us to use js on computer n not just on browsers
- express- js framework
- node- does a lot, so for backend- > we use express to make it useful for web dev
- server is built using express and node (express uses node)
- more stuff at https://expressjs.com/
# Create an express server
1. create directory                                        `mkdir foldername`
2. create index.js file                                      `echo > "index.js"`
3. initialize NPM                                            `npm init -y`
4. Install express package(dependency)       `npm i express`
	1. add `"type": "module"` in package.json
5. Write server application in index.js
6. Start server                                                `node filename.js`
-  ![[Pasted image 20250312120856.png]]
- this starts server on port 3000, locally (localhost)
- o/p -> on terminal the callback is printed and on port 3000, `cannot GET/` is printed
	- ![[Pasted image 20250313151151.png]]
- to avoid this we write
```js
app.get("/", (req,res)=>{                 // shown on the home page
    console.log(req);
})
```
# Create new file
- echo > "filename .txt "    `echo > "index.js"`
- code filename    `code index.js`
	- but you gotta save it for it to get created
# write code then make a file   (not working)
- write code
- `npm install`  to download the dependencies needed that's in the code , you don't have to specify any , all of them will be downloaded
- `nodemon index.js`  to run
## Localhost
- hosting the server locally on our own computer, hence c/a localhost 
## Port
- computer has multiple inputs, keyboard, printer etc
- it needs to listen to all of them
- different ports for different things makes it easy to interpret  
- ![[Pasted image 20250313144238.png]]
	- to see which ports are open
	- OUTPUT WILL BE
	- ![[Pasted image 20250313144340.png]]
## HTTP (request)
- for computers to talk with each other
- client side to talk with server side (req)
- Request vocab
	- GET
		- request resource from server 
	- POST 
		- sending resource to server
	- PUT (update)
		- replace a resource  (whole thing)
	- PATCH(update)
		- patch up a resource (a part of whole thing)
	- DELETE
		- delete a resource from server
- requesting and sending is done
```js
app.get("/", (req,res)=>{
    console.log(req.rawHeaders);
    res.send('Hello world');                  // send txt
    res.send("<h1>HELLO </h1>");                //send html
});
```
![[Pasted image 20250313153545.png]]
![[Pasted image 20250314120910.png]]
## Killing a port
[[Killing a port]]
# nodemon
- automatically restarts the server when the file is updated
- need to install before using
- then server making becomes
1. create directory                                        `mkdir foldername`
2. create index.js file                                      `echo > "index.js"`
3. initialize NPM                                            `npm init -y`
4. Install express package(dependency)       `npm i express`
   Install nodemon                                       `npm i -g nodemon`
	1. add `"type": "module"` in package.json
5. Write server application in index.js
6. Server should handle "/", "/contact", "/about" end points
7. Start server                                                `nodemon filename.js`
- `-g` to install it globally
- can't send two res at the same time
```js
app.get("/", (req,res)=>{
    res.send('Hello world');        
    res.send("<h1>Hello</h1>");      // won't print  , gives error
});
```
## End points
- basically "/" , "/about" , "/contact"  pages
- the pages your server shows if you type them after the localhost url
	- ![[Pasted image 20250313152945.png]]
- basic code gonna be
```js
import express from "express";
const app=express();
const port=3000;
  
app.get("/", (req,res)=>{
    res.send("<h1>Hello this home page gng</h1>");
});
  
app.get("/about", (req,res)=>{
    res.send(`This about page gng`);
})
  
app.get("/contact", (req,res)=>{
    res.send(`this contact page gng`);
})
  
app.listen(port, ()=>{
    console.log(`Server is running on ${port}`);
});
```
# Postman (response)
- to do backend first, then frontend
# Middlewear
- raw request passes through middlewear before it gets processed (get, put, post, patch, delete)
	- to logging request
	- status of request
	- authentication
	- errors in req etc
- commonly used middlewear - > body-parser