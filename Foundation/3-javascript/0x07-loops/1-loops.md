## Introduction to Loops in **JavaScript**

#### **Introduction to Loops**
In programming, loops are used to repeat a block of code multiple times. Instead of writing repetitive code manually, loops allow you to run the same code block a specific number of times or until a particular condition is met.

JavaScript offers several types of loops, each serving different purposes. The three most common loops in JavaScript are:
- **`while` loop**
- **`do-while` loop**
- **`for` loop**

---

### **1. While Loop**

#### **Syntax:**
```javascript
while (condition) {
    // Code block to be executed
}
```

- The `while` loop continues to execute the code block as long as the condition is **true**.
- If the condition becomes **false**, the loop stops.

#### **Example:**
```javascript
let count = 1;
while (count <= 5) {
    console.log("Count is: " + count);
    count++; // increment the count by 1
}
```
- In this example, the loop will print the count from 1 to 5. After each iteration, the value of `count` is increased by 1.
- Once `count` exceeds 5, the loop will stop.

#### **Points to Remember:**
- If the condition is always true, the loop will run infinitely, which may cause the program to freeze.
- Make sure to update the condition inside the loop (e.g., `count++`) to avoid infinite loops.

---

### **2. Do-While Loop**

#### **Syntax:**
```javascript
do {
    // Code block to be executed
} while (condition);
```

- The `do-while` loop is similar to the `while` loop, but with one key difference: the code block is executed **at least once**, even if the condition is false from the start. The condition is checked **after** the code block runs.

#### **Example:**
```javascript
let count = 6;
do {
    console.log("Count is: " + count);
    count++;
} while (count <= 5);
```
- In this example, the message will be printed once even though `count` is 6 and doesn’t meet the condition `count <= 5`.
- After the first execution, the condition is checked, and since it's false, the loop stops.

#### **Points to Remember:**
- Use the `do-while` loop when you want the code block to execute **at least once**, regardless of the condition.

---

### **3. For Loop**

#### **Syntax:**
```javascript
for (initialization; condition; increment/decrement) {
    // Code block to be executed
}
```

- The `for` loop is commonly used when you know in advance how many times you want the loop to execute.
- It consists of three parts:
  1. **Initialization**: This is executed before the loop starts and is usually used to declare and initialize a counter variable.
  2. **Condition**: The loop runs as long as this condition is **true**.
  3. **Increment/Decrement**: This is executed after each iteration of the loop, typically to update the counter variable.

#### **Example:**
```javascript
for (let i = 1; i <= 5; i++) {
    console.log("i is: " + i);
}
```
- In this example, the loop starts with `i = 1`, and it runs as long as `i <= 5`. After each iteration, `i` is incremented by 1 (`i++`).
- The loop will print the value of `i` from 1 to 5.

#### **Points to Remember:**
- The `for` loop is a compact and structured way of handling loops where the number of iterations is known beforehand.
- It’s widely used because of its clarity and ease of control over the loop iteration process.

---

### **Key Differences Between `while`, `do-while`, and `for` Loops:**

1. **`while` loop**: The condition is checked **before** the execution of the loop. If the condition is false from the beginning, the loop will never execute.
2. **`do-while` loop**: The code block is executed **at least once** because the condition is checked **after** the execution.
3. **`for` loop**: The most structured loop, commonly used when the number of iterations is known in advance. The initialization, condition, and update (increment/decrement) are all handled in one place.

---

### **Practical Questions for Testing:**

1. **`while` Loop Practical Questions:**
   - Write a JavaScript program to print numbers from 1 to 10 using a `while` loop.
   - Modify the above program to print only **even** numbers from 1 to 10 using a `while` loop.
   - Write a program to calculate the sum of all numbers from 1 to 100 using a `while` loop.
   - Challenge: Write a program that continues to ask the user for input using `prompt` until they enter the word "stop" using a `while` loop.

2. **`do-while` Loop Practical Questions:**
   - Write a JavaScript program to print numbers from 1 to 5 using a `do-while` loop.
   - Modify the above program to print **odd** numbers from 1 to 5 using a `do-while` loop.
   - Write a program that prompts the user to enter a number, then keeps asking for input until they enter a number greater than 10, using a `do-while` loop.
   - Challenge: Write a program that prompts the user for their name and greets them once, even if the input is empty, using a `do-while` loop.

3. **`for` Loop Practical Questions:**
   - Write a JavaScript program to print numbers from 1 to 10 using a `for` loop.
   - Modify the above program to print the multiplication table of 5 (i.e., 5x1, 5x2, 5x3, ..., 5x10) using a `for` loop.
   - Write a program to print the **factorial** of a number (e.g., factorial of 5 is 5 x 4 x 3 x 2 x 1 = 120) using a `for` loop.
   - Challenge: Write a program to print the Fibonacci sequence up to the 10th number using a `for` loop.

4. **Advanced Practical Questions:**
   - Write a program to print the first 10 prime numbers using a `for` loop.
   - Write a program to reverse a string input by the user using a `for` loop.
   - Challenge: Write a program that asks the user to enter 5 numbers, stores them in an array, and prints the sum of the numbers using a `for` loop.

---

### **Summary:**
- **`while` loop** is used when you want to execute a block of code as long as a condition remains true.
- **`do-while` loop** ensures that the code block is executed at least once, checking the condition afterward.
- **`for` loop** is ideal when you know in advance how many times the loop should run.

Loops are essential tools in programming, helping automate repetitive tasks, making your code more efficient and reducing manual effort. With practice, you’ll master these different looping structures and know when to use each one effectively.

---
