# 🔹 TypeScript Object Types

In TypeScript, **object types** describe the **shape of an object**, specifying the required properties and their types.

This is especially important in React when defining **props, state, or data models**.

---

## 🟦 1. Defining Object Types Inline

You can define the **structure of an object** directly when declaring a variable.

### ✅ Example

```ts
let user: { name: string; age: number } = {
  name: "Alice",
  age: 30,
};
```

### ❌ Type Safety

If you miss a property or provide the wrong type:

```ts
let person: { name: string; age: number } = {
  name: "Bob",
  // age: "thirty" // ❌ Error: Type 'string' is not assignable to type 'number'
};
```

---

## 🟦 2. Using Type Aliases for Reusability

For objects you’ll use repeatedly, define a **type alias**:

```ts
type Product = {
  id: number;
  name: string;
  price: number;
};

const item: Product = {
  id: 1,
  name: "Laptop",
  price: 999.99,
};
```

### ✅ Example in React Props

```tsx
type User = {
  name: string;
  isAdmin: boolean;
};

const Welcome = ({ user }: { user: User }) => {
  return <h1>Welcome, {user.isAdmin ? "Admin" : user.name}!</h1>;
};
```

---

## 🟦 3. Optional Properties (`?`)

Use `?` to make a property optional.

```ts
type Profile = {
  username: string;
  bio?: string; // Optional
};

const user1: Profile = { username: "dev123" };
const user2: Profile = { username: "coder456", bio: "Love TypeScript!" };
```

---

## 🟦 4. Readonly Properties

You can make properties **immutable** using `readonly`:

```ts
type Settings = {
  readonly theme: string;
};

const config: Settings = { theme: "dark" };
// config.theme = "light"; // ❌ Error: Cannot assign to 'theme' because it is a read-only property
```

---

## 🔍 Recap: Object Types Summary

| Feature         | Syntax Example                  | Purpose                  |
| --------------- | ------------------------------- | ------------------------ |
| **Inline Type** | `{ name: string; age: number }` | Quick object type        |
| **Type Alias**  | `type User = { ... }`           | Reusable type definition |
| **Optional**    | `bio?: string`                  | Optional fields          |
| **Readonly**    | `readonly theme: string`        | Prevent modifications    |

---

## 🧪 Hands-On Practice

```ts
type Book = {
  title: string;
  author: string;
  pages?: number;
};

const myBook: Book = {
  title: "TypeScript Basics",
  author: "Jane Doe",
  pages: 120,
};

// Uncomment to see the type error
// myBook.title = 42; // ❌ Error: number is not assignable to string
```

---

## 🧠 Bonus Tip: Nesting Object Types

You can nest objects:

```ts
type Company = {
  name: string;
  founder: { name: string; age: number };
};

const startup: Company = {
  name: "NextGen",
  founder: {
    name: "Alex",
    age: 35,
  },
};
```