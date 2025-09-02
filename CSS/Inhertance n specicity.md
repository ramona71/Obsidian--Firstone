- inline is the final level 
## Position
```css
li{
color: red;
color: green;
}
li{
color: blue           # gets blue, lower it is the more priority given
}
```
## Specificity
- the order is
	- id
	- attribute
	- class
	- element
```css
#li_id{color:orange}          # gets orange
li[draggable]{color:yellow}
.class_li {color:pink}
li{color:blue}
```
## Type
- order
	- inline
	- internal
	- external
![[Pasted image 20240914183755.png]]
## Important key word
```css
color:red;
color:blue !important;                gets blue
```

The order here is 
	- important
	- type
	- specificity
	- position