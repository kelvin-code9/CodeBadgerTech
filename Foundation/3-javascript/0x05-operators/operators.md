# 🧮 JavaScript Operators:

JavaScript operators let you perform operations on variables and values — like doing math, assigning values, comparing things, and making logical decisions.

We'll break this down into **four major categories**:

1. Arithmetic Operators
2. Assignment Operators
3. Comparison Operators
4. Logical Operators

Each section will include **clear examples**, **step-by-step outputs**, and easy-to-follow explanations.

---

## 1. 🔢 Arithmetic Operators

Arithmetic operators are used for basic math: addition, subtraction, multiplication, etc.

### 📋 List of Arithmetic Operators

| Operator | Description            | Example | Result           |
| -------- | ---------------------- | ------- | ---------------- |
| `+`      | Addition               | `5 + 3` | `8`              |
| `-`      | Subtraction            | `5 - 3` | `2`              |
| `*`      | Multiplication         | `5 * 3` | `15`             |
| `/`      | Division               | `6 / 3` | `2`              |
| `%`      | Modulus (remainder)    | `5 % 3` | `2`              |
| `++`     | Increment (add 1)      | `x++`   | `6` (if `x = 5`) |
| `--`     | Decrement (subtract 1) | `x--`   | `4` (if `x = 5`) |

---

### 💡 Example with Output

```javascript
let a = 10;
let b = 3;

console.log("a + b =", a + b);  // 13
console.log("a - b =", a - b);  // 7
console.log("a * b =", a * b);  // 30
console.log("a / b =", a / b);  // 3.333...
console.log("a % b =", a % b);  // 1
```

---

## 🔄 Increment and Decrement (`++` and `--`)

These operators increase or decrease a variable by 1.
But how they behave depends on their **position**:

* `x++` or `x--` → **Postfix**: Returns the current value, then changes it.
* `++x` or `--x` → **Prefix**: Changes the value first, then returns it.

---

### 👀 Step-by-Step Example

```javascript
let x = 5;

console.log("Initial x:", x);        // 5

console.log("Postfix x++:", x++);    // 5 (prints 5, then x becomes 6)
console.log("After x++:", x);        // 6

console.log("Prefix ++x:", ++x);     // 7 (x becomes 7, then prints 7)
console.log("Now x:", x);            // 7

console.log("Postfix x--:", x--);    // 7 (prints 7, then x becomes 6)
console.log("After x--:", x);        // 6

console.log("Prefix --x:", --x);     // 5 (x becomes 5, then prints 5)
console.log("Final x:", x);          // 5
```

🧠 **Teaching Tip**:

* Use **postfix (`x++`)** when you want to use the original value first.
* Use **prefix (`++x`)** when you want to increment before using the value.

---

## 2. 🧾 Assignment Operators

Assignment operators assign values to variables — and some do math while assigning.

### 📋 List of Assignment Operators

| Operator | Description         | Example  | Equivalent To | Result (`x = 5`) |
| -------- | ------------------- | -------- | ------------- | ---------------- |
| `=`      | Assign              | `x = 5`  | —             | 5                |
| `+=`     | Add and assign      | `x += 3` | `x = x + 3`   | 8                |
| `-=`     | Subtract and assign | `x -= 2` | `x = x - 2`   | 3                |
| `*=`     | Multiply and assign | `x *= 4` | `x = x * 4`   | 20               |
| `/=`     | Divide and assign   | `x /= 2` | `x = x / 2`   | 2.5              |
| `%=`     | Modulus and assign  | `x %= 3` | `x = x % 3`   | 2                |

---

### 💡 Example with Output

```javascript
let x = 10;

x += 5;
console.log("x += 5 →", x);  // 15

x -= 3;
console.log("x -= 3 →", x);  // 12

x *= 2;
console.log("x *= 2 →", x);  // 24

x /= 4;
console.log("x /= 4 →", x);  // 6

x %= 4;
console.log("x %= 4 →", x);  // 2
```

---

## 3. 🤔 Comparison Operators

Comparison operators **compare values** and return `true` or `false`.

### 📋 List of Comparison Operators

| Operator | Description                     | Example     | Result  |
| -------- | ------------------------------- | ----------- | ------- |
| `==`     | Equal (value only)              | `5 == '5'`  | `true`  |
| `===`    | Strict equal (value & type)     | `5 === '5'` | `false` |
| `!=`     | Not equal (value only)          | `5 != '6'`  | `true`  |
| `!==`    | Strict not equal (value & type) | `5 !== '5'` | `true`  |
| `>`      | Greater than                    | `5 > 3`     | `true`  |
| `<`      | Less than                       | `5 < 3`     | `false` |
| `>=`     | Greater than or equal           | `5 >= 5`    | `true`  |
| `<=`     | Less than or equal              | `5 <= 4`    | `false` |

---

### 💡 Example with Output

```javascript
console.log(5 == '5');    // true
console.log(5 === '5');   // false
console.log(10 != 9);     // true
console.log(10 !== '10'); // true
console.log(5 > 3);       // true
console.log(5 <= 5);      // true
```

🧠 **Teaching Tip**:
Use `===` and `!==` most of the time — they avoid type-related surprises.

---

## 4. 🔐 Logical Operators

Used to combine **multiple conditions** and return `true` or `false`.

### 📋 List of Logical Operators

| Operator | Description                     | Example         | Result                         |        |   |         |        |
| -------- | ------------------------------- | --------------- | ------------------------------ | ------ | - | ------- | ------ |
| `&&`     | Logical AND (both must be true) | `true && false` | `false`                        |        |   |         |        |
| \`       |                                 | \`              | Logical OR (at least one true) | \`true |   | false\` | `true` |
| `!`      | Logical NOT (negation)          | `!true`         | `false`                        |        |   |         |        |

---

### ✅ Logical AND (`&&`)

Returns `true` **only if both** expressions are `true`.

```javascript
let isAdult = true;
let hasID = true;

console.log(isAdult && hasID);  // true
```

---

### ✅ Logical OR (`||`)

Returns `true` **if at least one** expression is `true`.

```javascript
let isSunny = false;
let hasUmbrella = true;

console.log(isSunny || hasUmbrella);  // true
```

---

### ❌ Logical NOT (`!`)

**Reverses** the value: `true` becomes `false`, and vice versa.

```javascript
let isHungry = true;

console.log(!isHungry);  // false
```

---

## 🧾 Summary

| Category   | Operators                                      |   |         |
| ---------- | ---------------------------------------------- | - | ------- |
| Arithmetic | `+`, `-`, `*`, `/`, `%`, `++`, `--`            |   |         |
| Assignment | `=`, `+=`, `-=`, `*=`, `/=`, `%=`              |   |         |
| Comparison | `==`, `===`, `!=`, `!==`, `>`, `<`, `>=`, `<=` |   |         |
| Logical    | `&&`, \`                                       |   | `, `!\` |

---

These operators are essential building blocks in JavaScript. Understanding **how they work** will help you make smart decisions, calculate values, and control your program’s behavior.