
# 🔹 TypeScript: `interface` vs `type`

Both `interface` and `type` in TypeScript are used to **describe the shape of objects**, but there are important differences in **capabilities, flexibility, and use cases**.

Let’s break them down with clear examples.

---

## 🟦 1. What is an `interface`?

An **interface** defines the shape of an **object, class, or function signature**.

### ✅ Example

```ts
interface User {
  name: string;
  age: number;
}

const user: User = {
  name: "Alice",
  age: 30,
};
```

---

## 🟦 2. What is a `type` alias?

A **type alias** can define **primitive types, object shapes, unions, intersections**, and more.

### ✅ Example

```ts
type Product = {
  id: number;
  name: string;
};

const item: Product = {
  id: 1,
  name: "Laptop",
};
```

---

## 🟦 3. Key Differences

| Feature                    | `interface`               | `type`                            |
| -------------------------- | ------------------------- | --------------------------------- |
| **Extending**              | `extends` keyword         | Intersection (`&`)                |
| **Merging**                | Automatically merges      | Cannot merge automatically        |
| **Primitives/Unions**      | ❌ Objects only            | ✅ Can represent primitives/unions |
| **Implements**             | For classes               | Less common in class-based coding |
| **React Props Preference** | Often preferred for props | Also valid — stylistic choice     |

---

## 🟦 4. Extending / Combining

### ✅ `interface` Extending

```ts
interface Person {
  name: string;
}

interface Employee extends Person {
  role: string;
}

const emp: Employee = {
  name: "John",
  role: "Engineer",
};
```

### ✅ `type` Intersection

```ts
type Person = { name: string };
type Employee = Person & { role: string };

const emp: Employee = {
  name: "John",
  role: "Engineer",
};
```

---

## 🟦 5. Declaration Merging

`interface` supports **declaration merging**:

```ts
interface Profile {
  username: string;
}

interface Profile {
  isAdmin: boolean;
}

const admin: Profile = {
  username: "dev123",
  isAdmin: true,
};
```

But with `type`, you **cannot** redefine/merge:

```ts
type Profile = { username: string };
// type Profile = { isAdmin: boolean }; // ❌ Error: Duplicate identifier
```

---

## 🔍 Recap: When to Use

| Use Case                         | Recommended |
| -------------------------------- | ----------- |
| Object shapes (esp. React props) | `interface` |
| Primitive, union, tuple types    | `type`      |
| Extending multiple types         | `type`      |
| Declaration merging needed       | `interface` |

---

## 🧪 Hands-On Practice

```ts
interface Animal {
  species: string;
}

interface Pet extends Animal {
  name: string;
}

type Color = "red" | "green" | "blue";
type Size = "small" | "medium" | "large";

type Product = {
  name: string;
  size: Size;
  color: Color;
};
```

---

## 🧠 Bonus Tip: Style Consistency

For **React Props** and **object shapes**, `interface` is generally preferred for clarity and extendability:

```tsx
interface ButtonProps {
  label: string;
  onClick: () => void;
}

const Button = ({ label, onClick }: ButtonProps) => (
  <button onClick={onClick}>{label}</button>
);
```

But for **union types or combinations**, `type` is your friend.
