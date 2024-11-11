# **Module 9: Asynchronous JavaScript**

JavaScript can handle tasks that take time to complete, such as fetching data from a server, without making users wait or freezing the application. This concept of handling long-running tasks while keeping the program responsive is **asynchronous programming**. 

We’ll start by understanding **callbacks** and **promises** and finish with the more modern **async/await** approach, exploring how each improves handling asynchronous tasks.

---

## **Lesson 1: Callbacks and Promises**

### **1. Synchronous vs Asynchronous Code**

#### Real-World Analogy
Imagine you’re at a coffee shop:
- **Synchronous Code**: You place your order and wait at the counter until your coffee is ready before you do anything else.
- **Asynchronous Code**: You place your order and sit down to read a book, waiting for the barista to call your name when your coffee is ready. Meanwhile, you are free to do other things (like read) without blocking yourself from being productive.

#### Explanation
- **Synchronous Code**: Each task must complete before moving on to the next.
  - Example:
    ```javascript
    console.log("Order coffee");
    console.log("Wait for coffee");
    console.log("Enjoy coffee");
    // Output: Order coffee, Wait for coffee, Enjoy coffee
    ```

- **Asynchronous Code**: Some tasks (like brewing coffee) can take time, so JavaScript allows them to run in the background. This keeps the program responsive, allowing other tasks to run while waiting.
  - Example:
    ```javascript
    console.log("Order coffee");
    setTimeout(() => console.log("Enjoy coffee"), 2000); // Runs after 2 seconds
    console.log("Read book while waiting");
    // Output: Order coffee, Read book while waiting, Enjoy coffee (after 2 seconds)
    ```

### **2. Introduction to Callbacks**

#### What is a Callback?
A **callback** is a function you pass to another function, which will call it back (hence the name) when the task completes.

#### Callback in Action
- **Example**: Imagine ordering a coffee and leaving your phone number so the barista can call you back when it’s ready. You can go about your day and wait for their call instead of waiting in line.
  
  ```javascript
  function prepareCoffee(callback) {
      setTimeout(() => {
          console.log("Coffee is ready!");
          callback();
      }, 2000);
  }

  function enjoyCoffee() {
      console.log("Enjoying my coffee!");
  }

  prepareCoffee(enjoyCoffee);
  // Output after 2 seconds: Coffee is ready!, Enjoying my coffee!
  ```

#### **Advantages and Disadvantages of Callbacks**
- **Advantages**: Useful for simple tasks and keeps the code readable if only a few steps are needed.
- **Disadvantages**: With multiple tasks, callbacks can lead to “callback hell” where code becomes hard to follow because of deep nesting. 

---

### **3. Promises and `.then()`**

#### What is a Promise?
A **promise** represents a value that will be available sometime in the future. It can be in one of three states:
- **Pending**: The task has started but isn’t finished.
- **Fulfilled**: The task has completed successfully.
- **Rejected**: The task has failed.

#### Real-World Analogy for Promises
Imagine ordering a package online:
- The status is initially **Pending**.
- When it arrives, the promise is **Fulfilled**.
- If there’s an issue and the package is undeliverable, it’s **Rejected**.

#### Using Promises in Code
With promises, we handle asynchronous operations more clearly than with nested callbacks.

1. **Creating a Promise**
   ```javascript
   const coffeePromise = new Promise((resolve, reject) => {
       setTimeout(() => {
           let success = true; // Simulate a successful task
           if (success) {
               resolve("Coffee is ready!"); // Fulfilled
           } else {
               reject("Coffee machine broken!"); // Rejected
           }
       }, 2000);
   });
   ```

2. **Handling a Promise**
   - **`.then()`**: Runs when the promise is fulfilled.
   - **`.catch()`**: Runs if the promise is rejected.
   
   ```javascript
   coffeePromise
       .then((message) => console.log(message)) // Output after 2 seconds: Coffee is ready!
       .catch((error) => console.error(error)); // Only runs if there’s an error
   ```

#### Practical Task 1: Converting a Callback to a Promise
1. Convert the coffee preparation callback function (`prepareCoffee`) into a promise.

   **Callback Version**:
   ```javascript
   function prepareCoffee(callback) {
       setTimeout(() => {
           console.log("Coffee is ready!");
           callback();
       }, 2000);
   }
   prepareCoffee(() => console.log("Enjoy coffee"));
   ```

   **Promise Version**:
   ```javascript
   function prepareCoffee() {
       return new Promise((resolve, reject) => {
           setTimeout(() => {
               resolve("Coffee is ready!");
           }, 2000);
       });
   }

   prepareCoffee()
       .then((message) => {
           console.log(message);
           console.log("Enjoy coffee");
       })
       .catch((error) => console.error(error));
   ```

---

## **Lesson 2: Async/Await (ES7)**

JavaScript introduced `async` and `await` to make working with promises even more readable. It allows asynchronous code to look synchronous.

### **1. The `async` Keyword**

- **`async` Function**: Functions marked with `async` automatically return a promise.
- **Real-World Analogy**: Think of `async` as a promise for an eventual result. When you call an async function, you’re guaranteed that a result will come back in the future.

- **Example**:
  ```javascript
  async function makeCoffee() {
      return "Coffee is ready!";
  }

  makeCoffee().then((message) => console.log(message)); // Output: Coffee is ready!
  ```

### **2. The `await` Keyword**

- **`await`** pauses the function until the promise is resolved, letting us handle asynchronous tasks sequentially without the complexity of `.then()`.
- **Real-World Analogy**: Just as you wait for an ordered coffee to be served, `await` pauses the function, waiting for the result of the async task.

- **Example**:
  ```javascript
  async function getCoffee() {
      let coffee = await makeCoffee();
      console.log(coffee); // Output: Coffee is ready!
  }

  getCoffee();
  ```

### **3. Error Handling in Async Functions**

With `async/await`, we use `try...catch` for error handling.

- **Example**:
  ```javascript
  async function getCoffee() {
      try {
          let coffee = await makeCoffee();
          console.log(coffee); // Output: Coffee is ready!
      } catch (error) {
          console.error("Error:", error);
      }
  }

  getCoffee();
  ```

---

### **Practical Task 2: Refactor Callback/Promise Code to Async/Await**

1. **Convert Promise-based `prepareCoffee` to async/await**:
   ```javascript
   async function prepareCoffee() {
       return new Promise((resolve, reject) => {
           setTimeout(() => {
               resolve("Coffee is ready!");
           }, 2000);
       });
   }

   async function enjoyCoffee() {
       try {
           let coffee = await prepareCoffee();
           console.log(coffee);
           console.log("Enjoying coffee now!");
       } catch (error) {
           console.error("Error:", error);
       }
   }

   enjoyCoffee();
   ```

2. **Explanation**:
   - This code is more readable and easier to follow, as it resembles synchronous code flow.
   - Using `await` lets us avoid `.then()` chaining, making the code simpler.

---

### **Summary of Async/Await Benefits**

- **Improves readability**: Async/await looks and behaves more like synchronous code.
- **Easier error handling**: `try...catch` makes error handling straightforward.
- **Reduces nesting**: No need for deep nesting with callbacks or chaining with `.then()`.

--- 

This concludes our in-depth exploration of asynchronous JavaScript. With these concepts, you can now handle asynchronous tasks in a clear, modern, and efficient way.
