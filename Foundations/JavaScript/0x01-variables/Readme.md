# Introduction to JavaScript Variables: Using `let` and `const`

## What Are Variables?

In JavaScript, **variables** are used to store values like numbers, text, or other information. Think of a variable as a box that you can put something into, and give that box a name. Once you have a name for the box, you can easily access or change what's inside.

## How to Create a Variable

In JavaScript, we can create variables using two keywords: **`let`** and **`const`**.

### 1. `let`

- **`let`** is used when you need a variable whose value might change later.

#### Example:

```javascript
let age = 25;  // We create a variable named 'age' and store the value 25
console.log(age);  // This will show 25

age = 30;  // We change the value of 'age' to 30
console.log(age);  // This will show 30
```

- Here, we created a variable named `age` and set it to `25`. Later, we changed it to `30`. This is possible because we used `let`.

### 2. `const`

- **`const`** is used when you don’t want the value of a variable to change. Once you set a value using `const`, it stays the same.

#### Example:

```javascript
const year = 2024;  // We create a constant variable named 'year' and store the value 2024
console.log(year);  // This will show 2024

// Trying to change the value will cause an error
// year = 2025;  // This will give an error because 'year' cannot be changed
```

- Here, we created a variable `year` with a value of `2024`. Since we used `const`, we cannot change it later.

## Key Differences Between `let` and `const`

- **`let`** allows you to change the value later.
- **`const`** does not allow the value to be changed after it is set.

## Good to Know

- Always choose `const` when you know the value should not change, like a birth year, or a fixed value.
- Use `let` when the value might change, like someone's age, score in a game, or a countdown.

## Summary

- **`let`** is used for variables that might change.
- **`const`** is used for variables that should stay the same.

---
