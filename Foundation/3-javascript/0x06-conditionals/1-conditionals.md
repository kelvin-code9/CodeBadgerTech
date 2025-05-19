
# JavaScript Conditional Statements: The `if` Statement (and `switch`!)

---

## Introduction

In programming, we often need the computer to make decisions based on certain conditions. For example:

* Should we show a message or not?
* Is this number big or small?
* Should the program do one thing or another?

To handle these decisions, we use **conditional statements**. The most basic conditional statement is the **`if` statement**.

---

## What is an `if` Statement?

An `if` statement checks whether a condition is true. If it is true, it runs a block of code. If it’s false, it skips that code block.

### Example:

```javascript
let age = 20;

if (age >= 18) {
    console.log("You are an adult.");
}
// Output: You are an adult.
```

Here, if the age is 18 or more, the message prints. If not, nothing happens.

---

## Basic Syntax of `if` Statements

```javascript
if (condition) {
    // code runs here if the condition is true
}
```

* The **condition** is something that results in `true` or `false`.
* The code inside `{}` runs only if the condition is true.

### Example:

```javascript
let number = 10;

if (number > 5) {
    console.log("The number is greater than 5.");
}
// Output: The number is greater than 5.
```

---

## Using `if` and `else` Statements

Sometimes, you want to do something if the condition is true, **and something else** if it’s false. For that, use `else`.

### Example:

```javascript
let temperature = 15;

if (temperature > 30) {
    console.log("It's hot outside!");
} else {
    console.log("It's not hot today.");
}
// Output: It's not hot today.
```

Here, because the temperature is not above 30, the `else` block runs.

---

## Using `else if` for Multiple Choices

When there are more than two possibilities, use `else if` to check multiple conditions in order.

### Example:

```javascript
let score = 75;

if (score >= 90) {
    console.log("A");
} else if (score >= 80) {
    console.log("B");
} else if (score >= 70) {
    console.log("C");
} else {
    console.log("F");
}
// Output: C
```

This checks each condition in order and runs the first block where the condition is true.

---

## Nested `if` Statements

You can put an `if` statement inside another `if` — this is called **nesting**.

### Example:

```javascript
let num = 12;

if (num > 10) {
    console.log("Number is more than 10");

    if (num % 2 === 0) {
        console.log("And it's even too!");
    }
}
// Output:
// Number is more than 10
// And it's even too!
```

First, the program checks if `num` is greater than 10. Since it is, it then checks if the number is even.

---

## Bonus: The `switch` Statement

The `switch` statement is an alternative to many `else if` blocks. It’s useful when you want to compare **one value** to many options.

### Basic Syntax:

```javascript
switch (value) {
    case option1:
        // code runs if value === option1
        break;
    case option2:
        // code runs if value === option2
        break;
    default:
        // code runs if no cases matched
}
```

The `break` statement stops the switch from running into the next case.

### Example:

```javascript
let day = "Wednesday";

switch (day) {
    case "Monday":
        console.log("Start of the week");
        break;
    case "Wednesday":
        console.log("Midweek day");
        break;
    case "Friday":
        console.log("Almost weekend");
        break;
    default:
        console.log("Just another day");
}
// Output: Midweek day
```

---

### Example with Multiple Cases:

```javascript
let day = "Sunday";

switch (day) {
    case "Saturday":
    case "Sunday":
        console.log("Weekend!");
        break;
    default:
        console.log("Weekday");
}
// Output: Weekend!
```

Here, both "Saturday" and "Sunday" run the same code because there is no `break` between them.

---

# Activities Explained

---

### Activity 1: Even or Odd

```javascript
let num = 7;

if (num % 2 === 0) {
    console.log("Even number");
} else {
    console.log("Odd number");
}
// Output: Odd number
```

**Explanation:**
We use the remainder operator `%` to check if dividing `num` by 2 leaves no remainder (`0`). If yes, it’s even; otherwise, odd. Here `7 % 2` is `1`, so it prints "Odd number".

---

### Activity 2: Pass or Fail

```javascript
let score = 52;

if (score >= 60) {
    console.log("Passed");
} else {
    console.log("Failed");
}
// Output: Failed
```

**Explanation:**
If the score is 60 or above, print "Passed". If less, print "Failed". Since 52 is below 60, "Failed" is printed.

---

### Activity 3: Simple Calculator Check

```javascript
let result = 50 + 60;

if (result > 100) {
    console.log("Big number!");
} else {
    console.log("Not too big.");
}
// Output: Big number!
```

**Explanation:**
We add 50 and 60, getting 110, which is greater than 100. So it prints "Big number!".

---


### Activity 4: Simple Login Check

```javascript
let username = "admin";

if (username === "admin") {
    console.log("Welcome!");
} else {
    console.log("Wrong user.");
}
// Output: Welcome!
```

**Explanation:**
If the username is exactly "admin", print "Welcome!". Otherwise, "Wrong user.". Here it’s "admin", so welcome message shows.

---

---