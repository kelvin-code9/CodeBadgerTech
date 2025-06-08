# JavaScript Dates Tutorial

---

## 1. What is a Date in JavaScript?

A Date object in JavaScript represents a single moment in time. It stores dates and times and lets you work with them, like getting the current date, extracting day/month/year, or manipulating dates.

---

## 2. Creating Date Objects

You can create a Date object in several ways:

```js
// Current date and time
const now = new Date();
console.log(now); 

// Specific date and time (year, month, day, hours, minutes, seconds, milliseconds)
// Note: month is 0-indexed (0 = January, 11 = December)
const specificDate = new Date(2025, 5, 8, 15, 30, 0);
console.log(specificDate); 

// Date from a date string
const dateFromString = new Date("2025-06-08T15:30:00");
console.log(dateFromString); 

// Date from milliseconds since January 1, 1970
const dateFromMs = new Date(1686267000000);
console.log(dateFromMs);
```

---

## 3. Getting Parts of a Date

You can extract parts of a date using these methods:

```js
const date = new Date();

console.log(date.getFullYear());  // e.g., 2025
console.log(date.getMonth());     // 0-11 (0 = Jan)
console.log(date.getDate());      // 1-31 (day of month)
console.log(date.getDay());       // 0-6 (0 = Sunday)
console.log(date.getHours());     // 0-23
console.log(date.getMinutes());   // 0-59
console.log(date.getSeconds());   // 0-59
console.log(date.getMilliseconds()); // 0-999
```

---

## 4. Setting Parts of a Date

You can modify parts of a date with `set` methods:

```js
const date = new Date();

date.setFullYear(2024);
date.setMonth(11);      // December
date.setDate(25);
date.setHours(10);
date.setMinutes(30);
date.setSeconds(0);

console.log(date);
```

---

## 5. Formatting Dates

JavaScript Date objects don't have built-in formatting options, but you can get common string formats like:

```js
const date = new Date();

console.log(date.toDateString());    // e.g., "Sun Jun 08 2025"
console.log(date.toTimeString());    // e.g., "15:30:00 GMT+0000 (UTC)"
console.log(date.toISOString());     // ISO format: "2025-06-08T15:30:00.000Z"
console.log(date.toLocaleDateString()); // Locale date, e.g., "6/8/2025"
console.log(date.toLocaleTimeString()); // Locale time, e.g., "3:30:00 PM"
```

---

## 6. Working with Timestamps

A timestamp is the number of milliseconds since January 1, 1970 (Unix epoch).

```js
const now = new Date();
const timestamp = now.getTime();  // get timestamp in ms
console.log(timestamp);

const dateFromTimestamp = new Date(timestamp);
console.log(dateFromTimestamp);
```

---

## 7. Example: Calculate Days Between Two Dates

```js
const startDate = new Date("2025-06-01");
const endDate = new Date("2025-06-08");

const diffMs = endDate - startDate;  // difference in milliseconds
const diffDays = diffMs / (1000 * 60 * 60 * 24);

console.log(`There are ${diffDays} days between the two dates.`);
```

---

## 8. Summary Example

```js
const birthday = new Date(1990, 0, 15); // Jan 15, 1990

console.log("Birthday:", birthday.toDateString());
console.log("Year:", birthday.getFullYear());
console.log("Month (0-indexed):", birthday.getMonth());
console.log("Day of month:", birthday.getDate());

// Change birthday to next year
birthday.setFullYear(birthday.getFullYear() + 1);

console.log("Next year's birthday:", birthday.toDateString());
```

---
