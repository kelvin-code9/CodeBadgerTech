# JavaScript Conditional Statements: The `if` Statement

## Table of Contents
1. [Introduction](#introduction)
2. [What is an `if` Statement?](#what-is-an-if-statement)
3. [Basic Syntax of `if` Statements](#basic-syntax-of-if-statements)
4. [Using `if` and `else` Statements](#using-if-and-else-statements)
5. [Nested `if` Statements](#nested-if-statements)
6. [Classwork Activities](#classwork-activities)
7. [Conclusion](#conclusion)

## Introduction

In JavaScript, conditional statements allow us to execute different blocks of code based on different conditions. The `if` statement is fundamental in controlling the flow of a program. Understanding how to effectively use `if` and `else` statements will enable you to create dynamic and responsive applications.

## What is an `if` Statement?

An `if` statement evaluates a condition and executes a block of code if that condition is `true`. If the condition is `false`, the code block is skipped.

### Example of an `if` Statement

```javascript
let temperature = 30;

if (temperature > 25) {
    console.log("It's a hot day!");
}
```

In this example, since the temperature is greater than 25, the message "It's a hot day!" will be printed to the console.

## Basic Syntax of `if` Statements

The basic syntax of an `if` statement is as follows:

```javascript
if (condition) {
    // Code to execute if the condition is true
}
```

### Breakdown of Syntax
- **condition**: An expression that evaluates to `true` or `false`.
- **Code Block**: The code inside the curly braces `{}` executes only if the condition is `true`.

### Example with Comments

```javascript
let score = 90;

// Check if the score is greater than or equal to 60
if (score >= 60) {
    console.log("You passed the exam!"); // Executes if true
}
```

## Using `if` and `else` Statements

The `else` statement can be used alongside an `if` statement to provide an alternative block of code to execute when the condition is `false`.

### Syntax of `if...else`

```javascript
if (condition) {
    // Code to execute if the condition is true
} else {
    // Code to execute if the condition is false
}
```

### Example of `if...else`

```javascript
let age = 15;

if (age >= 18) {
    console.log("You are an adult.");
} else {
    console.log("You are not an adult.");
}
```

In this example, since the age is less than 18, the message "You are not an adult." will be printed.

### Example with Multiple Conditions

You can also combine multiple conditions using `if`, `else if`, and `else` to create more complex decision-making logic.

```javascript
let score = 85;

if (score >= 90) {
    console.log("Grade: A");
} else if (score >= 80) {
    console.log("Grade: B");
} else if (score >= 70) {
    console.log("Grade: C");
} else {
    console.log("Grade: F");
}
```

## Nested `if` Statements

You can also nest `if` statements within each other to create more complex conditions. This means you can place one `if` statement inside another `if` statement.

### Syntax of Nested `if`

```javascript
if (condition1) {
    if (condition2) {
        // Code to execute if both conditions are true
    }
}
```

### Example of Nested `if` Statements

```javascript
let temperature = 15;

if (temperature < 20) {
    console.log("It's quite cool.");
    if (temperature < 10) {
        console.log("It's very cold!");
    }
}
```

In this example, since the temperature is less than 20, the first message is printed. If it is also less than 10, the second message will be printed.

### Example with Multiple Nested Conditions

```javascript
let age = 30;

if (age < 13) {
    console.log("Child");
} else if (age < 20) {
    console.log("Teenager");
} else {
    console.log("Adult");
    if (age > 65) {
        console.log("Senior Citizen");
    }
}
```

Here, if the age is greater than or equal to 20, it will log "Adult," and if the age is also greater than 65, it will log "Senior Citizen."

## Classwork Activities

Here are some activities for students to practice writing `if` and `else` statements, including nested conditions. Each activity focuses on different scenarios without requiring user input.

### Activity 1: Simple Grade Evaluation
Write a program that evaluates the grade based on the following criteria:
- If the score is greater than or equal to 90, log "Grade: A".
- If the score is between 80 and 89, log "Grade: B".
- If the score is between 70 and 79, log "Grade: C".
- If the score is below 70, log "Grade: F".

**Example Solution**:
```javascript
let score = 85;

if (score >= 90) {
    console.log("Grade: A");
} else if (score >= 80) {
    console.log("Grade: B");
} else if (score >= 70) {
    console.log("Grade: C");
} else {
    console.log("Grade: F");
}
```

### Activity 2: Age Group Evaluation
Create a program that categorizes a person based on their age:
- If the age is less than 13, log "Child".
- If the age is between 13 and 19, log "Teenager".
- If the age is between 20 and 64, log "Adult".
- If the age is 65 or older, log "Senior".

**Example Solution**:
```javascript
let age = 30;

if (age < 13) {
    console.log("Child");
} else if (age < 20) {
    console.log("Teenager");
} else if (age < 65) {
    console.log("Adult");
} else {
    console.log("Senior");
}
```

### Activity 3: Light Status
Create a program to determine the status of a light based on its brightness level:
- If the brightness is above 80, log "Bright Light".
- If the brightness is between 40 and 80, log "Medium Light".
- If the brightness is below 40, log "Dim Light".

**Example Solution**:
```javascript
let brightness = 55;

if (brightness > 80) {
    console.log("Bright Light");
} else if (brightness >= 40) {
    console.log("Medium Light");
} else {
    console.log("Dim Light");
}
```

### Activity 4: Loan Eligibility
Write a program to check loan eligibility based on income:
- If the income is greater than or equal to 50000, log "Eligible for loan".
- If the income is between 30000 and 49999, log "Considered for loan".
- If the income is less than 30000, log "Not eligible for loan".

**Example Solution**:
```javascript
let income = 45000;

if (income >= 50000) {
    console.log("Eligible for loan");
} else if (income >= 30000) {
    console.log("Considered for loan");
} else {
    console.log("Not eligible for loan");
}
```

### Activity 5: Nested Temperature Check
Create a program that checks temperature ranges with nested `if` statements:
- If the temperature is below 0, log "Freezing cold!".
- If the temperature is between 0 and 20, log "Cold day!".
- If the temperature is between 21 and 30, log "Warm day!".
- If the temperature is above 30, log "Hot day!".
- If it’s a hot day, check if it’s above 40 and log "Extremely hot!".

**Example Solution**:
```javascript
let temperature = 32;

if (temperature < 0) {
    console.log("Freezing cold!");
} else if (temperature <= 20) {
    console.log("Cold day!");
} else if (temperature <= 30) {
    console.log("Warm day!");
} else {
    console.log("Hot day!");
    if (temperature > 40) {
        console.log("Extremely hot!");
    }
}
```

### Activity 6: Holiday Greeting
Write a program that checks if a date corresponds to a holiday:
- If it's December 25, log "Merry Christmas!".
- If it's January 1, log "Happy New Year!".
- If it's July 4, log "Happy Independence Day!".
- If it’s not a holiday, log "Not a holiday."

**Example Solution**:
```javascript
let date = "January 1";

if (date === "December 25") {
    console.log("Merry Christmas!");
} else if (date === "January 1") {
    console.log("Happy New Year!");
} else if (date === "July 4") {
    console.log("Happy Independence Day!");
} else {
    console.log("Not a holiday.");
}
```

### Activity 7

: Shopping Discount
Write a program that determines the discount based on the total shopping amount:
- If the total is greater than 100, log "20% discount".
- If the total is between 50 and 100, log "10% discount".
- If the total is less than 50, log "No discount".

**Example Solution**:
```javascript
let total = 75;

if (total > 100) {
    console.log("20% discount");
} else if (total >= 50) {
    console.log("10% discount");
} else {
    console.log("No discount");
}
```

### Activity 8: Even or Odd Number
Write a program that checks if a number is even or odd:
- If the number is divisible by 2, log "Even number".
- If not, log "Odd number".

**Example Solution**:
```javascript
let number = 7;

if (number % 2 === 0) {
    console.log("Even number");
} else {
    console.log("Odd number");
}
```

### Activity 9: Character Evaluation
Create a program that checks the character type:
- If the character is a vowel (a, e, i, o, u), log "Vowel".
- If it’s a consonant, log "Consonant".
- If it's not a letter, log "Not a letter".

**Example Solution**:
```javascript
let char = 'a';

if (char === 'a' || char === 'e' || char === 'i' || char === 'o' || char === 'u') {
    console.log("Vowel");
} else if ((char >= 'a' && char <= 'z') || (char >= 'A' && char <= 'Z')) {
    console.log("Consonant");
} else {
    console.log("Not a letter");
}
```

## Conclusion

In this lesson, you have learned about the `if` statement, how to use `else` to handle alternative conditions, and how to nest `if` statements for more complex decision-making. With these tools, you can create programs that respond intelligently to different situations.

Continue practicing with the activities provided to solidify your understanding of conditional statements in JavaScript!

--- 

Feel free to adjust any parts of the README or add more activities based on your teaching needs!
