# JavaScript Basic Data Types

## What Are Data Types?

In JavaScript, **data types** define the type of value that a variable can hold. For example, a number is a different type of data than a piece of text. Understanding data types is important because different types of data are handled in different ways in JavaScript.

JavaScript has several data types, but we’ll focus on the **basic ones**: 

- **Numbers**
- **Strings**
- **Booleans**
- **Undefined**
- **Null**

Let’s go through each one in detail.

---

## 1. **Numbers**

A **number** in JavaScript is used to represent both integers (whole numbers) and floating-point numbers (numbers with decimals).

### Examples:

```javascript
let age = 30;     // This is an integer number
let price = 19.99; // This is a floating-point number (decimal)
```

### What Can You Do with Numbers?

You can perform various operations with numbers, like addition, subtraction, multiplication, and division.

#### Example:

```javascript
let a = 10;
let b = 5;

console.log(a + b); // Addition: Outputs 15
console.log(a - b); // Subtraction: Outputs 5
console.log(a * b); // Multiplication: Outputs 50
console.log(a / b); // Division: Outputs 2
```

---

## 2. **Strings**

A **string** is used to represent text. Strings are always written inside **quotes**. You can use either **single quotes (' ')** or **double quotes (" ")**.

### Examples:

```javascript
let name = "Alice";  // A string with double quotes
let greeting = 'Hello, world!';  // A string with single quotes
```

### What Can You Do with Strings?

You can combine strings (called **concatenation**) or find out their length.

#### Example:

```javascript
let firstName = "John";
let lastName = "Doe";

console.log(firstName + " " + lastName); // Combines the strings: Outputs "John Doe"
console.log(firstName.length); // Gets the length of the string: Outputs 4
```

In the above example, `"John Doe"` is the result of **concatenating** the first name and last name with a space between them.

---

## 3. **Booleans**

A **boolean** is a data type that can only have one of two values:
- `true`
- `false`

Booleans are often used to represent the answer to a yes/no question or a true/false condition.

### Example:

```javascript
let isJavaScriptFun = true;
let isRainy = false;

console.log(isJavaScriptFun);  // Outputs: true
console.log(isRainy);          // Outputs: false
```

Booleans are very useful when making decisions in code, like checking if a certain condition is true or false.

---

## 4. **Undefined**

**Undefined** is a special data type in JavaScript. A variable that has been declared but **not assigned** a value will automatically be set to `undefined`.

### Example:

```javascript
let job;
console.log(job);  // Outputs: undefined
```

In this case, the variable `job` has been declared, but since it has no value yet, it is `undefined`.

### When Is `undefined` Used?

- When you create a variable but forget to give it a value.
- If a function does not return a value, it returns `undefined`.

---

## 5. **Null**

**Null** represents the intentional absence of any value. It is a value you can assign to a variable when you want to say, “this variable has no value.”

### Example:

```javascript
let result = null;
console.log(result);  // Outputs: null
```

### Difference Between `undefined` and `null`

- **`undefined`**: JavaScript sets it automatically when a variable is declared but not given a value.
- **`null`**: You set it manually to show that a variable has no value.

---

## Key Points to Remember

- **Numbers**: Represent both integers (whole numbers) and decimals.
- **Strings**: Represent text, written inside quotes.
- **Booleans**: Can only be `true` or `false`.
- **Undefined**: A variable that has been declared but not given a value.
- **Null**: A value that represents "no value" or "empty."

---

## Summary of Basic Data Types

| Data Type  | Example            | Description                                   |
|------------|--------------------|-----------------------------------------------|
| **Number** | `let x = 42;`       | Represents both integers and decimals.        |
| **String** | `let name = "Bob";` | Represents text, written inside quotes.       |
| **Boolean**| `let isCool = true;`| Represents true/false values.                 |
| **Undefined** | `let y;`         | A variable declared but not assigned a value. |
| **Null**   | `let z = null;`     | A variable that has no value (set intentionally). |

---

## Conclusion

Understanding these basic data types is the first step toward learning how to write programs in JavaScript. As you write more code, you'll see how these types are used to represent different kinds of information, and you'll combine them in interesting ways!

--- 

This guide should give beginners a solid introduction to the basic data types in JavaScript.
