## Introduction to Multimedia in HTML

Multimedia refers to content such as audio and video that can be heard or seen. It enhances user experience by making web pages more interactive and engaging.

### **Types of Multimedia in HTML**
Multimedia comes in different forms, including:
- **Audio** – Common formats include MP3. The `<audio>` tag is used to embed audio files in HTML.
- **Video** – Popular formats include MP4. The `<video>` tag is used to embed video files in HTML.

### **Common Multimedia Formats**
To use multimedia effectively, it's important to understand file formats. Some common formats include:

| **Media Type** | **File Format** | **Usage** |
|--------------|---------------|---------|
| **Audio** | MP3 | Used for embedding sound and music |
| **Video** | MP4 | Used for playing video content |

### **Checking the Format of a Multimedia File**
The format of a multimedia file can be identified by its **file extension** (e.g., `.mp3`, `.mp4`). This helps in determining compatibility with web browsers and media players.

### **Example: Embedding Audio in HTML**
```html
<audio controls>
    <source src="audiofile.mp3" type="audio/mpeg">
</audio>
```

### **Example: Embedding Video in HTML**
```html
<video width="320" height="240" controls>
    <source src="videofile.mp4" type="video/mp4">
</video>
```

By using multimedia elements, websites can provide a richer and more interactive experience for users. Make sure to choose the right formats for better performance and browser compatibility!

