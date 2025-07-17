
# 🔹 TypeScript Arrays & Union Types

In React apps, we often need to handle **lists of data** or **values that can be multiple types**. TypeScript makes this safer with:

* **Arrays** for lists
* **Union Types** for variables that can hold multiple possible types

Let’s break them down.

---

## 🟦 1. Arrays in TypeScript

Arrays hold **multiple values of the same type**, with the type declared for the entire collection.

### ✅ Basic Example

```ts
let scores: number[] = [90, 85, 100];
let names: string[] = ["Alice", "Bob", "Charlie"];
```

Alternatively:

```ts
let flags: Array<boolean> = [true, false, true];
```

### ✅ Manipulating Arrays

You can use array methods safely:

```ts
let fruits: string[] = ["Apple", "Banana"];
fruits.push("Cherry");  // ✅ Only strings allowed
```

### ❌ Type Safety

```ts
let ids: number[] = [1, 2, 3];
// ids.push("four"); ❌ Error: Argument of type 'string' is not assignable to parameter of type 'number'
```

---

## 🧩 Arrays of Objects

We can define arrays of specific object shapes:

```ts
type User = {
  name: string;
  age: number;
};

const users: User[] = [
  { name: "John", age: 25 },
  { name: "Jane", age: 30 },
];
```

This is common when **rendering lists in React**:

```tsx
const UserList = ({ users }: { users: User[] }) => {
  return (
    <ul>
      {users.map(user => (
        <li key={user.name}>{user.name} - {user.age} years old</li>
      ))}
    </ul>
  );
};
```

---

## 🟦 2. Union Types (`|`)

Union types allow a variable to be **one of several types**.

### ✅ Basic Example

```ts
let value: string | number;

value = "Hello"; // OK
value = 123;     // OK
// value = true; // ❌ Error: boolean is not assignable to string | number
```

### ✅ Union in Arrays

```ts
let mixed: (string | number)[] = ["Alice", 42, "Bob", 99];
```

### ✅ Example in React Props

```tsx
const Status = ({ code }: { code: "success" | "error" | "loading" }) => {
  return <p>Status: {code}</p>;
};
```

Now `code` can **only** be `"success"`, `"error"`, or `"loading"`.

---

## 🔍 Recap: Arrays & Union Types

| Concept   | Syntax Example                | Purpose                     |
| --------- | ----------------------------- | --------------------------- |
| **Array** | `let nums: number[] = [1, 2]` | List of values of same type |
| **Union** | `let val: string \| number`   | Multiple possible types     |
| **Combo** | `(string \| number)[]`        | Array of string OR number   |

---

## 🧪 Hands-On Practice

```ts
let colors: string[] = ["red", "blue", "green"];
// colors.push(5); // ❌ Error

let idOrName: string | number = "user123";
idOrName = 456; // ✅

let items: (string | boolean)[] = ["active", true, "inactive", false];
```

---

## 🧠 Bonus Tip: Type Aliases

You can create a **reusable type alias** for clarity:

```ts
type StatusType = "success" | "error" | "loading";

const status: StatusType = "loading";
```

---