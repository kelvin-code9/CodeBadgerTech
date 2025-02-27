# **HTML Iframes - Notes**  

## **What is an Iframe?**  
An **iframe (Inline Frame)** is an HTML element used to embed another webpage inside the current webpage. It allows you to display external content such as:  
✅ Other websites  
✅ Google Maps  
✅ YouTube videos  
✅ PDFs and documents  

### **Basic Syntax:**  
```html
<iframe src="https://www.example.com" width="600" height="400"></iframe>
```
- `src`: The URL of the page to be embedded  
- `width` & `height`: Controls the size of the iframe  

---

## **Common Uses of Iframes**
### **1. Embedding a YouTube Video**  
```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/dQw4w9WgXcQ" allowfullscreen></iframe>
```

### **2. Displaying a Google Map**  
```html
<iframe src="https://www.google.com/maps/embed?..."></iframe>
```

### **3. Loading a PDF Document**  
```html
<iframe src="document.pdf" width="800" height="600"></iframe>
```

---

## **Iframe Attributes**
| Attribute | Description |
|-----------|-------------|
| `src` | URL of the embedded content |
| `width` & `height` | Defines the iframe’s size |
| `frameborder="0"` | Removes the border |
| `allowfullscreen` | Enables fullscreen mode for videos |
| `scrolling="no"` | Disables scrolling (not recommended) |

---

## **Security Concerns**
🔴 **Avoid embedding untrusted websites** – They might contain harmful scripts.  
🔴 **Some websites block iframes** – They use `X-Frame-Options` to prevent embedding.  

---

## **Iframe vs. Embed vs. Object**
| Tag | Purpose |
|------|---------|
| `<iframe>` | Embeds webpages |
| `<embed>` | Used for multimedia (audio, video, PDFs) |
| `<object>` | Can embed various file types but is less common |

---

### **Practice Task:**  
Create a webpage that:  
✅ Embeds a YouTube video  
✅ Displays a Google Map  
✅ Loads a local PDF file  

📌 Save as **iframe_example.html**  

---

### sample code 
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Learning Iframes</title>
    <style>
        body {
            font-size: 18px;
            color: #333;
            font-family: Arial, sans-serif;
            text-align: center;
        }

        h1 {
            color: #007BFF;
        }

        iframe {
            margin: 20px 0;
        }
    </style>
</head>

<body>
    <h1>Understanding HTML Iframes</h1>
    <p>An iframe allows us to embed other web pages, videos, or maps into our own page.</p>

    <h2>Google Maps Example</h2>
    <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3151.835434509197!2d144.96305771531686!3d-37.81627974202162!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x6ad642af0f11fd81%3A0xf4cbae3e4b2a341b!2sMelbourne%2C%20Australia!5e0!3m2!1sen!2sus!4v1605706101601!5m2!1sen!2sus"
        width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy">
    </iframe>

    <h2>Embedded YouTube Video</h2>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/dQw4w9WgXcQ?si=WUnXiW39O7o_Se9w"
        title="YouTube video player" frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
    </iframe>
</body>

</html>
```

###OUTPUT
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Learning Iframes</title>
    <style>
        body {
            font-size: 18px;
            color: #333;
            font-family: Arial, sans-serif;
            text-align: center;
        }

        h1 {
            color: #007BFF;
        }

        iframe {
            margin: 20px 0;
        }
    </style>
</head>

<body>
    <h1>Understanding HTML Iframes</h1>
    <p>An iframe allows us to embed other web pages, videos, or maps into our own page.</p>

    <h2>Google Maps Example</h2>
    <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3151.835434509197!2d144.96305771531686!3d-37.81627974202162!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x6ad642af0f11fd81%3A0xf4cbae3e4b2a341b!2sMelbourne%2C%20Australia!5e0!3m2!1sen!2sus!4v1605706101601!5m2!1sen!2sus"
        width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy">
    </iframe>

    <h2>Embedded YouTube Video</h2>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/dQw4w9WgXcQ?si=WUnXiW39O7o_Se9w"
        title="YouTube video player" frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
    </iframe>
</body>

</html>
