## HTML5 Sections
HTML Sections group different HTML Elements
(e.g. text, heading, paragraphs, images etc.)
together.
Creating sections is essential for organizing and
styling web contents.

### Elements Used for HTML Sections
* ```<div>```: used to group large group of HTML elements like navigation, header, main content, footer, images; it is a block-level element
 
* ```<span>``` : used to group smaller group of text in a paragraph and few HTML elements; it is an inline element

### HTML5 Semantic Elements
Here is a list of HTML5 Semantic Elements that
work similarly with the <div> element:
* ```<nav>```: defines a navigation list or bar
* ```<header>```: defines a header
* ```<main>```: defines the main content
* ```<footer>```: defines a footer
 
Using these HTML5 semantic elements is not
mandatory but it is still a good practice and
recommended because it might help in Search
Engine Optimization (SEO) plus your code will be
more understandable.

Example on how to use div. Copy the code to your browser and understand how it truly works 
```
<!DOCTYPE html>
<html>
<head>
   <title> Try It Yourself </title>
</head>
<body>
   <!-- let's make divs with different contents and style -->
   
   <div style="background: gold; width: 400px; height: 400px">
       <p> This is a paragraph. </p>
   </div>
   
   <div style="background: yellow; width: 400px; height: 400px">
   	<p> This is a paragraph. </p>
   </div>
</body>
</html> 
```

Example on how to use span. Copy the code to your browser and understand how it truly works 

```
<!DOCTYPE html>
<html>
<head>
   <title> Try It Yourself </title>
</head>
<body>
   <!-- Let's put some text inside a span and style them differently -->
   
   <p> 
   	<span style="font-size: 30px">I</span> <span style="color: blue">am a paragraph</span> <span style="color: red">and my words are styled</span> <span style="color: green">differently using</span> <span style="color: gold"> the span element.</span>
   </p>
</body>
</html>
```

As you can see the <span> elements did
not separate the paragraph into multiple
lines.
Always Remember. The ```<span>``` element
is good for styling and organizing few and
inline elements while the ```<div>``` element is
good for larger elements.
