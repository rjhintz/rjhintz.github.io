# rjhintz.github.io
Personal web page fun
## Make a Basic Personal Web Page on Github
###Create Basic Web Page
####Create Repository
Create repo(sitory)

1. Logon to Github 
2. Create project repo as `<username>.github.io`, replacing `<username>`
with your Github username. 
####Initialize Repository

* Initialize repo with a README
####Create Top Level Index Page

1. Create an `index.html` page, clicking the plus icon next to your repository
name and typing the file name directly in the input box that appears.
2. Use text editor to create this markup:
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
        		<li><a href="https://github.com/<Githubusername>">github.com/,Githubusername</a></li>
			</ul>
		</footer>
	</body>
</html>
```
####Commit Index Page
At the bottom of the page, there is a text input area to add 
a description of your changes and a button to commit the file.

####View Index Page
In a couple of minutes, perhaps less, the new web page will be ready at
`<username>.github.io`
###Style Web Page
Optional: To "style" the content, standard practice is to use a CSS style sheet.
####Create CSS Stylesheet
Go to your repository home and create a new file named `css/main.css`. 
The `css/` before the filename will automatically create a subdirectory called `css`.

Place the following into `main.css`:
```
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
Some browsers use padding (Mozilla, Netscape, Safari) and others use margins 
(Internet Explorer, Opera) to set the amount of indentation.
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
/* list-style is the shorthand property for setting all the list properties */
/* "list-style: none" = 
	list-style-type: initial;
	list-style-position: initial;
	list-style-image: none; */

```
####Commit Stylesheet
Commit the `main.sss` stylesheet with an appropriate comment, such as "Initial".
####Link to the Stylesheet In the Index Page
Link to your CSS file inside your HTML document's `<head>`.
Go back to `index.html` and select the "Edit".

Add this text between `<head>` and `</head>` to create a link to `main.css` :
```
!-- link to main stylesheet -->
		<link rel="stylesheet" type="text/css" href="/css/main.css">
```
###Add Use of Jekyll Static Site Generator

###Setup for Jekyll

####Create Setup Files

####Create Content Files

####Update Index File


Much of this material is adapted from
[Creating and Hosting a Personal Site on GitHub](http://jmcglone.com/guides/github-pages/) 
