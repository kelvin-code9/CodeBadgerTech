
## 📝 JavaScript Operators Assignment

### 🔹 **Instructions:**

* Answer all questions by writing JavaScript code.
* Use `console.log()` to show outputs.
* Add comments explaining what each line is doing.
* Try to predict the output before running the code.

---

### 🔢 **Section 1: Arithmetic Operators**

1. Write expressions using each arithmetic operator with `a = 12` and `b = 5`.
   Show the result of each.

2. What is the result of `10 % 3` and `15 % 4`?

3. Try using arithmetic operators with strings:

   ```javascript
   console.log("5" + 3);     // What do you think this will print?
   console.log("5" - 3);     // And this?
   ```

---

### 🔄 **Section 2: Increment & Decrement**

1. What’s the difference between `x++` and `++x`?
   Use the following code and explain:

   ```javascript
   let x = 7;
   console.log(x++);  // Postfix
   console.log(x);    
   console.log(++x);  // Prefix
   console.log(x);    
   ```

2. What will this print?

   ```javascript
   let y = 10;
   let result = y++ + ++y;
   console.log(result);
   ```

---

### ➕ **Section 3: Assignment Operators**

1. Given `let score = 20;`, apply each of the following:

   ```javascript
   score += 5;
   score -= 2;
   score *= 3;
   score /= 4;
   score %= 3;
   ```

   Log the value after each step and explain what's happening.

---

### ⚖️ **Section 4: Comparison Operators**

1. Predict the result of each:

   ```javascript
   console.log(5 == '5');     // ?
   console.log(5 === '5');    // ?
   console.log(5 != '5');     // ?
   console.log(5 !== '5');    // ?
   console.log(8 > 5);        // ?
   console.log(3 <= 2);       // ?
   ```
---

### 🔀 **Section 5: Logical Operators**

1. Evaluate the following expressions:

   ```javascript
   let a = true;
   let b = false;

   console.log(a && b);
   console.log(a || b);
   console.log(!a);
   ```

---

### 🧠 **Bonus Challenge: Guess the Output**

What will this print and why?

```javascript
let a = 3;
let b = a++ + ++a + a;
console.log(b);
```
