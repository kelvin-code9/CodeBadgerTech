## 📝 Assignment: Working with Objects in JavaScript

### 🔹 Objective:

Apply your understanding of object literals, properties, methods, and the `this` keyword by creating and manipulating objects in JavaScript.

---

### ✅ Part 1: Create and Use an Object

1. **Create an object** named `car` with the following properties:

   * `brand`: a string (e.g., `"Toyota"`)
   * `model`: a string (e.g., `"Corolla"`)
   * `year`: a number (e.g., `2020`)
   * `start`: a method that logs:
     `"Starting the [brand] [model]..."` (use `this`)

2. **Test the object** by:

   * Printing the `brand` and `model` to the console.
   * Calling the `start` method.

---

### ✅ Part 2: Modify and Extend the Object

1. **Update** the `model` and `year` properties to new values.

2. **Add a new method** called `getCarAge` that calculates and logs the car's age based on the current year (e.g., 2025 − `year`).

   Example output:

   ```javascript
   This car is 5 years old.
   ```

3. **Call both methods** (`start` and `getCarAge`) and confirm they work with the updated values.

---

### ✅ Part 3: Create Your Own Object

1. Create an object of your choice (examples: `book`, `phone`, `animal`, `user`, etc.).
2. Include at least **3 properties** and **1 method**.
3. Make sure the method uses the `this` keyword to refer to the object's properties.
4. Modify at least one property after creation.
5. Log the updated object and call the method.

---

### ✅ Part 4: Short Answer Questions

Answer these questions in comments or a separate `.txt` file:

1. What is the purpose of the `this` keyword inside an object method?
2. What’s the difference between dot notation and bracket notation when accessing properties?
3. Why might you use bracket notation instead of dot notation?

---

### 📌 Bonus Challenge (Optional)

Create an object called `calculator` with methods:

* `add(a, b)` – returns the sum of `a` and `b`
* `subtract(a, b)` – returns the difference
* `multiply(a, b)` – returns the product
* `divide(a, b)` – returns the quotient

Call each method with sample inputs and log the result.

---

