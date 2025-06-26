
---

# 📝 **Assignment: Asynchronous JavaScript Basics**

## 👨‍🏫 Instructions

* Read each task carefully and try to implement the solution on your own.
* Try to understand what each function is doing, not just copy-paste!

---

## 🔹 **Part 1: Callbacks**

### ✅ Task 1: Delayed Greeting

Create a function `greetUser(name, callback)` that waits 2 seconds before greeting the user.

```javascript
function greetUser(name, callback) {
    // Your code here
}

greetUser("Ada", () => {
    console.log("Callback: Greeting done!");
});
```

**Expected Output:**

```
Hello, Ada!
Callback: Greeting done!
```

---

## 🔹 **Part 2: Promises**

### ✅ Task 2: Simulate Login with Promises

Write a function `loginUser()` that returns a promise. It should resolve after 1.5 seconds if the username is "admin", otherwise reject.

```javascript
function loginUser(username) {
    // Your code here
}

// Test it:
loginUser("admin")
    .then((message) => console.log("Success:", message))
    .catch((err) => console.log("Error:", err));
```

**Expected Output for `"admin"`:**

```
Success: Welcome back, admin!
```

**Expected Output for other input:**

```
Error: Invalid username.
```

---

## 🔹 **Part 3: Async/Await**

### ✅ Task 3: Fetch User Profile (Simulated)

Create an async function `getUserProfile()` that uses `await` to wait for a `fetchProfile()` promise. The `fetchProfile` function should resolve after 2 seconds.

```javascript
function fetchProfile() {
    // Return a promise that resolves to "Profile loaded"
}

async function getUserProfile() {
    // Await the result and print it
}

// Call the function
getUserProfile();
```

**Expected Output:**

```
Profile loaded
```

---

## ✨ Bonus Task: Combine Everything

Simulate making coffee:

1. `orderCoffee()` (returns a promise that resolves after 2 seconds).
2. `drinkCoffee()` (console logs a message).

Call them using `async/await`.

```javascript
function orderCoffee() {
    // Return a promise that resolves to "Coffee is ready!"
}

function drinkCoffee() {
    console.log("Drinking coffee...");
}

async function startCoffeeRoutine() {
    // Await the coffee, then drink it
}

startCoffeeRoutine();
```

---