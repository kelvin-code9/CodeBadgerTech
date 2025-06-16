

# 📘 JavaScript Tutorial: Understanding and Handling Errors

Errors are how JavaScript tells you something is wrong. Understanding them will make you a better programmer and help you debug faster.

---

## 🔍 What is an Error?

An **error** is a problem that stops the script from running correctly. It might be a mistake in your code (like a typo), a logic problem, or something unexpected (like missing data from the server).

Think of it like trying to call someone on a phone that’s turned off. JavaScript will say: *“Hey! I can’t do that!”*

---

## ⚠️ Types of JavaScript Errors (with Real-Life Analogies)

### 1. **SyntaxError** – “Grammar Mistake”

Occurs when your code breaks the language rules (like forgetting a closing bracket).

```js
// Example
let name = "Sam"
console.log(name // ← Missing parenthesis
```

🧠 **Analogy**: Like writing a sentence without a period. The computer doesn’t know where to stop reading.

🖥 **Console Output:**

```
Uncaught SyntaxError: missing ) after argument list
```

---

### 2. **ReferenceError** – “Who is that?”

Happens when you try to use a variable that doesn’t exist.

```js
console.log(age); // 'age' was never declared
```

🧠 **Analogy**: You say “Call David,” but you never saved David’s number in your phone.

🖥 **Console Output:**

```
Uncaught ReferenceError: age is not defined
```

---

### 3. **TypeError** – “Wrong kind of thing”

Thrown when you try to do something with a value that isn’t allowed.

```js
let number = 5;
number(); // Trying to call a number like a function
```

🧠 **Analogy**: Like trying to wear a spoon as a hat. It’s a spoon, not a hat!

🖥 **Console Output:**

```
Uncaught TypeError: number is not a function
```

---

### 4. **RangeError** – “Too much or too little”

Thrown when a number is outside the allowed range.

```js
let items = new Array(1000000000000); // Too big!
```

🧠 **Analogy**: Like trying to open 1 billion browser tabs. Your computer says, “NOPE.”

🖥 **Console Output:**

```
Uncaught RangeError: Invalid array length
```

---

### 5. **EvalError** – “Bad use of `eval()`” (Rarely used)

Occurs when there is a problem using the `eval()` function, though modern JavaScript rarely throws this anymore.

---

## 🛡️ Handling Errors with `try...catch`

Instead of crashing, you can catch errors and keep going.

```js
try {
  // Code that might fail
  let result = 10 / 0;
  console.log(result);
  console.log(unknownVar); // ReferenceError
} catch (error) {
  // Error caught here
  console.error("Caught error:", error.message);
}
```

🖥 **Console Output:**

```
Infinity
Caught error: unknownVar is not defined
```

💡 The code **inside `catch` still runs** even if the error occurs in `try`.

---

## 🔁 Always Runs: `finally`

No matter what happens—error or no error—the `finally` block always runs.

```js
try {
  JSON.parse('{"name": "Jane"}');
} catch (e) {
  console.log("Something went wrong.");
} finally {
  console.log("Done parsing.");
}
```

🖥 **Console Output:**

```
Done parsing.
```

---

## 🧨 Throwing Your Own Errors with `throw`

You can create and throw your own errors when something is wrong.

```js
function withdraw(amount) {
  if (amount < 0) {
    throw new Error("Amount must be positive");
  }
  console.log("Withdrawing", amount);
}

try {
  withdraw(-100);
} catch (e) {
  console.error("Custom error:", e.message);
}
```

🖥 **Console Output:**

```
Custom error: Amount must be positive
```

---

## 🧰 Advanced Example: Validating User Input

```js
function login(username, password) {
  if (!username || !password) {
    throw new Error("Username and password are required");
  }

  // Dummy login check
  if (username !== "admin" || password !== "1234") {
    throw new Error("Invalid credentials");
  }

  return "Login successful!";
}

try {
  const result = login("admin", "");
  console.log(result);
} catch (e) {
  console.error("Login failed:", e.message);
}
```

🖥 **Console Output:**

```
Login failed: Username and password are required
```

---

## 🧪 Recap Table

| 🔸 Error Type  | 🚫 Trigger                   | 💬 Example           |
| -------------- | ---------------------------- | -------------------- |
| SyntaxError    | Code that can't be parsed    | `let x = [1, 2, 3`   |
| ReferenceError | Using undefined variable     | `console.log(foo)`   |
| TypeError      | Wrong type used in operation | `null.toUpperCase()` |
| RangeError     | Number out of bounds         | `new Array(-1)`      |
| EvalError      | Misusing `eval()` (legacy)   | `eval(")`            |

---

## 🧠 Bonus Tips

* Always read the **error message**. It tells you the type of error, line number, and details.
* Use `console.log()` to debug and check values.
* Wrap risky code (like API calls or JSON parsing) in `try...catch`.
* Don’t ignore errors silently—at least log them.

---