### **Absolute and Relative Paths in HTML**
File paths are used in HTML to specify the location of files such as images, stylesheets, JavaScript files, or other web pages.

---

### **1. Absolute Path**
An absolute path provides the full URL or directory location of a file. It starts from the root and includes the domain name if it's an external resource.

**Example (External Link - Full URL):**
```html
<img src="https://example.com/images/photo.jpg" alt="Example Image">
```
**Example (Internal Link - Full Directory Path):**
```html
<img src="/home/user/website/images/photo.jpg" alt="Example Image">
```
- Used for linking external resources.
- Can break if the URL structure changes.

---

### **2. Relative Path**
A relative path specifies the file location relative to the current document.

**Example (Same Directory as HTML File):**
```html
<img src="photo.jpg" alt="Local Image">
```
**Example (Subdirectory Path):**
```html
<img src="images/photo.jpg" alt="Local Image in Folder">
```
**Example (Parent Directory Path):**
```html
<img src="../photo.jpg" alt="Image in Parent Directory">
```
- Easier to manage within a project.
- More flexible for moving files and folders.

---

**Key Differences:**
| Feature | Absolute Path | Relative Path |
|---------|--------------|--------------|
| Contains Domain Name | Yes | No |
| Flexibility | Less flexible | More flexible |
| Usage | External linking | Internal linking |

For better portability in web development, **relative paths** are commonly preferred. Let me know if you need more details! 🚀