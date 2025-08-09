

✅ Everything is done in a few small files for clarity. Once you get the pattern, you can move hooks into `src/hooks/*`.

# 🎯 What Are Custom Hooks?

Custom hooks are just functions that **use React hooks** (`useState`, `useEffect`, etc.) to encapsulate reusable logic. They let you share stateful logic across components **without** HOCs, render props, or duplication.

# 🔄 Why Create Custom Hooks?

* **Reuse**: Extract repeated effects/state (e.g., localStorage, media queries, fetch logic).
* **Testability**: Logic moves out of components → easier unit tests.
* **Separation of concerns**: UI components stay presentational; hooks manage data/state.
* **Composition**: Build small hooks and compose them like Lego pieces.

# 📦 When Should You Use Custom Hooks?

Use a custom hook when:

* You’ve copied the same `useEffect`/`useState` logic **twice** or more.
* You want to share logic across **unrelated** components.
* A component is too “smart” — you want to move non-UI parts out.

Don’t use a custom hook when:

* Logic is **truly local** to a single component and unlikely to repeat.
* You’re adding abstraction without a clear payoff.

---

# ✅ Step 1: Build a Simple `useLocalStorage` Hook

## Goal

Make `useLocalStorage<T>(key, initialValue)` behave like `useState`, but **persist** to `localStorage` and **hydrate** on first render.

### `useLocalStorage.ts`

```ts
import { useEffect, useRef, useState } from 'react';

type Serializer<T> = (value: T) => string;
type Deserializer<T> = (value: string) => T;

type Options<T> = {
  serializer?: Serializer<T>;
  deserializer?: Deserializer<T>;
  // For SSR or environments without window
  isServer?: boolean;
  // Optional key prefix for namespacing
  prefix?: string;
};

export function useLocalStorage<T>(
  key: string,
  initialValue: T | (() => T),
  options: Options<T> = {}
) {
  const {
    serializer = JSON.stringify,
    deserializer = JSON.parse,
    isServer = typeof window === 'undefined',
    prefix = '',
  } = options;

  const storageKey = prefix ? `${prefix}:${key}` : key;

  // Lazily compute initial state (avoid JSON.parse on every render)
  const [state, setState] = useState<T>(() => {
    if (isServer) return typeof initialValue === 'function'
      ? (initialValue as () => T)()
      : initialValue;

    try {
      const raw = window.localStorage.getItem(storageKey);
      if (raw !== null) return deserializer(raw);
    } catch {
      // ignore corrupted JSON or access errors
    }
    return typeof initialValue === 'function'
      ? (initialValue as () => T)()
      : initialValue;
  });

  // Track the current key to handle key changes safely
  const prevKeyRef = useRef(storageKey);

  // Persist to localStorage whenever state or key changes
  useEffect(() => {
    if (isServer) return;

    // If key changed, remove the old key to avoid orphans
    if (prevKeyRef.current !== storageKey) {
      try {
        window.localStorage.removeItem(prevKeyRef.current);
      } catch {}
      prevKeyRef.current = storageKey;
    }

    try {
      window.localStorage.setItem(storageKey, serializer(state));
    } catch {
      // Storage might be full or blocked; ignore but keep state in memory
    }
  }, [state, storageKey, serializer, isServer]);

  // Keep multiple tabs/windows in sync
  useEffect(() => {
    if (isServer) return;

    const onStorage = (e: StorageEvent) => {
      if (e.storageArea !== window.localStorage) return;
      if (e.key !== storageKey) return;

      try {
        if (e.newValue === null) {
          // Key was removed elsewhere → reset to initialValue
          setState(typeof initialValue === 'function'
            ? (initialValue as () => T)()
            : initialValue);
        } else {
          setState(deserializer(e.newValue));
        }
      } catch {}
    };

    window.addEventListener('storage', onStorage);
    return () => window.removeEventListener('storage', onStorage);
  }, [storageKey, deserializer, initialValue, isServer]);

  return [state, setState] as const;
}
```

### 🧠 Real Explanation

* **Hydration**: First render tries `localStorage.getItem(key)` and `JSON.parse`; if missing or invalid, falls back to `initialValue`.
* **Persistence**: On state change, we `setItem` with a safe `serializer`.
* **Multi-tab sync**: Listens to the `'storage'` event so changes in one tab update others.
* **SSR-safe**: No `window` access on the server; you can pass `isServer: true` explicitly if needed.
* **Key changes**: If the `key` prop changes at runtime, we remove the old key to avoid stale entries.

---

# ✅ Step 2: Use the Hook in a Component

### `App.tsx`

```tsx
import { useLocalStorage } from './useLocalStorage';

export default function App() {
  const [name, setName] = useLocalStorage<string>('name', '');
  const [count, setCount] = useLocalStorage<number>('count', 0, { prefix: 'demo' });

  return (
    <div style={{ padding: 24 }}>
      <h1>useLocalStorage Demo</h1>

      <label>
        Name:
        <input
          value={name}
          onChange={(e) => setName(e.target.value)}
          style={{ marginLeft: 8 }}
        />
      </label>

      <div style={{ marginTop: 16 }}>
        <button onClick={() => setCount(c => c + 1)}>Increment</button>
        <button onClick={() => setCount(0)} style={{ marginLeft: 8 }}>
          Reset
        </button>
        <p>Count: {count}</p>
      </div>
    </div>
  );
}
```

🧠 Real Explanation
This behaves like `useState`, but values persist across refreshes and survive unmounts. Open two tabs → increment in one → watch the other update (thanks to the storage event listener).

---

# 🔡 Typing Custom Hooks (TypeScript Best Practices)

**1) Use Generics for Value Type**

```ts
export function useLocalStorage<T>(key: string, initialValue: T): readonly [T, React.Dispatch<React.SetStateAction<T>>] {
  // ...
  return [state, setState] as const;
}
```

* Generic `T` lets the hook work with `string | number | object | array | boolean`, etc.

**2) Strongly-Typed Serializer/Deserializer**

```ts
type Serializer<T> = (value: T) => string;
type Deserializer<T> = (value: string) => T;

type Options<T> = {
  serializer?: Serializer<T>;
  deserializer?: Deserializer<T>;
  // ...
};
```

* Allows custom formats (e.g., compress, encrypt, or Date handling).

**3) Preserve Functional Updates**

```ts
const [state, setState] = useState<T>(() => /* lazy init */);
// setState(prev => next) still works because we return React’s setter as-is
```

**4) Return `as const`**

* Ensures tuple inference: `[value, setValue]` not `(T | Dispatch)[]`.

**5) SSR Safety**

* Surface an `isServer` flag or check `typeof window === 'undefined'` to avoid runtime errors in Node.

---

# ✅ Bonus: A Tiny `useToggle` Hook (shows the pattern)

```ts
import { useCallback, useState } from 'react';

export function useToggle(initial = false) {
  const [value, setValue] = useState<boolean>(initial);
  const on = useCallback(() => setValue(true), []);
  const off = useCallback(() => setValue(false), []);
  const toggle = useCallback(() => setValue(v => !v), []);
  return { value, on, off, toggle } as const;
}
```

Usage:

```tsx
const { value: isOpen, toggle } = useToggle();
<button onClick={toggle}>{isOpen ? 'Close' : 'Open'}</button>
```

---

# 🧼 Summary Table

| Concept              | Description                                                          |
| -------------------- | -------------------------------------------------------------------- |
| Custom hook          | A function that uses React hooks to encapsulate reusable logic       |
| When to use          | Repeated logic across components, complex effects, shared state      |
| `useLocalStorage<T>` | `useState` + persistence + multi-tab sync + SSR-safe guard           |
| Typing               | Use generics, typed (de)serializers, and `as const` return           |
| SSR                  | Avoid `window` on server; allow `isServer` override                  |
| Key niceties         | Handles key changes; swallows parse errors safely; supports prefixes |

---

# ⚠️ Common Pitfalls

| Problem                       | What Happens                                                 |
| ----------------------------- | ------------------------------------------------------------ |
| Accessing `window` during SSR | Crashes on the server (ReferenceError)                       |
| Unvalidated `JSON.parse`      | App crashes on corrupted storage; wrap in try/catch          |
| Forgetting multi-tab sync     | Values diverge across tabs; users see inconsistent state     |
| Changing storage key silently | Old entries left behind; handle key-change cleanup           |
| Over-abstraction              | A hook that’s only used once adds complexity with no benefit |

---

# ✅ Key Takeaways

* Custom hooks **package stateful logic** for reuse and clarity.
* `useLocalStorage<T>` is a perfect starter: small, practical, and easily typed.
* Make hooks **SSR-safe**, **resilient to bad data**, and **multi-tab aware** when relevant.
* Keep APIs simple: mirror React hooks (`[value, setValue]`) where it helps DX.
* Start with **one component**, extract repeating logic into a hook, and iterate.
