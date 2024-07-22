
### HTML Elements

In the first lesson we have studied about tags and
things like start tag (opening a tag) and end tag
(closing a tag).

An HTML element is usually composed of a "Start
Tag', "Element Content" and an "End Tag".
Example:
```
<p> This is an element content. </p>
```
TRY IT YOURSELF By pasting it in your Editor. Output should look like

```
This is an element content.
```

The example HTML Element above is composed
of the following:
* start tag: ```<p>```
* element content: This is an element
content.
* end tag: ```</p>```
* 
Example2:
```
<h1> Learning HTML Elements </h1>
```

The example HTML Element above is composed
of the following:
* start tag: ```<h1>```
* element content: ```Learning HTML Elements```
* end tag: ```</h1>```


## Nested HTML Elements
There are some cases that an HTML element can
contain one or more HTML elements.
For you to better understand it look at the
example code below.
```
<p><i> Italicized text </i></p>
```
<b>TRY it yourself by Pasting the above on your editor. Output shold be italized<b>


The example nested HTML Elements above are
composed of the following:
* Start tag. ```<p>```
* Start tag. ```<i>```
* Element Content. ```Italicized text```
* End tag. ```</i>```
* End tag. ```</p>```

On the example above, there are two start tags and two end tags.
The second tag i.e. ```<i>```  italicizes the text within.
Empty Elements

## Empty Elements
Empty Elements are elements that do not have an
element content and an end tag.
A list of commonly used Empty Elements:
```<meta />
<link />
<img />
<br />
<hr />
<input />
```
The best practice in HTML Empty Elements is to
always put a forward slash / sign before the
greater than > sign.
In this way they are closed at their start tags
