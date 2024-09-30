# Module 4: Functions in JavaScript

## Overview
This module delves into functions in JavaScript, a core aspect of the language that allows for code reuse, organization, and abstraction. Functions enable developers to write modular code, making programs easier to manage and understand. This module is divided into two lessons: **Function Basics** and **Advanced Function Concepts**.

## Table of Contents
1. [Lesson 1: Function Basics](#lesson-1-function-basics)
   - [Defining a Function](#defining-a-function)
   - [Function Parameters and Arguments](#function-parameters-and-arguments)
   - [Return Statements](#return-statements)
   - [Practical Tasks](#practical-tasks)
2. [Lesson 2: Advanced Function Concepts](#lesson-2-advanced-function-concepts)
   - [Function Expressions vs. Declarations](#function-expressions-vs-declarations)
   - [Arrow Functions (ES6)](#arrow-functions-es6)
   - [Scope (Local vs. Global)](#scope-local-vs-global)
   - [Practical Tasks](#practical-tasks-1)
3. [Conclusion](#conclusion)
4. [Further Reading](#further-reading)

---

## Lesson 1: Function Basics

### Defining a Function
A **function** is a reusable block of code that performs a specific task. Functions help in organizing code and improving its readability. In JavaScript, functions can be defined using the `function` keyword, followed by the function's name, parentheses for parameters, and curly braces to contain the code block.

**Syntax:**
```javascript
function functionName(parameters) {
    // code to be executed
}
```

**Example:**
```javascript
function sayHello() {
    console.log("Hello, World!");
}

// Calling the function
sayHello(); // Output: Hello, World!
```

### Function Parameters and Arguments
**Parameters** are variables listed as part of the function's definition. When a function is called, values passed to it are called **arguments**. Parameters act as placeholders for the arguments that will be passed when the function is invoked.

**Example:**
```javascript
function greet(name) {
    return `Hello, ${name}!`;
}

console.log(greet("Alice")); // Output: Hello, Alice!
```

### Return Statements
The `return` statement ends the execution of a function and specifies a value to be returned to the function caller. If no return statement is specified, the function will return `undefined` by default.

**Example:**
```javascript
function add(a, b) {
    return a + b;
}

let sum = add(5, 10);
console.log(sum); // Output: 15
```

### Practical Tasks
1. **Task:** Write a function that takes two numbers as arguments and returns their sum.
   - **Solution:**
   ```javascript
   function sum(num1, num2) {
       return num1 + num2;
   }

   console.log(sum(10, 5)); // Output: 15
   ```

2. **Task:** Write a function that takes three numbers as arguments and returns their average.
   - **Solution:**
   ```javascript
   function average(num1, num2, num3) {
       return (num1 + num2 + num3) / 3;
   }

   console.log(average(4, 8, 12)); // Output: 8
   ```

3. **Task:** Create a function that checks if a number is even or odd.
   - **Solution:**
   ```javascript
   function isEven(number) {
       return number % 2 === 0;
   }

   console.log(isEven(4)); // Output: true
   console.log(isEven(5)); // Output: false
   ```

4. **Task:** Write a function that returns the maximum of three numbers.
   - **Solution:**
   ```javascript
   function maxOfThree(num1, num2, num3) {
       return Math.max(num1, num2, num3);
   }

   console.log(maxOfThree(3, 5, 2)); // Output: 5
   ```

---

## Lesson 2: Advanced Function Concepts

### Function Expressions vs. Declarations
JavaScript allows functions to be defined in two primary ways: **Function Declarations** and **Function Expressions**.

- **Function Declarations:** Defined using the `function` keyword and can be called before they are defined in the code due to hoisting.
  
  **Example:**
  ```javascript
  console.log(square(5)); // Output: 25

  function square(x) {
      return x * x;
  }
  ```

- **Function Expressions:** Can be anonymous and are defined within an expression. They are not hoisted and cannot be called before their definition.

  **Example:**
  ```javascript
  const square = function(x) {
      return x * x;
  };

  console.log(square(5)); // Output: 25
  // console.log(square); // Uncommenting this line before the expression will throw an error
  ```

### Arrow Functions (ES6)
Arrow functions provide a concise syntax for writing function expressions and do not have their own `this`, making them particularly useful in scenarios like callbacks.

**Syntax:**
```javascript
const functionName = (parameters) => {
    // code to be executed
};
```

**Example:**
```javascript
const add = (a, b) => a + b; // Implicit return
console.log(add(2, 3)); // Output: 5

const greet = name => `Hello, ${name}`; // Single parameter without parentheses
console.log(greet("Alice")); // Output: Hello, Alice
```

### Scope (Local vs. Global)
Understanding scope is crucial for managing variable accessibility in JavaScript.

- **Global Scope:** Variables declared outside of any function are global and can be accessed from anywhere in the code.
  
  **Example:**
  ```javascript
  let globalVar = "I'm global";

  function checkScope() {
      console.log(globalVar); // Accessible
  }

  checkScope(); // Output: I'm global
  ```

- **Local Scope:** Variables declared inside a function are local to that function and cannot be accessed outside of it.

  **Example:**
  ```javascript
  function localScopeExample() {
      let localVar = "I'm local";
      console.log(localVar); // Accessible
  }

  localScopeExample(); // Output: I'm local
  // console.log(localVar); // Error: localVar is not defined
  ```

### Practical Tasks
1. **Task:** Convert the following function declaration into an arrow function:
   ```javascript
   function multiply(a, b) {
       return a * b;
   }
   ```
   - **Solution:**
   ```javascript
   const multiply = (a, b) => a * b;
   ```

2. **Task:** Write an arrow function that takes an array of numbers and returns the sum of the numbers.
   - **Solution:**
   ```javascript
   const sumArray = (numbers) => numbers.reduce((acc, curr) => acc + curr, 0);

   console.log(sumArray([1, 2, 3, 4, 5])); // Output: 15
   ```

3. **Task:** Create a function to check if a string is a palindrome (reads the same forwards and backwards).
   - **Solution:**
   ```javascript
   function isPalindrome(str) {
       const reversed = str.split('').reverse().join('');
       return str === reversed;
   }

   console.log(isPalindrome("racecar")); // Output: true
   console.log(isPalindrome("hello")); // Output: false
   ```

4. **Task:** Write a function that returns a new function that adds a specified value to its argument.
   - **Solution:**
   ```javascript
   function createAdder(x) {
       return function(y) {
           return x + y;
       };
   }

   const addFive = createAdder(5);
   console.log(addFive(10)); // Output: 15
   ```

5. **Task:** Demonstrate the difference between local and global variables by modifying a global variable inside a function.
   - **Solution:**
   ```javascript
   let counter = 0;

   function incrementCounter() {
       counter++;
       console.log(counter);
   }

   incrementCounter(); // Output: 1
   incrementCounter(); // Output: 2
   console.log(counter); // Output: 2 (global variable modified)
   ```

---
