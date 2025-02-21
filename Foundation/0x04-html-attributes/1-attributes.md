# HTML Attributes
HTML Attributes are special words used within the opening tag of an HTML element. They provide additional information about HTML elements. HTML attributes are used to configure and adjust the element’s behavior, appearance, or functionality in a variety of ways.

Each attribute has a name and a value, formatted as name=”value”. Attributes tell the browser how to render the element or how it should behave during user interactions.

Syntax:
```
<tagname attribute_name = “attribute_value”> content… </tagname>
```


Code Example of Using HTML Attributes
This HTML code demonstrates the use of the src attribute within the <img> tag to display an image.

```
<!DOCTYPE html>
<html>

<head>
    <title>HTML img src Attribute</title>
</head>

<body>
    <img src="https://www.codebadgertech.com/images/2.svg">
</body>

</html>
```

In this example:

Tag : ```<img>```

Attribute : ```src```

Value of Attribute : ```https://www.codebadgertech.com/images/2.svg```

Purpose : The <img> tag is used for embedding images in an HTML page. The src attribute within the <img> tag specifies the path to the image file you wish to display. This attribute is crucial as it directs the browser to the image’s location on the internet or a local directory.

Components of Attribute
An HTML attribute consists of two primary components:

1. attribute_name: This is the name of the attribute, which specifies what kind of additional information or property you are defining for the element. Common attribute names include href, src, class, id, etc.

2. attribute_value: The value is assigned to the attribute to define the specific setting or behavior. It is always placed in quotes.

Types of HTML Attributes
HTML attributes can be broadly categorized based on their function and the type of elements they modify. For example –

Global Attributes
These attributes can be used with any HTML element (though their effects might vary based on the element):

| Attribute        | Description |
|-----------------|-------------|
| class          | Groups elements and allows styling. |
| style          | Inline CSS styles. |
| src           | Specifies the source of various resources, such as image URLs for the img element, video URLs for the video element, and audio URLs for the audio element. |
| contenteditable | Determines whether the content within the element is editable. |
| role          | Specifies the element’s accessibility role. |
| tabindex       | Determines the order of focus during keyboard navigation. |
| id           | Assigns a unique identifier to an element, allowing targeting with CSS or JavaScript. |
| href         | Defines the hyperlink destination within the a element, enabling navigation. |
| alt          | Provides alternative text for images, essential for accessibility and SEO. |
| title        | Creates a tooltip that appears when a user hovers over the element. |
| lang         | Specifies the language of the element’s content, aiding with translation and accessibility. |

Some other main types of HTML attributes are:
```
- Event Attributes – These define the actions to be taken on specific browser events.
- Input Attributes – Specific to input elements within <form> tags.
- Image Attributes – Specific to the <img> element for handling images.
- Link Attributes – Specific to linking elements like <a> and <link>.
- Table Attributes – Used with table elements like <table>, <th>, <tr>, and <td>.
- Style Attributes – Define styles directly on an element.
- Media Attributes – Related to media elements like <audio> and <video>.
- Accessibility Attributes – Help improve accessibility, such as alt for images and aria-* attributes.
- Meta Attributes – Used with meta elements to specify metadata like charset.
```

# Common HTML Attributes

Let’s explore some of the most commonly used HTML attributes:

## 1. HTML style Attribute
The `style` attribute is used to apply inline CSS to an HTML element, allowing direct customization of properties like font size, color, alignment, and more.

### Example:
The following example demonstrates different style properties applied directly to HTML elements.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Style Attribute</title>
</head>
<body>
    <h2 style="font-family:Chaparral Pro Light;">Hello CodebadgerTech.</h2>
    <h3 style="font-size:20px;">Hello CodebadgerTech.</h3>
    <h2 style="color:#8CCEF9;">Hello CodebadgerTech.</h2>
    <h2 style="text-align:center;">Hello CodebadgerTech.</h2>
</body>
</html>
```
### OUTPUT
![image](https://github.com/user-attachments/assets/100284f3-0fcd-457b-a9ea-58cc47789d4c)

## 2. HTML id Attribute
The `id` attribute assigns a unique identifier to an HTML element, making it easier to apply styles or manipulate it with JavaScript.

### Example:
The example below demonstrates how to use the `id` attribute with CSS styling in the `<head>` section.

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        #codebadger {
            color: green;
        }
    </style>
</head>
<body>
    <h1 id="codebadger">Welcome to CodebadgerTech</h1>
</body>
</html>
```
### OUTPUT
![image](https://github.com/user-attachments/assets/8de4c234-6202-402c-adb0-cb9313144865)



## 3. HTML alt Attribute
The `alt` attribute provides alternative text for an image in case it fails to load. This improves accessibility and SEO.

### Example:
```html
<!DOCTYPE html>
<html>
<head>
    <title>HTML img alt Attribute</title>
</head>
<body>
    <img src="https://www.codebadgertech.com/images/2.svg" alt="The Logo"><br>
    <img src="" alt="Since the src value is blank, the alt value is displayed">
</body>
</html>
```
### OUTPUT
![image](https://github.com/user-attachments/assets/17d044db-6f89-4299-b931-9d0b23c9aef2)


## 4. HTML width and height Attribute
The `width` and `height` attributes define the dimensions of an image in pixels.

### Example:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Width and Height</title>
</head>
<body>
    <img src="https://www.codebadgertech.com/images/2.svg"
         width="300px"
         height="100px">
</body>
</html>
```
### OUTPUT
![image](https://github.com/user-attachments/assets/bdc0978d-f7fb-4d53-a0e1-2488ab78562e)


## 5. HTML title Attribute
The `title` attribute provides additional information about an element. The tooltip appears when the user hovers over it.

### Example:
```html
<!DOCTYPE html>
<html>
<head>
    <title>HTML title Attribute</title>
</head>
<body>
    <h3 title="Hello CodebadgerTech">Hover to see the effect</h3>
</body>
</html>
```

## 6. HTML href Attribute
The `href` attribute, used in `<a>` tags, specifies the URL a link navigates to. Adding `target="_blank"` opens the link in a new tab.

### Example:
```html
<!DOCTYPE html>
<html>
<head>
    <title>Link Attribute</title>
</head>
<body>
    <a href="https://www.codebadgertech.com/">Click to open in the same tab</a><br>
    <a href="https://www.codebadgertech.com/" target="_blank">Click to open in a different tab</a>
</body>
</html>
```
### OUTPUT
![image](https://github.com/user-attachments/assets/9e8245ff-d93c-4472-a1ca-8f6f6042bd21)



### Important Points About HTML Attributes

1. **Always Use Lowercase Attributes:**
   - You can use either uppercase or lowercase letters for defining attributes. However, it is recommended to use lowercase attributes as per W3C guidelines for consistency and better readability.

2. **Always Quote Attribute Values:**
   - The HTML standard does not require quotes around attribute values in certain situations. However, W3C recommends always using quotes for attribute values, and quotes are mandatory for stricter document types like XHTML. Using quotes helps avoid errors, especially when the attribute value contains spaces or special characters.

3. **Declare Quote as an Attribute Value:**
   - You can use either single (') or double (") quotes for attribute values in HTML, but it is essential to be consistent throughout your document. If the attribute value contains a double quote, then use single quotes to enclose it, and vice versa. For simplicity, it is a good practice to consistently use double quotes, as it aligns with the convention used in many HTML examples and tutorials.

