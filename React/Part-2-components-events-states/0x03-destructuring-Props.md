
# 🚀 **Destructuring Props**

> ✅ **Reminder:** We are still working directly inside **App.tsx**.
> In real projects, components should live in their **own files under a `components/` folder**, but for now:
> **All examples and usage remain in `App.tsx`.**

---

## 🎯 **What You’ll Learn**

* What is **Destructuring** in TypeScript/JavaScript.
* How to **destructure props inside React components**.
* Why destructuring makes your code **cleaner and easier to read**.

---

## 🔵 **What is Destructuring?**

In TypeScript and JavaScript, **destructuring** means **breaking an object into its parts directly**, instead of accessing each property via dot notation.

### ✅ Without Destructuring

```tsx
function Greeting(props: { name: string; }) {
  return <h2>Hello, {props.name}!</h2>;
}
```

### ✅ With Destructuring

```tsx
function Greeting({ name }: { name: string }) {
  return <h2>Hello, {name}!</h2>;
}
```

Instead of calling `props.name`, destructuring lets us extract `name` directly.

---

## 🟩 **Step-by-Step with a Typed Props Example**

### ✅ Step 1: Define the Props Type

```tsx
type UserInfoProps = {
  username: string;
  role: string;
};
```

### ✅ Step 2: Destructure Props in the Component

Instead of:

```tsx
function UserInfo(props: UserInfoProps) {
  return (
    <div>
      <h2>User: {props.username}</h2>
      <p>Role: {props.role}</p>
    </div>
  );
}
```

We destructure:

```tsx
function UserInfo({ username, role }: UserInfoProps) {
  return (
    <div>
      <h2>User: {username}</h2>
      <p>Role: {role}</p>
    </div>
  );
}
```

Now inside the function body, we can **directly use `username` and `role`**, without prefixing them with `props.`

---

## 🟦 **Full Example in App.tsx**

```tsx
type UserInfoProps = {
  username: string;
  role: string;
};

function UserInfo({ username, role }: UserInfoProps) {
  return (
    <div>
      <h2>User: {username}</h2>
      <p>Role: {role}</p>
    </div>
  );
}

function App() {
  return (
    <div>
      <h1>System Users</h1>

      <UserInfo username="Favour" role="Auditor" />
      <UserInfo username="Amaka" role="Developer" />
    </div>
  );
}

export default App;
```

---

## 🧠 **Why Destructure?**

| Benefit                  | Explanation                                                     |
| ------------------------ | --------------------------------------------------------------- |
| **Cleaner Code**         | No repetitive `props.` prefix.                                  |
| **Improved Readability** | Easier to see what data the component expects.                  |
| **Enforced Typing**      | TypeScript ensures destructured variables match the prop types. |


---