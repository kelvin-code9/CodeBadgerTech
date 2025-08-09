# ⚛️ Global State with Context API in React

> ✅ Everything is done in `App.tsx` (and a few support files) for clarity. Once you get the pattern, you can move logic into dedicated files (like `contexts/ThemeContext.tsx`).

---

## 🎯 What Is Context API?

React's Context API lets you **share state across many components** — without passing props down manually at every level.

### 🔄 Why?

> To avoid “prop drilling” — passing the same data through many nested components unnecessarily.

---

## 📦 When Should You Use Context?

✅ Use context for **global app state** like:

* Theme (light/dark)
* Authentication info (user, token)
* Language/locale
* Shopping cart
* Modal state

❌ Don’t use it for **everything**. Stick with props/state for local component-specific data.

---

## ✅ Step 1: Creating a Context

```tsx
// ThemeContext.tsx
import { createContext } from 'react';

export type Theme = 'light' | 'dark';

type ThemeContextType = {
  theme: Theme;
  toggleTheme: () => void;
};

export const ThemeContext = createContext<ThemeContextType | null>(null);
```

### 💡 Explanation:

* `createContext` makes a new context object.
* We define a type `ThemeContextType` for clarity and TypeScript safety.
* The initial value is `null` — we’ll check for this later with `useContext`.

---

## ✅ Step 2: Creating a Context Provider

```tsx
// ThemeProvider.tsx
import { useState } from 'react';
import { ThemeContext, Theme } from './ThemeContext';

type Props = {
  children: React.ReactNode;
};

export function ThemeProvider({ children }: Props) {
  const [theme, setTheme] = useState<Theme>('light');

  const toggleTheme = () => {
    setTheme(prev => (prev === 'light' ? 'dark' : 'light'));
  };

  return (
    <ThemeContext.Provider value={{ theme, toggleTheme }}>
      {children}
    </ThemeContext.Provider>
  );
}
```

### 🧠 Real Explanation:

* This component **wraps your app** and provides the global value.
* Any child component can access this data using `useContext`.
* You only create one `<ThemeProvider>`, then wrap your app with it.

---

## ✅ Step 3: Using `useContext` in Components

```tsx
// ThemeButton.tsx
import { useContext } from 'react';
import { ThemeContext } from './ThemeContext';

export function ThemeButton() {
  const context = useContext(ThemeContext);

  if (!context) throw new Error('ThemeButton must be used within ThemeProvider');

  const { theme, toggleTheme } = context;

  return (
    <button onClick={toggleTheme}>
      Current Theme: {theme.toUpperCase()}
    </button>
  );
}
```

### 🧠 Real Explanation

* `useContext(ThemeContext)` pulls the value from the nearest `<ThemeProvider>`.
* We check for `null` because we initialized the context as `null`.
* `toggleTheme` flips between light and dark.

---

## ✅ Step 4: Putting It All Together

```tsx
// App.tsx
import { ThemeProvider } from './ThemeProvider';
import { ThemeButton } from './ThemeButton';

function App() {
  return (
    <ThemeProvider>
      <div style={{ padding: 40 }}>
        <h1>Context Demo</h1>
        <ThemeButton />
      </div>
    </ThemeProvider>
  );
}

export default App;
```

### ✅ Result

Your button now **shares global state** via context. No need to pass `theme` or `toggleTheme` through props.

---

## ✅ Bonus: Consuming Context in Multiple Components

```tsx
// ThemeStatus.tsx
import { useContext } from 'react';
import { ThemeContext } from './ThemeContext';

export function ThemeStatus() {
  const context = useContext(ThemeContext);
  if (!context) return null;

  return <p>✅ The current theme is <strong>{context.theme}</strong></p>;
}
```

Then add it to `App.tsx`:

```tsx
<ThemeProvider>
  <ThemeStatus />
  <ThemeButton />
</ThemeProvider>
```

> 🔁 Both components access the same state — and re-render together when it changes.

---

## 🔡 Typing Context Values (TypeScript Best Practices)

| What                 | How it’s done                                 |         |
| -------------------- | --------------------------------------------- | ------- |
| Define shape         | `type ThemeContextType = { theme: ..., ... }` |         |
| Use generic argument | \`createContext\<ThemeContextType             | null>\` |
| Validate on access   | Check for `null` when using `useContext()`    |         |

---

## 🧼 Summary Table

| Concept            | Description                                                     |
| ------------------ | --------------------------------------------------------------- |
| `createContext`    | Creates a context object for shared state                       |
| `Context.Provider` | The wrapper that shares data with all child components          |
| `useContext`       | Hook that lets components **read** the nearest provider’s value |
| Typing with TS     | Ensure consistent usage across app — especially for dev teams   |
| Common use cases   | Theme, auth, locale, user, settings, cart, modals               |

---

## ⚠️ Common Pitfalls

| Problem                   | What Happens                                                            |
| ------------------------- | ----------------------------------------------------------------------- |
| ❌ No Provider             | `useContext` will return `null`, and accessing properties causes crash  |
| ❌ Re-render everything    | Storing large data in context can trigger unnecessary re-renders        |
| ❌ Overusing Context       | Not everything should be global — prefer props for local component data |
| ❌ Complex nested contexts | If you use multiple contexts, organize them clearly                     |

---

## ✅ Key Takeaways

* **Context = global state** for your React app.
* Avoid prop-drilling by lifting shared state to the top.
* Use `useContext()` in deeply nested components to **read** values.
* Type your context carefully in TypeScript for better dev experience.
* Wrap your app with a **provider** component.

---

## 📦 Want a Real-World Example?

Replace `ThemeContext` with:

* `AuthContext` (user data, login/logout)
* `CartContext` (cart items, total price, add/remove functions)
* `LangContext` (selected language + translator functions)

Each one follows **the exact same pattern**.