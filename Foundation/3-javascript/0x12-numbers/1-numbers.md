
## 1. JavaScript Number Basics & Limitations

JavaScript uses **one numeric type**: a 64-bit floating point number (following the IEEE 754 standard). This means all numbers — whether integers or decimals — are represented as floating point.

**Why does this matter?**
Because floating point math can cause **precision errors** with decimal numbers:

```js
console.log(0.1 + 0.2);          // 0.30000000000000004 (not exactly 0.3)
console.log(0.1 + 0.2 === 0.3);  // false
```

This happens because some decimals can’t be represented exactly in binary floating point.

---

## 2. Safe Integer Range

JavaScript safely represents integers between:

* **`Number.MAX_SAFE_INTEGER` = 9007199254740991 (2^53 - 1)**
* **`Number.MIN_SAFE_INTEGER` = -9007199254740991**

Beyond these limits, integers lose precision.

```js
console.log(Number.MAX_SAFE_INTEGER); // 9007199254740991
console.log(9007199254740992 === 9007199254740993); // true — precision lost!
```

If you need integers bigger than this, use **BigInt** (covered later).

---

## 3. Special Numeric Values You Need to Know

* **`Infinity`** and **`-Infinity`** represent numbers beyond the largest/smallest numbers.
* **`NaN`** (Not-a-Number) means an invalid number operation or parse.

```js
console.log(1 / 0);            // Infinity
console.log(-1 / 0);           // -Infinity
console.log("foo" * 3);        // NaN
console.log(typeof NaN);       // "number" — tricky!
```

To check for NaN, **always use**:

```js
Number.isNaN(NaN);   // true
Number.isNaN("foo"); // false (correct!)
isNaN("foo");        // true (legacy behavior, avoid)
```

---

## 4. Parsing Numbers from Strings

Sometimes you want to convert strings into numbers:

* `Number("123.45")` converts the *entire* string to a number or returns NaN.
* `parseInt("123px")` extracts leading integers until invalid character.
* `parseFloat("123.45px")` extracts leading float until invalid character.

```js
console.log(Number("123.45"));    // 123.45
console.log(parseInt("123px"));   // 123
console.log(parseFloat("123.45px")); // 123.45
console.log(Number("foo"));       // NaN
console.log(parseInt("foo"));     // NaN
```

---

## 5. Rounding Numbers: Methods & Differences

JavaScript offers several ways to round numbers:

| Method         | Description                          | Example               |
| -------------- | ------------------------------------ | --------------------- |
| `Math.floor()` | Rounds *down* to the nearest integer | `Math.floor(4.7) → 4` |
| `Math.ceil()`  | Rounds *up* to the nearest integer   | `Math.ceil(4.2) → 5`  |
| `Math.round()` | Rounds to the *nearest* integer      | `Math.round(4.5) → 5` |
| `Math.trunc()` | Removes fractional part (truncates)  | `Math.trunc(4.7) → 4` |

Examples:

```js
const num = 4.7;

console.log(Math.floor(num));  // 4
console.log(Math.ceil(num));   // 5
console.log(Math.round(num));  // 5
console.log(Math.trunc(num));  // 4
```

---

## 6. Fixing Floating Point Precision Errors

To avoid floating point rounding problems when working with decimals (e.g., money), multiply first, then round, then divide back:

```js
function preciseAdd(a, b, decimals = 2) {
  const factor = 10 ** decimals;
  return Math.round((a + b) * factor) / factor;
}

console.log(preciseAdd(0.1, 0.2)); // 0.3 (correct)
```

Also, you can use `.toFixed()` to format decimals as strings with fixed decimal places:

```js
console.log((0.1 + 0.2).toFixed(2)); // "0.30" (string!)
```

Note: `.toFixed()` returns a string, so convert back to number if needed:

```js
const fixed = Number((0.1 + 0.2).toFixed(2)); // 0.3 (number)
```

---

## 7. BigInt: Working with Huge Integers Safely

JavaScript's `BigInt` lets you work with integers larger than `Number.MAX_SAFE_INTEGER` **without losing precision**:

```js
const hugeInt = 900719925474099123456789n; // Note the 'n' suffix
const sum = hugeInt + 10n;

console.log(sum); // 900719925474099123456799n
```

**Important:** You cannot mix BigInt and Number in operations:

```js
console.log(10n + 5); // TypeError: Cannot mix BigInt and other types
```

Always convert or stick to one type.

---

## 8. Common Math Methods & Utilities

JavaScript’s `Math` object provides many useful functions:

| Method          | Description                | Example                  |
| --------------- | -------------------------- | ------------------------ |
| `Math.abs(x)`   | Absolute value             | `Math.abs(-5) → 5`       |
| `Math.max(...)` | Max value                  | `Math.max(1,5,3) → 5`    |
| `Math.min(...)` | Min value                  | `Math.min(1,5,3) → 1`    |
| `Math.pow(x,y)` | x to the power of y        | `Math.pow(2,3) → 8`      |
| `Math.sqrt(x)`  | Square root                | `Math.sqrt(9) → 3`       |
| `Math.cbrt(x)`  | Cube root                  | `Math.cbrt(27) → 3`      |
| `Math.exp(x)`   | e to the power of x        | `Math.exp(1) → 2.718...` |
| `Math.log(x)`   | Natural logarithm (base e) | `Math.log(Math.E) → 1`   |
| `Math.log10(x)` | Log base 10                | `Math.log10(1000) → 3`   |

---

## 9. Generate Random Numbers

Random number generation is easy but often misunderstood:

```js
// Random float between 0 (inclusive) and 1 (exclusive)
const r = Math.random();
console.log(r);
```

To generate a **random integer between min and max (inclusive):**

```js
function randomInt(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

console.log(randomInt(1, 10)); // Could be any integer from 1 to 10
```

---

## 10. New ES6+ Number Utilities

Use these to perform reliable checks:

| Method                    | What It Does                               |
| ------------------------- | ------------------------------------------ |
| `Number.isFinite(x)`      | Checks if `x` is a finite number           |
| `Number.isInteger(x)`     | Checks if `x` is an integer                |
| `Number.isSafeInteger(x)` | Checks if `x` is within safe integer range |
| `Number.isNaN(x)`         | Checks if `x` is the NaN value             |

Examples:

```js
console.log(Number.isFinite(123));       // true
console.log(Number.isFinite(Infinity));  // false
console.log(Number.isInteger(10));        // true
console.log(Number.isInteger(10.5));      // false
console.log(Number.isSafeInteger(9007199254740991)); // true
console.log(Number.isSafeInteger(9007199254740992)); // false
```

---

## 11. Useful Helper Functions

### Clamp a number within a range

```js
function clamp(num, min, max) {
  return Math.min(Math.max(num, min), max);
}

console.log(clamp(10, 1, 5));  // 5
console.log(clamp(-1, 0, 100)); // 0
console.log(clamp(50, 0, 100)); // 50
```

### Round a number to N decimal places

```js
function roundTo(value, decimals) {
  const factor = 10 ** decimals;
  return Math.round(value * factor) / factor;
}

console.log(roundTo(3.1415926535, 3)); // 3.142
console.log(roundTo(1.005, 2));         // 1.01 — fixes float precision issue
```

---

## 12. Numeric Edge Cases

* Dividing by zero returns Infinity or -Infinity:

  ```js
  console.log(1 / 0);   // Infinity
  console.log(-1 / 0);  // -Infinity
  ```

* 0 divided by 0 returns NaN:

  ```js
  console.log(0 / 0);   // NaN
  ```

Always watch out for these when writing math-heavy code.

---

# Summary

* JavaScript numbers are floating point, which can cause precision quirks.
* Use rounding techniques to fix decimal errors.
* Use BigInt for safely handling very large integers.
* Use `Math` methods for common math operations.
* Use ES6+ `Number` methods for accurate type checking.
* Always handle special values like `NaN`, `Infinity`, and edge cases properly.
* Implement helpers like `clamp` and `roundTo` for cleaner, reusable code.

