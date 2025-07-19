# 🚨 Common Errors and How to Fix Them in React + TypeScript

---

## 🟥 1. **JSX Must Return a Single Parent Element**

### ✅ **Explanation**

When a component returns JSX, it must have **one single parent element wrapping everything**.
If you try to return multiple sibling elements **without a wrapper**, React throws an error.

### ✅ **Example of the Error**

```tsx
function MyComponent() {
  return (
    <h1>Hello</h1>
    <p>Welcome!</p>
  );
}
```

### ✅ **Error Message**

```
Adjacent JSX elements must be wrapped in an enclosing tag.
```

### ✅ **How to Fix**

Wrap everything inside a:

* A container element like `<div>`, **OR**
* A React Fragment `<>...</>`

```tsx
function MyComponent() {
  return (
    <div>
      <h1>Hello</h1>
      <p>Welcome!</p>
    </div>
  );
}
```

**OR using Fragments:**

```tsx
function MyComponent() {
  return (
    <>
      <h1>Hello</h1>
      <p>Welcome!</p>
    </>
  );
}
```

### ✅ **Bonus Tip**

Fragments don't add extra HTML elements to the DOM — they are **invisible wrappers**.

---

## 🟥 2. **Undefined or Missing Props**

### ✅ **Explanation**

When you define props in a component using **TypeScript types**, you must **provide them correctly** when using the component.

If you forget to pass them, or pass them with the **wrong name or type**, TypeScript (and sometimes React) will complain.

### ✅ **Example of the Error**

```tsx
type ProfileProps = {
  name: string;
};

function Profile({ name }: ProfileProps) {
  return <p>Name: {name}</p>;
}

// ❌ Forgetting to pass `name` prop
<Profile />;
```

### ✅ **TypeScript Error**

```
Property 'name' is missing in type '{}' but required in type 'ProfileProps'.
```

### ✅ **How to Fix**

Always pass the **required props**:

```tsx
<Profile name="Favour" />;
```

### ✅ **Bonus Tip**

If a prop is **optional**, declare it with a `?`:

```tsx
type ProfileProps = {
  name?: string;
};
```

Now this works:

```tsx
<Profile />;
```

---

## 🟥 3. **Invalid Return Values (Returning Objects Instead of JSX)**

### ✅ **Explanation**

A React component **must return JSX (or `null`)**, not **plain objects or arrays of objects**.

Returning an object directly causes an error.

### ✅ **Example of the Error**

```tsx
function Profile() {
  return {
    name: "Favour",
    age: 25
  };
}
```

### ✅ **Error Message**

```
Objects are not valid as a React child (found: object with keys {name, age}).
```

### ✅ **How to Fix**

Make sure you return **JSX**:

```tsx
function Profile() {
  const user = { name: "Favour", age: 25 };

  return (
    <div>
      <p>Name: {user.name}</p>
      <p>Age: {user.age}</p>
    </div>
  );
}
```

### ✅ **Bonus Tip**

You can return `null` if you don't want to render anything:

```tsx
function Profile() {
  return null;
}
```

---

## 🟥 4. **Case Sensitivity Errors**

### ✅ **Explanation**

JSX is **case-sensitive**.
This matters for:

* **Component names:** Custom components must start with an **uppercase letter**.
* **Props:** Props must match **exact casing**.

### ✅ **Example of the Error**

```tsx
function profile() {
  return <p>My Profile</p>;
}

// ❌ Using lowercase component name
<profile />;
```

### ✅ **React Error Message**

```
The tag <profile> is unrecognized in this browser.
```

### ✅ **How to Fix**

Define and use components with **PascalCase** (uppercase start):

```tsx
function Profile() {
  return <p>My Profile</p>;
}

<Profile />;
```

Similarly, props must match:

```tsx
function Profile({ userName }: { userName: string }) {
  return <p>{userName}</p>;
}

<Profile userName="Favour" />; // ✅ Correct

<Profile username="Favour" />; // ❌ Will cause a TypeScript error
```

---

## 🟥 5. **TypeScript Error Messages (Basics)**

### ✅ **Explanation**

TypeScript shows errors when:

* You use **wrong types**.
* You **miss required props**.
* You **mismatch types between parent and child components**.

### ✅ **Example: Type Mismatch**

```tsx
type ProfileProps = {
  age: number;
};

function Profile({ age }: ProfileProps) {
  return <p>Age: {age}</p>;
}

// ❌ Passing wrong type
<Profile age="twenty-five" />;
```

### ✅ **TypeScript Error Message**

```
Type 'string' is not assignable to type 'number'.
```

### ✅ **How to Fix**

```tsx
<Profile age={25} />;
```

---

## ✅ Bonus: Common TS Error Examples and Solutions

| TypeScript Error                         | Cause                               | Solution                              |
| ---------------------------------------- | ----------------------------------- | ------------------------------------- |
| `Property 'xyz' does not exist on type`  | You accessed a property not defined | Check and define the property in type |
| `Type 'X' is not assignable to type 'Y'` | Passed a wrong data type            | Pass the correct data type            |
| `Expected 1 arguments, but got 0.`       | Forgot to pass a required prop      | Provide all required props            |

---

## ✅ Summary Table

| Error               | Cause                  | Fix                           |
| ------------------- | ---------------------- | ----------------------------- |
| Multiple JSX roots  | Multiple elements      | Wrap with `<div>` or `<> </>` |
| Missing props       | Prop not provided      | Pass all required props       |
| Returning an object | Invalid return value   | Return JSX only               |
| Wrong casing        | Case sensitivity       | Use PascalCase components     |
| Type errors         | Type mismatch in props | Pass the correct data type    |

---
