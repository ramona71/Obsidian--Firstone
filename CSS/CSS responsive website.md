 - use
	- media queries
	- css grid
	- css flexbox
	- external frameworks (bootstrap)
## Media Queries
```css
@media (min-width:66px) and (max-width:99px){
}
```
- to change the page while printing , use @media print (orentation:landscape)
## Flex box
- flex
```css
.box{
display:flex;
gap:10px;
}
```
- in flex box, all of them will be flex, not block not inline not inline block (even if you keep paragraph element, all will turn into inline-block typa flex element)
- inline flex- like inline block but with flex element
- flow direction- row- main axis , cross axis from top to bottom
- flow direction- coloumn- main axis- top to bottom - cross from left to right
- ![[Pasted image 20240917170311.png]]
- u can even shorten it and jsut write flex:1;           has grow 1 , shrink 1 and basis 0
#### Flex sizing
- the order in which the content shrinks when the page size is changed is
	mix/max width(we set) > flex basis> width (we set)> content width
	![[Pasted image 20240917165721.png]]

-  flex basis- like width, which we set in flex
- order: 1;             elemnt goes at last cuz others don't have any order, it doesn't have default value like z index
- flex-wrap: nowrap;        going to continue to push of screen
- https://appbrewery.github.io/flex-layout/ for more flex and justify content and align items type shit
- flex box cheet sheet   https://css-tricks.com/snippets/css/a-guide-to-flexbox/
- justify content is for row wise (main axis), to centre
 ![[Pasted image 20240916221120.png]]
- but align content is for column wise(column wise)
 ![[Pasted image 20240916221148.png]]
 - height : 70vh;  like %
 - align- content only works when flex is set to wrap
 - if the flexbox doesn't align in center use 
	 - Add `height: 100vh;` to your `body` to make sure it takes the full height of the viewport. The `vh` unit represents 1% of the viewport height, so `100vh` makes the body as tall as the visible area of the browser window.
## Grid
- auto: the size of box fix to the content in it
- ![[Pasted image 20240919214324.png]]
- Grid sizing
	- fixed = grid-template-rows :100px;
	- auto= grid-template-rows : auto;
	- fractional= grid-template-rows :1fr;
	- minmax= grid-template-rows: minmax(400px, 800px); 
	- repeat= grid-template-rows : repeat(4,200px);
- if grid is only defined for 4 elements (2X2) but there are 5 elements , then the height of 5th elements is set according to content but the width will be of the grid's 
- in these cases u can keep auto size for the width
```css
grid-auto-rows: 200px;              // sets the new elements height 200px
```

- grid tracks: grid rows n columns
- grid lines: that separate the grid cells
- container: can be made of more that one cell
- to make the element take up more that one cell use grid-column: span 2;   ->takes two cells
- can also do grid- column-start : 1;   grid-column-end:2;
```css
//instead of typing
grid-column-start:1;
grid-column-end:2;
grid-row-start:3;
grid-row-end:4;

//just use
grid-column: span 2;
grid-row:;

//even smaller
grid-area: 3/1/4/2;        //    rowstart/columstart/rowend/columnend
```
- main difference between flex box and grid is that grid lets u overlay items
	- ![[Pasted image 20240919235819.png]]
- 

## Bootstrap
- built on flexbox
- external css layout system
- open source
- contained premade html frames
- 10 column layout system on flexbox- works both on website and apps pretty well
- Adv- build website pretty fast n easily, takes off all the testing part
- Dis- class bloat (a lot of stuff happening in html file) , loss of customization
- When to use frameworks
	- when making mobile first responsive website to put online fast (prototypes)
- how? by using link tag
- div container> div row> divs
	- ![[Pasted image 20240920105336.png]]
- don't need media queries cuz bootstrap does all the resposive work itself
- it has breakpoints
	- ![[Pasted image 20240921124542.png]]