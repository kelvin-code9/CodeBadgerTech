## HTML Attributes
 HTML attributes are special words used inside the opening tag of an HTML element to control the element's behavior or provide additional information about the element. Attributes come in name/value pairs, where the name is the attribute name and the value is the attribute value, enclosed in double or single quotes

### Important Things to Remember
* HTML attributes are found in HTML tags.
* HTML attributes only appear at start tags. It
will never be on end tags.
* HTML elements can have multiple
attributes.
* HTML attributes are composed of
name/value pairS.
* There are some attributes that can be used
on all HTML Elements though they may not
have effects on some elements. They are
called Global Attributes

An HTML attribute is composed of:
* an attribute name
* an equal = sign
* a value surrounded by quotation marks
"value"

It looks like this: ```attributename="value"```
You can also use single quotation marks
depending on the situation esp. when the value
contains double quotes.
We will only use double quotation marks
throughout the entire tutorial.
In this lesson we are going to learn some HTML
Attributes with examples.

### we have a lot of attributes but we will be picking them bit by bit

* Attribute lang:
```
  <! DOCTYPE html>
  <html lang="en-US">
   <!-- html document/file content goes
</html>
```
We use the lang attribute to define the language
of an HTML file.
The language defined above is American English.

* Attribute href:
```
<a href="http://www.example."> Go to http://www.example.com </a>
```

Links are defined using the anchor <a> element.
On the example above we used the ***href
attribute*** to tell the browser where to go.
When clicked the user will be redirected to
http://www.example.com.


* The src Attribute

 The ```<img>``` tag is used to embed an image in an HTML page. The src attribute specifies the path to the image to be displayed: example
 
 ```<img src="img_girl.jpg">```


* The width and height Attributes

The <img> tag should also contain the width and height attributes, which specify the width and height of the image (in pixels):

```<img src="img_girl.jpg" width="500" height="600">```

copy and paste on your browser

* The alt Attribute

The required alt attribute for the <img> tag specifies an alternate text for an image, if the image for some reason cannot be displayed. This can be due to a slow connection, or an error in the src attribute, or if the user uses a screen reader.

```<img src="img_girl.jpg" alt="Girl with a jacket">```

* The title Attribute

The title attribute defines some extra information about an element.

The value of the title attribute will be displayed as a tooltip when you mouse over the element

```<p title="I'm a tooltip">This is a paragraph.</p>``` copy and run the code on your browser to see how it works


* Attribute style:

```
  <p style="font-size: 40px; color: gold">
      I am a paragraph with a size of 40 pixels    and my color is gold.
  </p>
  ```
  
 
 the attribute ***style*** is used to add styles to our html. font-size is a property that is used to set the size of the text, while 40px is the value of the property. color is also a property snd gold is the value. copy the code to ur visual studio sbd text run it

## Summary

* All HTML elements can have attributes

* The href attribute of <a> specifies the URL of the page the link goes to

* The src attribute of <img> specifies the path to the image to be displayed

* The width and height attributes of <img> provide size information for images

* The alt attribute of <img> provides an alternate text for an image

* The style attribute is used to add styles to an element, such as color, font, size, and more

* The lang attribute of the <html> tag declares the language of the Web page

* The title attribute defines some extra information about an elemen
