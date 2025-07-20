

# 🚀 Page Re-rendering in React (Theory Only)**

> ✅ **Reminder:** Everything remains inside **App.tsx** for now.
> We will write full reactivity examples after learning **state (`useState`)** and **effects (`useEffect`)**.

---

## 🎯 **What is Page Re-rendering in React?**

In plain terms:

> **Re-rendering** is when **React updates the UI automatically** because:

1. The **props passed to a component change**, OR
2. The **internal state of a component changes** (stateful components — coming next!).

You don’t need to manually refresh or reload. React **detects the change** and **refreshes only the affected parts of the UI**.

---

## 🟦 **Example: Re-rendering via Props**

Let’s build a simple component that receives props, and whenever the **prop value changes**, React will automatically **re-render it with the new data**.

### ✅ Step 1: Create a `Greeting` Component

```tsx
type GreetingProps = {
  name: string;
};

function Greeting(props: GreetingProps) {
  return <h2>Hello, {props.name}!</h2>;
}
```

### ✅ Step 2: Using the Component in App

```tsx
function App() {
  return (
    <div>
      <h1>Greetings</h1>

      <Greeting name="Favour" />
      <Greeting name="Amaka" />
    </div>
  );
}

export default App;
```

---

## 🟨 **But When Does React Re-render?**

In the example above, **React re-renders the `Greeting` component** if the **`name` prop changes**.

> ✅ **However:**
> Because our code here is static (props never change), there is **no re-render happening yet**.

To **trigger re-renders dynamically**, we need:

* **State (`useState`)** to hold dynamic data
* And later, **`useEffect`** to trigger updates like time ticks or API calls.

We will introduce these next.

---

## ✅ **Key Rule of React Re-rendering**

| Trigger      | Effect                          |
| ------------ | ------------------------------- |
| Props change | Child component re-renders      |
| State change | The component re-renders itself |

---

## ✅ **Summary**

* **Re-rendering is automatic** when props or state change.
* Right now, our props are **static**, so no re-render occurs after the first display.
* Once we learn **state**, we’ll build components that:

  * Change over time
  * Update based on user interactions
  * And thus **trigger React to re-render automatically**.

---
