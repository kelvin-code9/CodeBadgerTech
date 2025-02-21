
## **HTML Images**  
The HTML `<img>` tag is used to embed an image in web pages by linking them. It creates a placeholder for the image, defined by attributes like `src`, `width`, `height`, and `alt`, and does not require a closing tag.  

### **Ways to Insert Images in a Webpage**  
There are two ways to insert images into a webpage:  
1. **By providing a full path (URL)** to access an image from the internet.  
2. **By providing a relative file path** from the location of the current web page file.  

### **Basic Example of the `<img>` Tag**  

```html
<!DOCTYPE html>
<html>
<body>
    <img src="https://www.codebadgertech.com/sample-image.png" 
         alt="CodeBadger image" />
</body>
</html>
```

### **Explanation:**  
- The `<img>` tag is used to embed an image into the webpage.  
- **`src` attribute**: Specifies the **image source URL**, which loads the image when the webpage is accessed.  
- **`alt` attribute**: Provides alternative text for the image, which is useful for **accessibility** and when the image **fails to load**.  

---

## **HTML `<img>` Tag Attributes**  

| Attribute      | Description |
|---------------|-------------|
| **src**       | Specifies the **path** to the image file. |
| **alt**       | Provides **alternative text** when the image cannot be displayed. |
| **crossorigin** | Allows importing images from **third-party sites** with cross-origin access. |
| **height**    | Specifies the **height** of the image. |
| **width**     | Specifies the **width** of the image. |
| **ismap**     | Specifies an image as a **server-side image map**. |


---

## **1. HTML `<img>` Tag – `alt` Attribute**  
The `alt` attribute in the `<img>` tag provides a **text alternative** when an image fails to load. It improves **accessibility** for users with slow internet or screen readers.  

```html
<!DOCTYPE html>
<html>
<body>
    <img src="https://www.codebadgertech.com/logo.png"
        alt="This is CodeBadger logo" />
</body>
</html>
```

---

## **2. Set Image Size – `width` and `height` Attributes**  
The `width` and `height` attributes specify an image's **dimensions** in pixels.  

```html
<!DOCTYPE html>
<html>
<body>
    <img src="https://www.codebadgertech.com/logo.png"
        alt="CodeBadger logo" 
        width="300" 
        height="300" />
</body>
</html>
```

---

## **3. Adding Titles to an Image**  
The `title` attribute displays a **tooltip** when users hover over an image.  

```html
<!DOCTYPE html>
<html>
<body>
    <img src="https://www.codebadgertech.com/logo.png"
        alt="CodeBadger logo" 
        width="200" 
        height="200" 
        title="Logo of CodeBadger" />
</body>
</html>
```

---

## **4. Setting Image Borders**  
By default, images **do not have borders**. The `border` property allows customization.  

```html
<!DOCTYPE html>
<html>
<body>
    <img src="https://www.codebadgertech.com/logo.png"
        alt="CodeBadger logo" 
        width="200" 
        height="200" 
        border="5" />
</body>
</html>
```

---

## **5. Aligning an Image**  
The `align` attribute allows **horizontal alignment** of an image.  

```html
<!DOCTYPE html>
<html>
<body>
    <img src="https://www.codebadgertech.com/logo.png"
        alt="CodeBadger logo" 
        align="right" />
</body>
</html>
```

---

## **6. Adding an Image as a Link**  
To make an image **clickable**, wrap the `<img>` tag inside an `<a>` tag.  

```html
<!DOCTYPE html>
<html>
<body>
    <a href="https://www.codebadgertech.com/">
        <img src="https://www.codebadgertech.com/logo.png"
            alt="CodeBadger logo" />
    </a>
</body>
</html>
```

---

## **7. Adding an Animated Image (GIFs)**  
Animated images can be embedded using the `<img>` tag with a `.gif` file.  

```html
<!DOCTYPE html>
<html>
<body>
    <img src="https://www.codebadgertech.com/animated.gif" 
         alt="Animated Image" 
         style="width: 200px; height: 200px" /> 
</body>
</html>
```

---

## **8. Common Image Formats in HTML**  
Different image file formats supported by browsers:  

| S.No. | File Type | Extension |
|-------|----------|-----------|
| 1 | **PNG** (Portable Network Graphics) | `.png` |
| 2 | **JPEG** (Joint Photographic Experts Group) | `.jpg`, `.jpeg`, `.jfif`, `.pjpeg`, `.pjp` |
| 3 | **SVG** (Scalable Vector Graphics) | `.svg` |
| 4 | **GIF** (Graphics Interchange Format) | `.gif` |
| 5 | **ICO** (Microsoft Icon) | `.ico`, `.cur` |
| 6 | **APNG** (Animated PNG) | `.apng` |

---

## **Tips for Using HTML Images Effectively**  

1. **Optimize Image Sizes**  
   - Large images slow down **page loading times**.  
   - Compress images and use appropriate formats (`JPEG` for photos, `PNG` for transparent graphics).  

2. **Use Descriptive Alt Text**  
   - Improves **accessibility** for screen reader users.  
   - Acts as **anchor text** in text-only browsers.  

3. **Maintain Aspect Ratios**  
   - Avoid **distorting** images unless required.  
   - Ensures **good visual aesthetics**.  


---

### **Final Notes**  
This guide covers **all essential concepts** of HTML images, including **embedding, attributes, styling, alignment, and responsiveness**. By following these best practices, you can **enhance user experience and website performance**.  

🚀
