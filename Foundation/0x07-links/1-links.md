

# **HTML Links & Hyperlinks**  
 

HTML links, also known as **hyperlinks**, are defined using the `<a>` (anchor) tag. These links are essential for **navigating between web pages**, directing users to other sites, documents, or sections within the same page.  

## **Basic Syntax of an HTML Link:**  
```html
<a href="https://www.example.com">Visit Example</a>
```
**Note:** A hyperlink can be applied to **text, images, buttons, or other HTML elements**.  

---

## **1. Creating a Simple HTML Link**  
The following example creates a **clickable link** that redirects users to **CodeBadger** when clicked:  

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>HTML Links</title>
</head>
<body>
    <p>Click the link below to visit CodeBadger:</p>
    <a href="https://www.codebadgertech.com/">CodeBadger</a>
</body>
</html>
```
### OUTPUT:
<!DOCTYPE html>
<html lang="en">
<head>
   
</head>
<body>
    <p>Click the link below to visit CodeBadger:</p>
    <a href="https://www.codebadgertech.com/">CodeBadger</a>
</body>
</html>

<hr>

### **Default Link Styling:**  
- **Unvisited links** appear **blue** and underlined.  
- **Visited links** appear **purple** and underlined.  
- **Active links** appear **red** while being clicked.  

---

## **2. Using the `target` Attribute in Links**  
The `target` attribute defines **where the linked page opens**.  

### **Available Values for `target`:**  

| **Attribute** | **Function** |
|--------------|-------------|
| `_blank` | Opens the link in a **new tab/window**. |
| `_self` | Opens the link in the **same tab** (default behavior). |
| `_parent` | Opens the link in the **parent frame**. |
| `_top` | Opens the link in the **entire window**, breaking out of frames. |
| `framename` | Opens the link in a **specified frame**. |

### **Example: Different Target Attributes**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Target Attribute Example</title>
</head>
<body>
    <h3>Opening Links in Different Ways</h3>

    <p>Opens CodeBadger in a **new tab**:</p>
    <a href="https://www.codebadger.org" target="_blank">Open in New Tab</a>

    <p>Opens CodeBadger in the **same tab**:</p>
    <a href="https://www.codebadger.org" target="_self">Open in Same Tab</a>

    <p>Opens CodeBadger in the **parent frame**:</p>
    <a href="https://www.codebadger.org" target="_parent">Open in Parent Frame</a>

    <p>Opens CodeBadger in the **full window**:</p>
    <a href="https://www.codebadger.org" target="_top">Open in Full Window</a>
</body>
</html>
```

---

## **3. Linking Different HTML Elements**  
You can create **clickable links** on various elements like images, email addresses, phone numbers, and files.  

### **Common Types of Hyperlinks**  

| **Type of Link** | **Example Code** |
|------------------|-----------------|
| **Linking an Image** | `<a href="https://www.codebadger.org"><img src="logo.png" alt="CodeBadger Logo"></a>` |
| **Email Link** | `<a href="mailto:contact@codebadger.org">Email CodeBadger</a>` |
| **Phone Number Link** | `<a href="tel:+1234567890">Call CodeBadger</a>` |
| **Download File Link** | `<a href="document.pdf" download>Download PDF</a>` |

### **Example: Linking an Image & Email**
```html
<h3>Clickable Image Link</h3>
<a href="https://www.codebadger.org">
    <img src="logo.png" alt="Visit CodeBadger" width="200">
</a>

<h3>Send an Email</h3>
<a href="mailto:support@codebadger.org">Contact Support</a>
```

---

## **4. Adding Titles to Links**
The `title` attribute provides **extra information when hovering over a link**.

### **Example:**
```html
<a href="https://www.codebadgertech.com/" title="Click to visit CodeBadger">Visit CodeBadger</a>
```
🔹 When the user hovers over the link, <a href="https://www.codebadgertech.com/" title="Click to visit CodeBadger">Visit CodeBadger</a> it appears as a tooltip.

---

## **5. Creating Page Anchors (Jump Links)**
Jump links allow users to **navigate to specific sections** of a webpage.

### **Example:**
```html
<a href="#section2">Go to Section 2</a>

<h2 id="section2">Section 2</h2>
<p>This is the second section of the page.</p>
```
🔹 Clicking the link **jumps** to `"Section 2"` on the same page.

---


## **Conclusion**  
Hyperlinks are essential for **web navigation**. Using `<a>` tags, you can create **text links, image links, email links, phone links, and download links**. Styling them with **CSS** improves user experience.

 🚀
