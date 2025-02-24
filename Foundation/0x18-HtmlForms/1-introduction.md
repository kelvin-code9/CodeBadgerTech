# HTML `forms`

The `<form>` tag is used to create an HTML form for user input. It acts as a container for various input elements such as text fields, checkboxes, radio buttons, and submit buttons. Forms enable users to enter and submit data to a server for processing or to be handled by client-side scripts.

### Key Features of the `<form>` Tag
- It allows data collection through different input types.
- Supports attributes that define how data is submitted and processed.
- Works with both client-side and server-side scripting.

### Example: Simple User Information Form
```html
<!DOCTYPE html>
<html>
<body>
    <form action="/submit" method="POST">
        <h2>User Information</h2>
        
        <label for="fname">First Name:</label>
        <input type="text" id="fname" name="fname" placeholder="Enter your first name" required><br><br>

        <label for="lname">Last Name:</label>
        <input type="text" id="lname" name="lname" placeholder="Enter your last name" required><br><br>

        <input type="submit" value="Submit">
    </form>          
</body>
</html>
```

## OUTPUT
![image](https://github.com/user-attachments/assets/45d386b9-bc0a-4f38-a3e1-f88a8797099f)


### Common Form Elements
Here are some commonly used form elements in HTML:
- `<input>` - Creates various input fields (text, password, checkbox, radio, etc.).
- `<button>` - Defines a clickable button.
- `<select>` - Creates a dropdown list.
- `<textarea>` - Allows multi-line text input.
- `<label>` - Associates text with form elements.
- `<fieldset>` - Groups related form elements.
- `<legend>` - Defines a caption for a `<fieldset>`.
- `<datalist>` - Provides a list of predefined options for input fields.
- `<output>` - Displays calculation results.

### Important `<form>` Attributes
| Attribute | Description |
|-----------|-------------|
| `name` | Specifies the form's name. |
| `action` | Defines where the form data will be sent upon submission. |
| `method` | Determines how data is sent (GET or POST). |
| `target` | Specifies where the response will be displayed (e.g., new tab, same tab). |
| `enctype` | Defines encoding type for submitted data. |
| `accept-charset` | Specifies allowed character encodings for form submission. |
| `autocomplete` | Enables or disables browser autocomplete. |
| `novalidate` | Prevents built-in form validation. |
| `rel` | Defines the relationship between the document and linked resource. |

### Form Submission Methods
- **GET Method**: Appends form data to the URL. Useful for retrieving data but has a length limit.
- **POST Method**: Sends data in the request body, making it more secure and allowing large amounts of data.

### Example: Form with Radio Buttons
This example demonstrates how to create a gender selection form using radio buttons.
```html
<!DOCTYPE html>
<html>
<body>
    <h1>Gender Selection</h1>
    <form action="#" method="POST">
        <label for="male">Male</label>
        <input type="radio" id="male" name="gender" value="male">

        <label for="female">Female</label>
        <input type="radio" id="female" name="gender" value="female">

        <label for="other">Other</label>
        <input type="radio" id="other" name="gender" value="other"><br><br>
        
        <input type="submit" value="Submit">
    </form>
</body>
</html>
```
## OUTPUT
![image](https://github.com/user-attachments/assets/29f00bfc-4ab2-475b-b59b-089dfa758d81)


### Example: Form with Checkboxes
The following form lets users select their interests using checkboxes and submit their choices.
```html
<!DOCTYPE html>
<html>
<body>
    <h1>Newsletter Subscription</h1>
    <form action="/submit" method="POST">
        <p>Select your interests:</p>

        <input type="checkbox" id="tech" name="interests" value="Technology">
        <label for="tech">Technology</label><br>

        <input type="checkbox" id="sports" name="interests" value="Sports">
        <label for="sports">Sports</label><br>

        <input type="checkbox" id="music" name="interests" value="Music">
        <label for="music">Music</label><br>

        <input type="checkbox" id="movies" name="interests" value="Movies">
        <label for="movies">Movies</label><br><br>

        <input type="submit" value="Subscribe">
    </form>
</body>
</html>
```

### OUTPUT
![image](https://github.com/user-attachments/assets/de23ff34-7b13-43fb-afe2-89e600e2ab80)


This guide provides a beginner-friendly introduction to HTML forms. Understanding these elements and attributes will help in designing user-friendly and functional web forms
