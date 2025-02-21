
## **HTML Headings**  

HTML headings are used to define titles and subtitles on a webpage. They help structure the content, making it easier to read and navigate.  

### **Why Use Headings?**  
- **Improves Readability:** Headings break content into clear sections, making it more user-friendly.  
- **Boosts SEO:** Search engines use headings to understand page structure, which helps with rankings.  

### **Example of HTML Headings:**  

```html
<html>
<body>
    <h1>Main Heading</h1>
    <h2>Subheading</h2>
    <h3>Smaller Subheading</h3>
    <h4>Sub-Subheading</h4>
    <h5>Minor Subheading</h5>
    <h6>Smallest Heading</h6>
</body>
</html>
```

This example uses heading tags (`<h1>` to `<h6>`) to structure content from the most important (largest) to the least important (smallest). Each level represents the content hierarchy, ensuring a well-organized page.

### OUTPUT
<html>
<body>
    <h1>Main Heading</h1>
    <h2>Subheading</h2>
    <h3>Smaller Subheading</h3>
    <h4>Sub-Subheading</h4>
    <h5>Minor Subheading</h5>
    <h6>Smallest Heading</h6>
</body>
</html>

**Note:** The **"h"** in the heading tag should always be lowercase (e.g., `<h1>`, not `<H1>`).  

---

## **Levels of HTML Headings**  

HTML provides six levels of headings, each serving a unique role in content organization:  

### **`<h1>` – Main Heading (Largest)**  
- Represents the primary focus of the page (usually the title).  
- Best practice: Use **only one `<h1>`** per page for SEO.  
- Helps both users and search engines understand the main topic.  

### **`<h2>` – Subheadings**  
- Used to divide content into major sections.  
- If further subsections are needed, use `<h3>` to maintain a logical flow.  

### **`<h3>` to `<h6>` – Smaller Headings**  
- `<h3>` is used for subsections under `<h2>`.  
- `<h4>` to `<h6>` are for additional, less significant divisions.  
- `<h6>` is the smallest and least important heading.  

---

## **Customizing HTML Headings**  

You can modify heading styles using the **`style`** attribute in HTML.  

### **Example: Changing Heading Size**  

```html
<!DOCTYPE html>
<html>
    <head>
    <title>Changing Heading Font</title>
</head>
<body>

    <h1>Default H1 Heading</h1>

    <!-- Customize the size of the heading -->
    <h1 style="font-size: 50px">H1 with Larger Font</h1>

</body>
</html>
```

In this example, the **`font-size`** property increases the size of the second `<h1>` heading to **50 pixels**.  

### **Example: Changing Heading Color**  

```html
<!DOCTYPE html>
<html>

<head>
    <title>Changing Heading Color</title>
</head>

<body>

    <h1>Default H1 Heading</h1>

    <!-- Customize the color of the heading -->
    <h1 style="color: red;">H1 with Red Color</h1>

</body>

</html>
```  

In this example, the **`color`** property changes the text color of the second `<h1>` heading to **red**.

---

## **Best Practices for Using HTML Headings**  

✔ **Keep Headings Descriptive:** Each heading should accurately describe the section it introduces. This helps readers quickly understand the content.  

✔ **Avoid Overuse:** Use headings for **structuring content**, not just for styling or emphasis. For styling purposes, use **CSS** instead.  

---
