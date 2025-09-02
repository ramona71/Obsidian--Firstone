- FRONT END FRAMEWORK??
> [!NOTE]  . jsx file name and the function inside it must start with a capital letter
- js library ( NOT FRAMEWORK)
- uses components (reusable block of code(js and html))
- uses syntax extension of js (jsx)- > JavaScript XML 
- uses virtual DOM 
	- can track the changes and update it only to the real DOM without having to refresh the entire webpage
	- reduces performance overhead
- had individual components (HTML, CSS, js in single components, multiple of them)
# VITE
- vite -> built tool
- ` npm create vite@latest my-react-app (file name)` -> node package 
- or `npm create vite@latest my-react-app --template react`
- manager 
	- development server, to make react app
- all this appears
```terminal
√ Project name: ... my-react-app
√ Package name: ... -my-react-app
√ Select a framework: » React      //select it
√ Select a variant: » JavaScript
```
- then do
	- ![[Pasted image 20250224163210.png]]
- appears
```
  VITE v6.1.1  ready in 354 ms

  ➜  Local:   http://localhost:5173/         -> this is the address
  ➜  Network: use --host to expose
  ➜  press h + enter to show help
```
- open the address in web server
- To restart the server if you close out of it
	- `cd path_to_the_folder`
	- `npm run dev`

> [!NOTE] Steps to make a react app and run it
> 1. ` npm create vite@latest my-react-app (file name)`
> 2. `cd path_to_the_folder`
> 3. ` npm install`
> 4. `npm run dev`
# Standard HTML templelte
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>JSX</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  
  <body>
    <div id="root"></div>         %% should have a div with root %%
    <script src="../src/index.js" type="text/javascript"></script>
  </body>
</html>
```
# The structure
![[Pasted image 20250224163950.png]]
- node modules- external libraries and packages our project relies on
	- built tools and utility libraries, routing libraries
- public folder - has public assets (images and videos)
	- not bundled during final output
	- typically available as links (url)
- src folder 
	- assets - same as public folder but files here r bundled during final output
	- main.jsx - js xml file ( the main one)
		- react works with components, in this we have `App` component
	- App.jsx- root component
	- index.css and app.css -> styling files
- index.html ->main entry to our program
- package.json -> structured in key value pairs
	- contains meta data about project such as
		- name 
		- version
		- built
		- react version no etc
# First Component
- we got `App` as first component
- `App` is imported into main.jsx
- so make a jsx file( component) and import it another component
- `Header` component and import it to App component
	- in a fxn you can write html and js code
	- in `return` statement only pure html can be returned
		- and only can return single element( can keep children elements in it)
- make sure to export the comp
	- `export default Header`
- this is how we import n include a component into `App` component
```jsx
import Header from './Header.jsx'
function App() {
  return (
    <Header/>          // including Header component
  );
}
```
- `Header component`
```jsx
function Header(){    // capital
    return(
        <header>
            <h1>My website</h1>
        </header>
    ); 
}
export default Header       
```

> [!NOTE] .jsx is basically like html files and we can add .css to those files
> but with these, the html is inside a function and is returned
# Fragment
- basically empty `<> </>`
- since we can't return multiple html tags , put them in a fragment to return as one
```jsx
  return (
    <>                     // fragment
     <Header/>
     <Footer/>
    </>
  );
```
- to insert js in btw html use `{}`
ex
```jsx
 <p>&copy; {new Date().getFullYear()} Your website name</p>
```


