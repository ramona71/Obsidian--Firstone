# Types
- Inline , Internal , External
- Inline - inside the tags (body/ para etc)
```css
<body style="background-color: black;">
    <p style="color: white;">Lorem ipsum dolor sit amet consectetur adipisicing elit. </p>  
</body>
```
- Internal - inside `head` tag
```css
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        body{
            background-color: black;
        }
        p{
            color: white;
        }
        h1{
            color: pink;
        }
    </style>
</head>
```
- External - as an external style sheet (external file)
- Best thing about style sheets is that u can apply them to more than one html file
```css
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">         // this
</head>
```
# Id and classes
- Id -> to apply css to a specific tag
- class -> to apply css to any no of tags
-  difference between class and id
	- id- only one element can have the same id
		-  id needs `#` before the name of id
	- class- multiple elements can have the same class name
		-  class needs `.` before the name of id
```css
p{                       // to every para
    color: cyan;
} 
#p1{                     // to a specific tag of the class
    color: yellow;
}
.p2{                     // to the class
	color: pink;         
}
```
- to select a specific element inside a class 
```css
.innerbox p{
color : white;                  selects only para elements of innerbox class
}
```
- Example
```css
p{
    color: cyan;
}
#p1{
    color: yellow;
}
.odd{
    color: brown;
}
.even{
    color: orange;
}

    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. </p>  
    <p id="p1">Man fucking yellow</p>
    <p class="odd">one</p>
    <p class="even">two</p>
    <p class="odd">Three</p>
    <p class="even">Four</p>
```
# Advanced shit
- Stack classes which are same using comma
```CSS
  .vid_stats, .vid_preview {
        font-size: 13px;
        color: rgb(96, 96, 96);
        margin-bottom: 20px;
        }
```
- combine two classes with
```css
	<div class="c1 c2"></div>
	<h1 class="class1 class2"> Hello</h1>
```
- Grouping of selectors(classes, id ,elements etc)
```css
selector, selector{            
color: white;
}
```
- child - constraint is that it is one level deep
```css
selector(parent)> selector(child){                   
}
ex:
.outerbox> p{
}
```
- desendent- can be applied to any no of levels deep
```css
selector selector{
}
ex:
remember to add class/id after element 
li#idname.box
```
- chaining - selecting where ALL selectors r true
```css
selectorselector{
}
```
- z- index to place the block on the top
```css
# for element
body{                            #use this to change bg of the page
}

# for class
.class_name{
}

#for id 
#id_name{
}

#to select all
*{
}

p[draggable]{
}
p[draggable="False"]{
}
```
