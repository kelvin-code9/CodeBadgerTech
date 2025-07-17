
# 🔹 Interfaces for Props in React with TypeScript

## For this section make sure your code are placed in `App.tsx` from the first react app we created

Before we talk about *interfaces*, we need to understand something very important in React: **props**.

---

## 🧠 What Are Props?

**Props** (short for “properties”) are how you pass **data** from a **parent component** to a **child component** in React.

Think of props like arguments to a function — they help make components reusable.

### 🔍 Example (Without TypeScript Yet)

```jsx
function Greet(props) {
  return <h1>Hello, {props.name}!</h1>;
}
```

If you use this component like this:

```jsx
<Greet name="Favour" />
```

It will output:

```
Hello, Favour!
```

Here, `name="Favour"` is a **prop** being passed to the `Greet` component.

---

## 📦 Why Use Props?

* To customize a component’s content
* To make components reusable
* To keep code modular and clean

🧠 You can pass any kind of data: strings, numbers, booleans, even functions or JSX elements.

---

## 🟦 Typing Props in TypeScript with `interface`

Now that you understand what props are, let’s use **TypeScript interfaces** to describe what kind of data those props must have.

### ✅ Step-by-Step Example

```tsx

interface GreetProps {
  name: string;
  age: number;
}

function Greet({ name, age }: GreetProps) {
  return (
    <div>
      <h1>Hello, {name}!</h1>
      <p>You are {age} years old.</p>
    </div>
  );
}

function App() {
  return <Greet name="Favour" age={25} />;
}

export default App;

```

---

## 🔍 What's Going On?

| Part                   | Explanation                                                                                            |
| ---------------------- | ------------------------------------------------------------------------------------------------------ |
| `interface GreetProps` | Declares the expected shape of the props object. It must have a `name` (string) and an `age` (number). |
| `props: GreetProps`    | Tells TypeScript that `props` must match the `GreetProps`                                                          |

---

## 🟨 Destructuring Props (Cleaner Syntax)

You’ll often see this style in modern React code:

```tsx
function Greet({ name, age }: GreetProps) {
  return (
    <div>
      <h1>Hello, {name}!</h1>
      <p>Age: {age}</p>
    </div>
  );
}

```

This is called **destructuring**. It’s just a cleaner way to pull `name` and `age` directly from the `props` object.

---

## 🟢 Why Use an Interface Instead of Inline Types?

You *could* write the types like this:

```tsx
function Greet({ name, age }: { name: string; age: number }) {
  return <p>Hello, {name} — Age {age}</p>;
}
```

But as your components grow, it becomes **harder to read and reuse**. Using an `interface` keeps your code clean and organized — especially when you have multiple props.

---

## ⚠️ Type Safety in Action

If you make a mistake, TypeScript will catch it.

```tsx
<Greet name="Favour" age="twenty" /> // ❌ Error: age should be a number

<Greet name="Favour" />              // ❌ Error: age is missing
```

This protects your app from subtle bugs like using the wrong data type or forgetting to pass something important.

---



---

## 🧠 Summary

| Concept       | Example                                 | Purpose                          |
| ------------- | --------------------------------------- | -------------------------------- |
| Props         | `<Greet name="Favour" age={25} />`      | Pass data to components          |
| Interface     | `interface GreetProps { name: string }` | Define prop structure            |
| Props typing  | `props: GreetProps`                     | Type-safe props inside component |
| Destructuring | `({ name, age }: GreetProps)`           | Cleaner syntax                   |
| Return type   | `(): JSX.Element`                       | Ensures JSX is returned          |

---
