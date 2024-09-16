# JavaScript Operators: Super Detailed Guide

## 1. **Arithmetic Operators**

Arithmetic operators are used to perform basic mathematical operations like addition, subtraction, multiplication, etc.

### List of Arithmetic Operators:

| Operator | Description                | Example        | Result       |
|----------|----------------------------|----------------|--------------|
| `+`      | Addition                   | `5 + 3`        | `8`          |
| `-`      | Subtraction                | `5 - 3`        | `2`          |
| `*`      | Multiplication             | `5 * 3`        | `15`         |
| `/`      | Division                   | `6 / 3`        | `2`          |
| `%`      | Modulus (remainder)        | `5 % 3`        | `2`          |
| `++`     | Increment (increase by 1)  | `x++` (if x = 5) | `6`          |
| `--`     | Decrement (decrease by 1)  | `x--` (if x = 5) | `4`          |

### Examples:

```javascript
let a = 10;
let b = 3;

console.log(a + b);  // Addition: 10 + 3 = 13
console.log(a - b);  // Subtraction: 10 - 3 = 7
console.log(a * b);  // Multiplication: 10 * 3 = 30
console.log(a / b);  // Division: 10 / 3 = 3.333...
console.log(a % b);  // Modulus: 10 % 3 = 1 (Remainder)
```

### Increment (`++`) and Decrement (`--`)

- **`++` (Increment)**: Increases a number by 1.
- **`--` (Decrement)**: Decreases a number by 1.

#### Example:

```javascript
let x = 5;
x++;  // Increment: x is now 6
x--;  // Decrement: x is now back to 5
```

There are **two forms** of increment/decrement:
- **Postfix** (e.g., `x++` or `x--`): Returns the original value first, then increments/decrements.
- **Prefix** (e.g., `++x` or `--x`): Increments/decrements first, then returns the new value.

```javascript
let x = 5;
console.log(x++);  // Outputs: 5, then x becomes 6
console.log(++x);  // x becomes 7, then outputs: 7
```

---

## 2. **Assignment Operators**

Assignment operators are used to assign values to variables. The basic one is `=`, but there are many more that combine assignment with arithmetic.

### List of Assignment Operators:

| Operator | Description                | Example        | Equivalent to  | Result         |
|----------|----------------------------|----------------|----------------|----------------|
| `=`      | Assigns a value             | `x = 5`        |                | `x = 5`        |
| `+=`     | Add and assign              | `x += 3`       | `x = x + 3`    | `x = 8` (if x = 5) |
| `-=`     | Subtract and assign         | `x -= 2`       | `x = x - 2`    | `x = 3` (if x = 5) |
| `*=`     | Multiply and assign         | `x *= 4`       | `x = x * 4`    | `x = 20` (if x = 5) |
| `/=`     | Divide and assign           | `x /= 2`       | `x = x / 2`    | `x = 2.5` (if x = 5) |
| `%=`     | Modulus and assign          | `x %= 3`       | `x = x % 3`    | `x = 2` (if x = 5) |

### Examples:

```javascript
let x = 10;

x += 5;  // x = x + 5; x is now 15
x -= 3;  // x = x - 3; x is now 12
x *= 2;  // x = x * 2; x is now 24
x /= 4;  // x = x / 4; x is now 6
x %= 4;  // x = x % 4; x is now 2 (remainder)
```

---

## 3. **Comparison Operators**

Comparison operators are used to **compare two values**. They return either `true` or `false` depending on whether the comparison is correct.

### List of Comparison Operators:

| Operator | Description                       | Example         | Result           |
|----------|-----------------------------------|-----------------|------------------|
| `==`     | Equal to (value only)             | `5 == '5'`      | `true`           |
| `===`    | Strict equal to (value and type)  | `5 === '5'`     | `false`          |
| `!=`     | Not equal to (value only)         | `5 != '6'`      | `true`           |
| `!==`    | Strict not equal (value and type) | `5 !== '5'`     | `true`           |
| `>`      | Greater than                     | `5 > 3`         | `true`           |
| `<`      | Less than                        | `5 < 3`         | `false`          |
| `>=`     | Greater than or equal to         | `5 >= 5`        | `true`           |
| `<=`     | Less than or equal to            | `5 <= 4`        | `false`          |

### Key Concepts:

- **`==` (Equal to)**: Compares **only the value**, not the data type. So `5 == '5'` is `true` because the value `5` is the same, even though one is a number and the other is a string.
  
- **`===` (Strict equal to)**: Compares both **value and type**. `5 === '5'` is `false` because even though the value is the same, the types are different (number vs string).

### Examples:

```javascript
console.log(5 == '5');   // true, because the value is the same
console.log(5 === '5');  // false, because the types are different (number vs string)
console.log(10 != 9);    // true, because 10 is not equal to 9
console.log(10 !== '10');// true, because the value is the same but the type is different
console.log(5 > 3);      // true, 5 is greater than 3
console.log(5 <= 5);     // true, 5 is equal to 5
```

---

## 4. **Logical Operators**

Logical operators are used to combine multiple conditions. They return `true` or `false` depending on the logic.

### List of Logical Operators:

| Operator | Description                        | Example            | Result           |
|----------|------------------------------------|--------------------|------------------|
| `&&`     | Logical AND (both must be true)    | `true && false`    | `false`          |
| `||`     | Logical OR (one must be true)      | `true || false`    | `true`           |
| `!`      | Logical NOT (inverts true/false)   | `!true`            | `false`          |

### 1. **Logical AND (`&&`)**

- Returns `true` **only if both** conditions are true. If either condition is false, it returns `false`.

#### Example:

```javascript
let isAdult = true;
let hasID = true;

console.log(isAdult && hasID);  // true, because both are true
```

### 2. **Logical OR (`||`)**

- Returns `true` **if at least one** condition is true. It returns `false` only if both conditions are false.

#### Example:

```javascript
let isSunny = false;
let hasUmbrella = true;

console.log(isSunny || hasUmbrella);  // true, because one condition (hasUmbrella) is true
```

### 3. **Logical NOT (`!`)**

- **Reverses** the result. It turns `true` into `false` and `false` into `true`.

#### Example:

```javascript
let isHungry = true;
console.log(!isHungry);  // false, because !true is false
```

---

## Summary of Operators:

### Arithmetic Operators:

- `+`, `-`, `*`, `/`, `%`, `++`, `--`

### Assignment Operators:

- `=`, `+=`, `-=`, `*=`, `/=`, `%=`

### Comparison Operators:

- `==`, `===`, `!=`, `!==`, `>`, `<`, `>=`, `<=`

### Logical Operators:

- `&&`, `||`, `!`

---

These operators are the **building blocks** for controlling the flow of your code. You'll use them constantly as you write JavaScript
