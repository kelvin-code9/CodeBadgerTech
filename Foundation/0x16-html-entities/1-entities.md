### **HTML Entities Note**  

In HTML, some characters have special meanings and must be represented using **character entities** to be displayed correctly. These entities prevent errors and ensure proper rendering across different browsers.  

#### **Common HTML Entities**  
| Symbol | Entity Name | Entity Number |
|---------|------------|--------------|
| **Less Than (<)** | `&lt;` | `&#60;` |
| **Greater Than (>)** | `&gt;` | `&#62;` |
| **Pound (£)** | `&pound;` | `&#163;` |
| **Euro (€)** | `&euro;` | `&#8364;` |
| **Copyright (©)** | `&copy;` | `&#169;` |
| **Registered Trademark (®)** | `&reg;` | `&#174;` |
| **Double Quotation Mark (")** | `&quot;` | `&#34;` |

#### **Why Use HTML Entities?**
- Prevents conflicts with HTML syntax (e.g., `<` and `>` in tags).
- Ensures proper display of special symbols and characters.
- Improves browser compatibility and content accessibility.

#### **Example Usage in HTML**
```html
<p>&copy; 2025 MyWebsite. All Rights Reserved.</p>
<p>Price: &pound;50 or &euro;60</p>
<p>Use &lt;h1&gt; for headings in HTML.</p>
```

## Output
<p>&copy; 2025 MyWebsite. All Rights Reserved.</p>
<p>Price: &pound;50 or &euro;60</p>
<p>Use &lt;h1&gt; for headings in HTML.</p>

---

Here is a table of symbols that are not present on a standard keyboard but can be used in HTML using entities:  

### **Special HTML Entities Table**
| Symbol | Description | Entity Name | Entity Number |
|---------|----------------------|-------------|--------------|
| †       | Dagger               | `&dagger;`  | `&#8224;`  |
| ‡       | Double Dagger        | `&Dagger;`  | `&#8225;`  |
| •       | Bullet Point         | `&bull;`    | `&#8226;`  |
| ‰       | Per Mille Sign       | `&permil;`  | `&#8240;`  |
| ‾       | Overline             | `&oline;`   | `&#8254;`  |
| ℑ       | Blackletter I        | `&image;`   | `&#8465;`  |
| ℜ       | Blackletter R        | `&real;`    | `&#8476;`  |
| ℵ       | Aleph Symbol         | `&alefsym;` | `&#8501;`  |
| ⌈       | Left Ceiling         | `&lceil;`   | `&#8968;`  |
| ⌉       | Right Ceiling        | `&rceil;`   | `&#8969;`  |
| ⌊       | Left Floor           | `&lfloor;`  | `&#8970;`  |
| ⌋       | Right Floor          | `&rfloor;`  | `&#8971;`  |
| ◊       | Lozenge              | `&loz;`     | `&#9674;`  |
| ♠       | Spade Suit           | `&spades;`  | `&#9824;`  |
| ♣       | Club Suit            | `&clubs;`   | `&#9827;`  |
| ♥       | Heart Suit           | `&hearts;`  | `&#9829;`  |
| ♦       | Diamond Suit         | `&diams;`   | `

---
Here is an **HTML Emoji Entities table**

### **HTML Emoji Entities Table**
| Emoji | Description | Entity Number |
|--------|-------------|--------------|
| 😀     | Grinning Face | `&#128512;` |
| 😂     | Face with Tears of Joy | `&#128514;` |
| 😍     | Smiling Face with Heart-Eyes | `&#128525;` |
| 😎     | Smiling Face with Sunglasses | `&#128526;` |
| 😢     | Crying Face | `&#128546;` |
| 😡     | Angry Face | `&#128545;` |
| 👍     | Thumbs Up | `&#128077;` |
| 👎     | Thumbs Down | `&#128078;` |
| 👏     | Clapping Hands | `&#128079;` |
| 🙌     | Raising Hands | `&#128588;` |
| 💯     | 100 Points | `&#128175;` |
| 🔥     | Fire | `&#128293;` |
| 🎉     | Party Popper | `&#127881;` |
| ❤️     | Red Heart | `&#10084;` |
| ⭐     | Star | `&#11088;` |
| ☀️     | Sun | `&#9728;` |
| ☁️     | Cloud | `&#9729;` |
| ☔     | Umbrella with Rain Drops | `&#9748;` |
| 🌍     | Earth Globe | `&#127757;` |
| 🚀     | Rocket | `&#128640;` |

### **How to Use in HTML**
To use these emojis in HTML, just insert the **entity number** in your code.  
For example:
```html
<p>Hello World! &#128512; &#127881; 🎉</p>
```
This will display:  
**Hello World! 😀 🎉 🎉**


By using these entities, we can display special characters safely in an HTML document.  

---
