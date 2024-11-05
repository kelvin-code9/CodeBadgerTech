## Lesson 2: Objects in JavaScript

### Learning Objectives:
- Understand the basics of objects in JavaScript.
- Learn how to create an object using object literals.
- Access and modify object properties.
- Define methods within objects and understand how they work.
- Implement a practical example to reinforce learning.

---

### 1. **What is an Object in JavaScript?**
In JavaScript, an **object** is a collection of related data and/or functionality. Objects are used to represent real-world entities that have properties and behaviors.

For example, a "person" could be an object with properties like "name" and "age," and a behavior such as "greet."

### 2. **Object Literals**
An **object literal** is a way to define an object in JavaScript directly using curly braces `{}`. This is one of the simplest and most common ways to create objects.

**Syntax:**
```javascript
let objectName = {
    key1: value1,
    key2: value2,
    // additional key-value pairs
};
```

Each key in an object is a **property**, and each key-value pair defines a property of that object. You can also add **methods** to objects, which are functions defined as properties.

---

### 3. **Creating an Object Using Object Literals**

Let's create an object named `person` with properties `name`, `age`, and a method called `greet`:

```javascript
let person = {
    name: "Alice",
    age: 25,
    greet: function() {
        console.log("Hello, my name is " + this.name + "!");
    }
};
```

In this example:
- `name` is a property with the value `"Alice"`.
- `age` is a property with the value `25`.
- `greet` is a method that logs a greeting to the console. The keyword `this` refers to the current object (`person`), so `this.name` will output `"Alice"`.

---

### 4. **Accessing and Modifying Object Properties**

You can access or modify object properties in two main ways:
1. **Dot Notation**: `objectName.propertyName`
2. **Bracket Notation**: `objectName["propertyName"]`

**Example:**
```javascript
console.log(person.name);       // Accessing property using dot notation
console.log(person["age"]);     // Accessing property using bracket notation

// Modifying properties
person.age = 30;                // Changing age to 30
person["name"] = "Bob";         // Changing name to "Bob"
```

**Note**: Dot notation is generally more common and readable. However, if the property name has special characters or spaces, use bracket notation.

---

### 5. **Methods in Objects**

A **method** is a function that is defined as a property of an object. Methods allow objects to have behaviors.

In the `person` object example above, `greet` is a method. It performs an action by printing a message to the console.

**Calling a Method:**
To call a method, use the same syntax as accessing a property, followed by parentheses `()`.

```javascript
person.greet();  // Outputs: Hello, my name is Bob!
```

### 6. **`this` Keyword in Objects**

- Inside a method, `this` refers to the object calling the method.
- In the `greet` method, `this.name` refers to `person.name`.

This allows methods to access and use other properties within the same object.

---

### Practical Example: Building a `person` Object

#### Code Example:
```javascript
let person = {
    name: "Alice",
    age: 25,
    greet: function() {
        console.log("Hello, my name is " + this.name + " and I am " + this.age + " years old.");
    }
};

// Accessing properties
console.log(person.name);  // Output: Alice
console.log(person.age);   // Output: 25

// Modifying properties
person.name = "Charlie";
person.age = 28;

// Calling the greet method
person.greet();  // Output: Hello, my name is Charlie and I am 28 years old.
```

#### Explanation:
1. We created an object `person` with properties `name` and `age`.
2. The `greet` method prints a greeting message that includes the `name` and `age` properties.
3. We demonstrated how to access and modify properties.
4. We invoked the `greet` method, which uses the updated values of `name` and `age`.

---

### Classwork: Practice Exercise

1. **Create an Object:**  
   Write an object called `student` with the following properties:
   - `name`: a string representing the student's name.
   - `grade`: a number representing the student’s current grade.
   - `introduce`: a method that prints `"Hi, I'm [name] and I'm in grade [grade]."` (Use `this` to reference properties.)

2. **Modify Properties:**  
   - After creating the object, update the `grade` to a new value.
   - Update the `name` to a new value.

3. **Call the Method:**  
   - Call the `introduce` method to ensure it prints the updated values correctly.

**Expected Output Example:**
```javascript
// Initial values
Hi, I'm John and I'm in grade 8.

// After modifications
Hi, I'm Sarah and I'm in grade 9.
```

---

### Summary:
- Objects in JavaScript are collections of properties and methods.
- Use dot notation or bracket notation to access and modify properties.
- Methods allow objects to have behaviors, and `this` refers to the object itself within a method.

