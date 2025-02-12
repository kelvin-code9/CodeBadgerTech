
---

# **HTML Paragraphs**  

In HTML, a paragraph is a block of text enclosed within the `<p>` tag. It helps in organizing content into readable sections. The `<p>` tag is widely used to format text and make it easier to display on a webpage.  

## **Syntax:**  
```html
<p> Content </p>
```

## **How HTML Paragraphs Are Displayed**  
When you wrap text inside the `<p>` tag, the browser automatically:  
- Adds space before and after the paragraph for better readability.  
- Breaks the text into a distinct block, making it easy to follow.  

---

## **Example 1: Basic Paragraphs in HTML**  

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>The p tag</title>
</head>
<body>
    <p>A Computer Science portal for CodeBadger Students.</p>
    <p>It contains well-written, well-thought-out articles.</p>
</body>
</html>
```

### **Output:**  

A Computer Science portal for CodeBadger Students.  

It contains well-written, well-thought-out articles.  

---

## **Key Properties of the `<p>` Tag:**  
- **Automatic Space Handling:** The browser compresses multiple spaces into a single space.  
- **Line Compression:** If extra line breaks are added manually, the browser ignores them and displays the text in a single block.  
- **Block-Level Display:** The `<p>` tag is a block-level element, meaning each paragraph appears on a new line.  

---

## **Example 2: Handling Multiple Lines in a Paragraph**  

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML p tag</title>
</head>
<body>
    <p>
        This paragraph has multiple lines.
        But HTML reduces them to a single line,
        omitting the carriage return we have used.
    </p>
    <p>
        This paragraph has multiple spaces.
        But HTML reduces them all to a single space.
    </p>
</body>
</html>
```

### **Output:**  

This paragraph has multiple lines. But HTML reduces them to a single line, omitting the carriage return we have used.  

This paragraph has multiple spaces. But HTML reduces them all to a single space.  

---

## **Using the `<br>` Tag for Line Breaks**  
The `<br>` tag creates a line break within a paragraph without starting a new one.  

### **Syntax:**  
```html
<br>
```

### **Example: Using `<br>` to Insert Line Breaks**  

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML paragraph</title>
</head>
<body>
    <p>
        This paragraph has multiple<br>
        lines. But HTML reduces them<br>
        to a single line, omitting<br>
        the carriage return we have used.
    </p>
</body>
</html>
```

### **Output:**  

This paragraph has multiple  
lines. But HTML reduces them  
to a single line, omitting  
the carriage return we have used.  

---

## **Using the `<hr>` Tag for Section Breaks**  
The `<hr>` tag creates a horizontal line to visually separate sections of a webpage.

### **Syntax:**  
```html
<hr>
```

### **Example: Using `<hr>` to Separate Sections**  

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Horizontal Rule Example</title>
</head>
<body>
    <h1>Welcome to My Website</h1>
    <p>
        CodeBadger is a leading Organization that provides computer science resources and coding challenges.
    </p>
    <hr>
    <p>
        This platform helps developers improve their programming skills through interactive problems.
    </p>
</body>
</html>
```

### **Output:**  

**Welcome to My Website**  

CodeBadger is a leading Organization that provides computer science resources and coding challenges. 

*— (Horizontal Line) —*  

This platform helps developers improve their programming skills through interactive problems.  

---

## **Aligning Paragraphs**  
Although the `align` attribute was previously used to align text inside a paragraph, it is now deprecated in HTML5. CSS should be used instead.  

### **Syntax (Deprecated Method):**  
```html
<p align="value"> Text </p>
```

### **Example: Aligning Text with `<p>` (Deprecated Method)**  

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML paragraph</title>
</head>
<body>
    <p align="center">Welcome Folks</p>
    <p align="left">A Computer Science portal for Coders.</p>
    <p align="right">It contains well-written, well-thought-out articles.</p>
</body>
</html>
```

### **Output:**  


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML paragraph</title>
</head>
<body>
    <p align="center">Welcome Folks</p>
    <p align="left">A Computer Science portal for coders.</p>
    <p align="right">It contains well-written, well-thought-out articles.</p>
</body>
</html>


### **Modern Alternative (Using CSS):**  
```html
<p style="text-align: center;">Welcome Folks</p>
<p style="text-align: left;">A Computer Science portal for coders.</p>
<p style="text-align: right;">It contains well-written, well-thought-out articles.</p>
```

---

## **Using the `<pre>` Tag for Preformatted Text**  
The `<pre>` tag preserves spaces, line breaks, and formatting exactly as written in the HTML code.

### **Syntax:**  
```html
<pre> Content </pre>
```

### **Example: Using `<pre>` to Preserve Formatting**  

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Preformatted Text</title>
</head>
<body>
    <pre>
    This paragraph has multiple
    lines. But it is displayed 
    exactly as it is written.
    </pre>

    <pre>
    This     paragraph has multiple
    spaces. But     they are displayed 
    exactly    as they appear in the code.
    </pre>
</body>
</html>
```

### **Output:**  

```
This paragraph has multiple
lines. But it is displayed 
exactly as it is written.
```

```
This     paragraph has multiple
spaces. But     they are displayed 
exactly    as they appear in the code.
```

---

## **Common Mistakes to Avoid**  
🚫 **Nesting Paragraphs**: You cannot place one `<p>` tag inside another. Each paragraph should be independent.  
🚫 **Using `<p>` for Non-Text Content**: The `<p>` tag is for text. For images, tables, or other elements, use `<img>`, `<table>`, or `<div>` instead.  

---

🚀