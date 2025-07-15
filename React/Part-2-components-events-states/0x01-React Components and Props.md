
# 🚀 React Components and Props

> ✅ **Note:** In a real-world React project, components are usually created in their **own separate files inside a `components` folder**.
> However, for the purpose of this lesson and for ease of learning, we’ll be writing **everything inside `App.tsx`**.

---

## 🎯 **Lesson Objectives**

By the end of this lesson, you’ll understand:

* ✅ What are **React Components**.
* ✅ What are **Props** and why we use them.
* ✅ How to **type props in TypeScript**.
* ✅ The concept of **reusing components** with different data.

---

## 🔵 **1. What is a React Component?**

A **Component** is a **function** that returns **TSX** — which is like HTML inside TypeScript.

> ✅ Components are the **building blocks** of any React application. They help us **break the UI into smaller, reusable pieces.**

### Example

```tsx
function Welcome() {
  return <h2>Welcome to React!</h2>;
}
```

We can now **use this custom component** like:

```tsx
<Welcome />
```

Which outputs:

> Welcome to React!

---

## 🟩 **2. What are Props?**

**Props** (short for **Properties**) are **inputs** we can pass to a component.
They allow us to **customize components dynamically**, just like passing **parameters to a function**.

For example, instead of showing the same message to everyone, what if we want to greet users by name?

We’ll need props to make this possible.

---

## 🟦 **3. Typing Props in TypeScript**

In TypeScript, we create a **type definition** to describe the structure of props.

### ✅ Example: Greeting Component

### Step 1: Define the Props Type

```tsx
type GreetingProps = {
  name: string;
};
```

> This says that the `Greeting` component should always receive a **`name` prop of type `string`**.

---

### Step 2: Create the Component Using Props

We create a component that **accepts `props`** and uses `props.name` to display a custom message.

```tsx
function Greeting(props: GreetingProps) {
  return <h2>Hello, {props.name}!</h2>;
}
```

---

### Step 3: Using the Component in App.tsx

```tsx
function App() {
  return (
    <div>
      <h1>Greetings Section</h1>

      <Greeting name="Favour" />
      <Greeting name="Amaka" />
      <Greeting name="Emeka" />
    </div>
  );
}

export default App;
```

---

## ✅ **4. Reusability of Components**

Once a component is defined, you can **reuse it multiple times** by passing in different **props values**.

Example:

```tsx
<Greeting name="Favour" />
<Greeting name="Amaka" />
<Greeting name="Emeka" />
```

> All three are using the same **`Greeting` component**, but each one displays a different name.

---

## ✅ **5. Full App.tsx Example**

```tsx
type GreetingProps = {
  name: string;
};

function Greeting(props: GreetingProps) {
  return <h2>Hello, {props.name}!</h2>;
}

function App() {
  return (
    <div>
      <h1>Greetings Section</h1>

      <Greeting name="Favour" />
      <Greeting name="Amaka" />
      <Greeting name="Emeka" />
    </div>
  );
}

export default App;
```

---

## 🧠 **Summary of Key Concepts**

| Concept               | Meaning                                                             |
| --------------------- | ------------------------------------------------------------------- |
| **Component**         | A function that returns TSX (UI code).                              |
| **Props**             | Inputs you pass to a component to customize it.                     |
| **TypeScript Typing** | Define the expected shape of props using `type` or `interface`.     |
| **Reusability**       | Once a component is written, it can be reused with different props. |


---
