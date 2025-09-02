- font size
- font weight
- font family
- text-align
- border
- padding
- margin
- color














### Border
- border goes outwords and the width and height of html element remains same
```css
border: 10px solid black;
border-top:0px;
border: 0px , 10px, 20px, 30px;   goes in clock wise direction
border: 0px, 10px;                goes in top-bottom, left-right combo
```
![[Pasted image 20240914141010.png]]
![[Pasted image 20240914140831.png]]
- border styles -> there are so many to choose from
	- ![[Pasted image 20250202153103.png]]
```css
h1{
    border-style:inset;
    border-width: 5px;
    border-color: purple;
}
  
/* or just do */
h1{
    border: 5px inset purple;
}
```
### Padding
![[Pasted image 20240914140805.png]]
- padding pushes border out, the height and width of space doesn't change
### Margin
- margin is outside the element
![[Pasted image 20240914140937.png]]

# Font
- can download them onto ur system , or use google API
- (the below one did not work tho)
```css
@font-face {
    font-family: kanit-mediumItalic;
    src: url(Kanit\Kanit-MediumItalic.ttf);
}
h1{
    font-family: "Kanit Medium Italic";

// this worked
@import url('https://fonts.googleapis.com/css2?family=Kanit&display=swap');
```
### Font family
- two fonts r written one after another, 2nd one called fall back font
- some websties doesnt' support a font ,so we need fall back font
### Font size
- 1px
- 1pt
- 1em- relative to parent- 100% of the parent size- the tag it's in (1.1em -> 110%  )
- 1rem- relative to root- 100% of the root size, which is normally html tag
### Font weight
- normal , bold
- lighter, bolder
- 100-900
## Position
- fixed= placed in the browser window
- absolute=placed on the page
- position:      you can use them individually
	- fixed
	- absolute
	- relative
	- static
-  put position absolute into position: fixed/relative to keep items on top of each other
### Inheritance
- affects mostly text , not all properties like border , margin, padding.
## Color
- ![[Pasted image 20240919235941.png]]
- colors
	- names -> red
	- rgb -> rgb(255,0,0)
	- hexa decimal -> #ff0000
	- hsl (0,100%, 50%)     (hue, staturation, lighness)
- available on a lot of websites
	- https://developer.mozilla.org/en-US/docs/Web/CSS/named-color
```css
#p1{
    color: tomato;
}
#p2{
    color: rgb(79, 60, 245);
}
#p3{
    color: #fff000;
}
#p4{
    color: hsl(93, 90%, 69%);  
}
```