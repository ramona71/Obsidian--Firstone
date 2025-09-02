- Keep all the css in head section
- keep a button in para
```HTML
<p>paragraph of <button>hello</button> text</p>
```
	![[Pasted image 20240730133648.png]]
- everything that's not visible on page , goes into head
# All tags
```html
<html>           main tag
<head>
<title>
<body>
<link>         for favicon/ or any outside file
<!-- -->         comments

<h1>             titles
<h2>
<h3>             subtitles
<h4>             
<h5>
<h6>
<p>            dont' care if spaces or gaps are present in the para
<pre>          cares if spaces or gaps are present in the para

<hr>           adds line
<br>           adds a line gap (like endl)
<a>            anchor tag
<img>          images/ gif
<audio>
<source>
<video>

<b>
<i>
<u>
<big>
<small>
<sub>
<sup>          text formatting

<span>         inline container
<div>          block container

<ol>
<ul>
<li>
<dl>           description list
<dt>           word
<dd>           description

<table>
<tr>           table row
<th>           table header
<td>

<form>
<input>        by default , text type
``` 
# All attributes
```html
<a
 target ="_blank"                opens link in new page
 title ="Goes to google"         hover, shows title (for buttons, links)
 hfer                            hyperlink (to websites, other html/css files etc)
 src                             for image link
 height
 width
 alt                             if picture doesnt load , text displays
 target                          _blank
 type                            mp3/ wave   , mp4/webm , text, email, password, phone no
 controls                        for audio/vid
 autoplay
 muted
 loop
 rel  

action                            file name, done with backend lang
 
</a>
```
- class
	- ![[Pasted image 20240730134249.png]]
	- u can add same class to multiple buttons
	- tables
# Explanation
- href -. hyperlink (anchor tag)
	- to include websites links, other files (html/css etc) , mail etc 
```html
<!-- href examples -->
        <a href="https://www.google.com/"  target="_blank" title="Goes to googl">Google</a>
        <a href="Project1-lyrics.html">Song lyrics project</a>
        <a href="mailto:fakemail@fakeaf.com">Email me</a>
```
- img     -> images and gifs
	- write only height, width self adjusts
	- write both, image compresses
```html
<img src="Screenshot (265).png" height="200px" alt="Picture of isagi">

<img src="219176.gif" alt="isagi gif bro" height="200px">
```
- href and image -> when clicked on the image , the link opens
```html
<a href="https://bluelock.fandom.com/wiki/Yoichi_Isagi">
	<img src="Screenshot (265).png" height="200px" alt="Picture of isagi">
</a>
```
- audio 
	- controls -> ui/ux 
	- autoplay -> annoying (dont use it XXXX)
	- muted -> autoplaying but atleast it's muted
	- loop -> so it's looped
	- we include wave type too incase the website doesn't support mp3
	- if mp3 doesn't work, wave will play
```html
<audio controls autoplay muted loop>
  <source src="Audio images vids/JOJOOOOOOOOOOOOOOO.mp3" type="audio/mp3">
  <source src="Audio images vids/JOJOOOOOOOOOOOOOOO.wave" type="audio/wave">
</audio>

below shit is more that enough
<audio src="Audio images vids/JOJOOOOOOOOOOOOOOO.mp3" controls autoplay muted loop> </audio>
  or
<audio controls>
  <source src="Audio images vids/JOJOOOOOOOOOOOOOOO.mp3" type="audio/mp3">
</audio>
```
- video
	- format gotta be .mp4 / .webm / .ogg
	- same as audio tbh
	- if mp4 doesn't work, webm will play
```html
<video src="Audio images vids/Doukyuusei OST - Sora to Kaze no Waltz (空と風のワルツ).mp4" 
	   controls autoplay muted loop height="200px"></video>
or
<video controls autoplay muted loop height="200px">
     <source src="Audio images vids/Doukyuusei OST - Sora to Kaze no Waltz (空と風のワルツ).mp4" type="vid/ mp4">
     <source src="Audio images vids/Doukyuusei OST - Sora to Kaze no Waltz (空と風のワルツ).webm" type="vid/webm ">
</video>
```
- video inside anchor
	- when clicked on the vid, takes you to the link (you can keep the yt link of the vid)
```html
<a target="_blank" href="https://en.wikipedia.org/wiki/Classmates_(manga)">
	<video src="Audio images vids/Doukyuusei OST - Sora to Kaze no Waltz (空と風のワルツ).mp4"            controls autoplay muted loop height="200px"></video>
 </a>
```
- favicon  - icon beside title for webpage
	- gotta be .ico / .png /.gif / .jpg / .svg
	- put it in 'head' section
```html
 <link rel="icon" href="Audio images vids/frieren.jpeg">
```
- text formatting
	- makes text bold, italic, underlined etc
```html
<p>This is normal text</p>
<p>This is <b>bold</b> text</p>
<p>This is <i>italic</i> text</p>
<p>This is <u>underlined</u> text</p>
<p>This is <del>deleted</del> text</p>
<p>This is <big>big</big> text</p>
<p>This is<small>small</small> text</p>
<p>This is <sub>subscript</sub> text</p>
<p>This is <sup>superscript</sup> text</p>
<p>This is <tt>monospaced</tt> text</p>
<p>This is <mark>mark</mark> text</p>
<p>This is <mark  style="background-color: cyan;">mark</mark> text</p>
```
![[Pasted image 20250129223210.png]]
- span and div
	- span - inline
	- div- block
```html
<p><span style="background-color: tomato;">This is a span sentence</span></p>
<p><div style="background-color: cyan;">This is a div sentence</div></p>

<p>Lorem, ipsum dolor sit amet consectetur adipisicing elit.  <span style="background-color: tomato;">In deleniti voluptatem eligendi nesciunt tempore nisi mollitia voluptas accusamus, asperiores similique tenetur quisquam?</span></p>

<p>Lorem ipsum dolor sit amet consectetur adipisicing elit.<div style="background-color: cyan;">Quod tempore unde tempora rerum, nulla sapiente, placeat recusandae voluptates omnis ex cumque commodi deserunt officia porro eveniet ratione eius qui earum.</div></p>
```
![[Pasted image 20250129224051.png]]
- lists  
	- unordered  `<ul>`
	- ordered  `<ol>`
	- list item `<li>`
	- nesting lists
```html
<ul>
	<li>Orange</li>
	<li>Cofee supplies </li>
		<ol>
            <li>Coffee beans</li>
            <li>Sugar</li>
            <ul>
                <li>White sugar</li>
                <li>brown sugar</li>
            </ul>   
		</ol>
</ul>
```
![[Pasted image 20250129230954.png]]
- Description list `dl`
	- word `dt` - it's description  `dd`
```html
 <dl>
    <dt>dragon</dt>
    <dd>Dragon got wings and shit and it's cool af cuz it breathes fire from it's mouth yyyyyyyyy       </dd>
    <dt>Witch</dt>
    <dd>Cool af too and womean only ig?? man i want a witch so baddddd</dd>
</dl>
```
![[Pasted image 20250129231548.png]]
- table
```html
<table border=2;>
            <tr align="center" style="background-color: aqua;">
                <th width="100" >Sunday</th>
                <th>Monday</th>
                <th>Tuesday</th>
                <th>Wednesday</th>
                <th>Thursday</th>
                <th>Friday</th>
                <th>Sunday</th>
            </tr>
            <tr align="center" style="background-color: rgb(207, 248, 248); ">
                <td>Closed</td>
                <td>Open</td>
                <td>Open</td>
                <td>Open</td>
                <td>Closed</td>
                <td>Open</td>
                <td>Closed</td>
            </tr>
</table>
```
- button
	- keep it inside a anchor now it can take you anywhere
```html
 <a href="Project1-lyrics.html">
     <button onclick="Some_js_fxn()" style="background-color: pink; color: blue ; font-size: 20px; width: 150px; border:2px solid black;">Song lyrics page</button>
</a>
```
- Form
	- `<form>`
	- `action` attribute , sends data to a file, done with backend lang(like php)
	- `method` specifies if it's a get/ post request
		- POST- > confidential data
		- GET -> insensitive data
	- `for` of `<label>` and `id` of `<input>` should be the same !!
```html
```
- m
```html
```