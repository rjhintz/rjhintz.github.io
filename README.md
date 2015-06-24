# rjhintz.github.io
Personal web page fun
## Make a Basic Personal Web Page on Github
###Create Basic Web Page
####Create Repository
Create repo(sitory)

1. Choose a useful Github "handle." Consider
using your Twitter handle.
2. Create Github account, if necessary, then Logon to Github 
3. Create project repo as `<username>.github.io`, replacing `<username>`
with your Github username. 

####Initialize Repository

* Initialize repo with a README

####Create Top Level Index Page

1. Create an `index.html` page, clicking the plus icon next
to your repository name and typing the file name directly 
in the input box that appears.
2. Use a text editor to create this HTML "markup":
```html
<!doctype html>
<html>
	<head>
		<title>FirstName LastName</title>
	</head>
	<body>
		<nav>
    		<ul>
        		<li><a href="/">Home</a></li>
	        	<li><a href="/about">About</a></li>
        		<li><a href="/cv">CV</a></li>
        		<li><a href="/blog">Blog</a></li>
    		</ul>
		</nav>
		<div class="container">
    		<div class="blurb">
        		<h1>FirstName LastName</h1>
				<p>I'm FirstName LastName</p>
    		</div><!-- /.blurb -->
		</div><!-- /.container -->
		<footer>
    		<ul>
        		<li><a href="mailto:youremail@gmail.com">email</a></li>
        		<li><a href="https://github.com/<Githubusername>
				">github.com/,Githubusername</a></li>
			</ul>
		</footer>
	</body>
</html>
```
######Note
[notepad-plus-plus](https://notepad-plus-plus.org/) is worth 
considering as an editor, especially for Windows users.

####Commit Index Page
At the bottom of the page, use the text input area to add 
a description of your changes. Then use the button to commit the file.

####View Index Page
In a couple of minutes, perhaps less, the new web page will be ready at
`<username>.github.io`
###Style Web Page
Optional: To "style" the content, standard practice is 
to use a CSS style sheet.
####Create CSS Stylesheet
Go to your repository home and create a new file named `css/main.css`. 
The `css/` before the filename will automatically create 
a subdirectory called `css`.

Place the following into `main.css`. Note that currently this content 
includes many comments, some 
associated with currently empty associated content.
```css
/* External Style Sheet
 * Title: Main Theme
 * Version: 1.0.0
 * Author: FirstName LastName
*/
/* General stylesheet headings */
/* === Normalization === */
/* === Primary layout === */
/* === Secondary layout === */
/* === Tertiary layout === */
/* === Navigation === */
/* === Text-related === */
/* === Links and images === */
/* === General styles === */
/* === General classes === */
/* === Miscellaneous === */
/* */
/* Scope for "body" declaration: body and body's sub-elements */
body {
/* prioritized list of one or more font names.
   If a browser does not have access to the first, it uses the next. 
   Last of the 3 is generic */
    font-family:'Helvetica', 'Arial', 'Sans-Serif';
/* "initial" size is medium; 1 em (16 pixels) for normal text */	
	font-size: 1.0em;
	/* margin: space around an element’s border */
	margin-top: 5%;
    margin-bottom: 5%;
    margin-right: 10%;
    margin-left: 5%;
/*  width of an element’s content area 
	"auto" keyword lets the browser automatically calculate the width 
	works ok with tablet & mobile screens */
	   width: auto;
}
nav ul, footer ul {
/* get rid of list bullets */
    list-style: none;
	font-weight: bold;
}
nav ul li, footer ul li {
/* display list elements for nav and footer in one line */ 
    display: inline;
/* Standard HTML lists have a certain amount of left-indentation. 
The amount varies on each browser. 
Some browsers use padding (Mozilla, Netscape, Safari) and 
others use margins (Internet Explorer, Opera) to 
set the amount of indentation.
To remove this left-indentation consistently across all browsers, 
set both padding and margins to "0" for the "UL". */
	margin: 0;
	padding: 0;
/* spacing between list elements on single line */
    margin-right: 20px;
}
a {
/* visual effect for anchor text; see also hover behavior later */    
	text-decoration: none;
/* #999 short for #999999, mid gray */
    color: #999;
}
/* "hover" pseudo-class */
a:hover {
/* visual effect for text */ 
    text-decoration: underline;
}
p {
/* #333 short for #333333, darker gray */
    color: #333;
}
footer {
/* #d5d5d5d5d5d5 : light gray */
    border-top: 1px solid #d5d5d5;
    font-size: .8em;
}

/* ---------------------------------------------------- */
/* General comments on CSS */
/* list-style is the shorthand property for setting 
all the list properties */
/* "list-style: none" = 
	list-style-type: initial;
	list-style-position: initial;
	list-style-image: none; */

```
####Commit Stylesheet
Commit the `main.sss` stylesheet with an appropriate comment, 
such as "Initial".
####Link to the Stylesheet In the Index Page
Link to your CSS file inside your HTML document's `<head>`.
Go back to `index.html` and select the "Edit".

Add this text between `<head>` and `</head>` to create a 
link to `main.css` :
```html
!-- link to main stylesheet -->
		<link rel="stylesheet" type="text/css" href="/css/main.css">
```
###Add Use of Jekyll Static Site Generator
Jekyll is a static web site generator that uses templates. 
Instead of repeating the same navigation markup on every page, 
which would have to edited on every page if content is added or removed 
or if there's a change to 
the location of navigation item, 
a Jekyll layout can be called that will be used on all pages. 
###Setup for Jekyll
####Create Setup Files
Create a `.gitignore` file. This file tells Git to ignore the 
`_site` directory 
that Jekyll automatically generates each time you commit. 
Because this directory and all the files inside are written 
each time you commit, you do not want this directory under 
version control.

Add this line to the `.gitignore` file:
```
_site/
```
####Create Content Files
Create a `_config.yml` file. 

This example specifies the name of our site and version of Markdown:
```
	name: <FirstName LastName>
	markdown: kramdown
```

Also:

* Make a `_layouts` directory
* Create file inside it called `default.html`. 
```
<!doctype html>
<!-- advanced elements from h5bp_index.html -->
	<html>
		<head>
			<meta charset=utf-8>
			<meta http-equiv="x-ua-compatible" content="ie=edge">
			<title>{{ page.title }}</title>
			<meta name="viewport" content="width=device-width, initial-scale=1">
			<!-- link to external stylesheet(s) -->
			<link rel="stylesheet" type="text/css" href="/css/main.css">
		</head>
		<body>
			<nav>
	    		<ul>
	        		<li><a href="/">Home</a></li>
	<!--	        	<li><a href="/about">About</a></li> -->
	<!--        		<li><a href="/blog">Blog</a></li>   -->
	    		</ul>
			</nav>
			<div class="container">
			
			{{ content }}
			
			</div><!-- /.container -->		
			<footer>
	    		<ul>
	        		<li><a href="mailto:rjhintz@gmail.com">email</a></li>
					<li><a href="https://twitter.com/rjhintz">twitter</a></li>
	        		<li><a href="https://github.com/rjhintz">github.com/rjhintz</a></li>
				</ul>
			</footer>
		</body>
	</html>
```
####Update Index File
Update `index.html` to reflect use of Jekyll layout.

The file below is personalized with a photo image positioned on 
the right.
The border is explictly shown as 0pt none since 
some current browsers will otherwise include a border.
```
---
layout: default
title: Rich Hintz
---
<div class="blurb">
	<p>
		<a href="http://imgur.com/DzYcDag">
		<img src="http://i.imgur.com/DzYcDag.jpg" 
		title="source: imgur.com";
		style="border:0pt none;
		clear:right;
		float:right">
		</a>
	</p>
	<h3>Rich Hintz</h3>
	<p>Generally known as <em>rjhintz</em> on the network.
	<p>Things I'm interested in lately can be found in my Twitter feed and occasionally in these blogs:
		<ul>
			<li><a href="http://postconsumerwaste.blogspot.com">post consumer waste</a>, non-technology related </li>
			<li><a href="http://nextordermachine.blogspot.com">next order machine</a>, enterprise class technology </li>
			<li><a href="http://fiberinfrastructure.blogspot.com">fiber infrastructure</a>, for a focus on fiber optic infrastructure</li>
		</ul>
	</p>
	<p>Also, just like everyone else, I have the usual:
		<ul>
			<li><a href="http://www.flickr.com/photos/rjhintz/">flickr, </a>
				<a href="https://instagram.com/rjhintz/">Instagram, </a>
				and <a href="http://www.panoramio.com/user/186735">Panoramio </a>photos<br></li>
			<li><a href="http://www.youtube.com/rjhintz">YouTube videos</a></li>
			<li>and, somewhat less usual, interesting "<a href="http://www.wikiloc.com/wikiloc/user.do?name=rjhintz">tracks</a>" of journeys</li>
		</ul>
	</p>
</div><!-- /.blurb -->
``` 
###Optional
You can add a photo to your site fairly easily.
####Set Up an Image Hosting Site
[Imgur](www.imgur.com) is as good as any for low volumes, say <250,
of images.

I used an image sized at 243x162 pixels, which works ok.

Note that you don't have to "publish" to the wider Imgur community to
have the image be available as a link.
####
Optional: blur edges of photo.
[Quick Picture Tools](http://www.quickpicturetools.com/en/blur_edges/) 
is ok for this.
######Credit
Much of this material is adapted from
[Creating and Hosting a Personal Site on GitHub]
(http://jmcglone.com/guides/github-pages/) 
