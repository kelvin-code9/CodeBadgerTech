
---

# JavaScript Conditionals: Combining Conditions with Logical Operators `&&` (AND) and `||` (OR)

---

## Why Combine Conditions?

When programming, decisions often depend on **more than one factor**. Instead of writing nested or repeated `if` statements, you can combine multiple conditions into **one complex condition**.

Logical operators allow you to do exactly that.

---

## NOTE: the symbol for 'or' is '||' but when using it in the table i will be writing it as or. this is because markdown fails to properly interpret the symbol when it is in a table

## Logical Operators Overview

| Operator | Name | Meaning                                   |    |                                            |
| -------- | ---- | ----------------------------------------- | -- | ------------------------------------------ |
| `&&`     | AND  | True only if **both** conditions are true |    |                                            |
| or       |   OR | True if **at least one** condition is true |

---

## The AND Operator: `&&`

### What does `&&` mean?

The `&&` operator (AND) requires **all conditions** on its left and right to be true for the entire expression to be true.

### Truth Table for `&&`:

| Condition 1 | Condition 2 | Result (`Condition1 && Condition2`) |
| ----------- | ----------- | ----------------------------------- |
| true        | true        | true                                |
| true        | false       | false                               |
| false       | true        | false                               |
| false       | false       | false                               |

### Example 1: Simple AND

```javascript
let isLoggedIn = true;
let hasPaid = false;

if (isLoggedIn && hasPaid) {
    console.log("Access granted.");
} else {
    console.log("Access denied.");
}
// Output: Access denied.
```

**Explanation:**
Even though `isLoggedIn` is true, `hasPaid` is false, so the whole condition fails.

---

## The OR Operator: `||`

### What does `||` mean?

The `||` operator (OR) requires **at least one** of the conditions to be true for the entire expression to be true.

### Truth Table for `||`:

| Condition 1 | Condition 2 | Result (`Condition1 or Condition2`) |
| ----------- | ----------- | ----------------------------------- |
| true        | true        | true                                |
| true        | false       | true                                |
| false       | true        | true                                |
| false       | false       | false                               |
   |

### Example 2: Simple OR

```javascript
let isHoliday = false;
let isWeekend = true;

if (isHoliday || isWeekend) {
    console.log("Day off!");
} else {
    console.log("Work day.");
}
// Output: Day off!
```

**Explanation:**
Because `isWeekend` is true, the whole condition is true even though `isHoliday` is false.

---

## Operator Precedence: `&&` vs `||`

When you combine `&&` and `||` in the **same condition**, JavaScript evaluates `&&` **before** `||`.

### Example:

```javascript
let a = true;
let b = false;
let c = true;

if (a || b && c) {
    console.log("True!");
} else {
    console.log("False!");
}
// Output: True!
```

**Why?**
`b && c` is evaluated first (false && true = false).
Then `a || false` is evaluated (true || false = true).

---

## Using Parentheses to Control Evaluation Order

You can use parentheses `()` to change the order of evaluation and make conditions clearer.

### Example:

```javascript
let a = false;
let b = true;
let c = true;

if ((a || b) && c) {
    console.log("True!");
} else {
    console.log("False!");
}
// Output: True!
```

**Explanation:**
`(a || b)` evaluates first → `(false || true)` → `true`
Then `true && c` → `true && true` → `true`

---

## Combining Multiple Conditions

You can chain many conditions using `&&` and `||` to handle complex logic.

### Example:

```javascript
let age = 25;
let hasLicense = true;
let isSober = true;

if (age >= 18 && hasLicense && isSober) {
    console.log("Allowed to drive.");
} else {
    console.log("Not allowed to drive.");
}
// Output: Allowed to drive.
```

---

## Practical Examples with Explanations

### Example 1: Access Control

```javascript
let username = "user1";
let password = "secret123";

if (username === "user1" && password === "secret123") {
    console.log("Login successful!");
} else {
    console.log("Login failed.");
}
// Output: Login successful!
```

### Example 2: Weekend or Holiday

```javascript
let isWeekend = false;
let isHoliday = false;

if (isWeekend || isHoliday) {
    console.log("No work today.");
} else {
    console.log("Work day.");
}
// Output: Work day.
```

---

## Common Mistakes to Avoid

1. **Confusing `&&` with `||`:**

   * `&&` needs *all* to be true
   * `||` needs *at least one* true

2. **Forgetting parentheses:**
   When combining both, use parentheses to clarify intent and avoid bugs.

3. **Using assignment `=` instead of comparison `==` or `===`:**
   Example wrong: `if (a = 5 && b = 10) { ... }`
   Should be: `if (a === 5 && b === 10) { ... }`

---

## Summary Table

Logical Operator | Meaning | True if...             | Example                   | Explanation
-----------------|---------|------------------------|---------------------------|-------------------------------------
&&               | AND     | All conditions are true| age > 18 && hasID         | Both sides must be true
or               | OR      | At least one is true   | isHoliday || isWeekend    | Either side being true is enough



## Final Notes

* Use `&&` to require **all** conditions to pass.
* Use `||` to accept **any** one condition.
* Use parentheses to **control evaluation order** and make your code easier to read.
* Combining these operators lets you write **complex, powerful decisions** in a single `if` statement.

---