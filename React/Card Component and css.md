- make sure the fxn name is capital
- `class` is a reserve keyword so use `className` instead in jsx
- if ur using any images etc put them in assets folder
	- and import them to use

> [!NOTE] Import everything, files, jsx, images, videos etc
- the card jsx file
```jsx
import ProfilePic from './assets/square.png';      // import pics
function Card(){
    return (
        <div className="card">          
            <img className='card-image' alt="square image dawg" src={ProfilePic}></img>                               // use imported pic
            <h2 className='card-title'>Mona Lisa</h2>
            <p className='card-para'>I stopped tweaking, it ain't it, instead imma tweak in my journal frrrrrrr ong</p>
        </div>
    );
  
}
export default Card
```

> [!NOTE] This is a fxn based component

> [!NOTE] Mostly css styling will be done in external `index.css` file (main css file, that's directly connected to main.jsx) 

> [!NOTE] When the react app doesn't work, just make a new one and import each file and check where it went wrong
> Dont waste time on old one

# Css styling in react (3 ways)
1. external -> external css file
2. modules -> keeping the specific css file and jsx file in a file
3. inline -> using js object, in the same fxn
## 1. External style sheets
- make a jsx file , import to `App`
- and style it in global css file -> `index.css`
- preferred if naming convension is strong ,and is a smaller application
```jsx
function Button1(){
    const styles={}
    return (
        <button className="button1">Submit</button>
    );
}
```
## 2. Modules
- avoids naming conflict, cuz unique file is generated for you through hashing algo
- make a folder for the jsx
- move the jsx and css file into a specific folder
- here, we import
	- jsx file of `button` into `App`
	- css file of `button` into `button.jsx`   (remember the css naming)
		- by `import styles from './Button2.module.css'`
- the jsx file of module will be like
```jsx
import styles from './Button2.module.css'
  
function Button2(){
    return(
        <button className={styles.button2}>Click me</button>
    );
}
export default Button2
```
- disadv
	- can't apply global styles easily
## 3. Inline
- make a js object and apply them to html
```jsx
function Button1(){
    const styles={
            backgroundColor:"rgb(63, 63, 173)",     // can't use '-' 
            color:" white",
            padding:" 10px 10px",
            borderRadius: "10px",
            cursor: 'pointer',
    }
    return (
        <button style={styles}>Submit</button>
    );
}
```
- great for isolated components
- not preferred (in large code bases)