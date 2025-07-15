
# 🚀 Component Helper Functions

> ✅ **Reminder:** We're still writing everything inside **App.tsx** for ease of learning.

---

## 🎯 **What Are Helper Functions in React Components?**

Sometimes, inside a component, you need to:

* **Format data** (e.g., convert a number to currency).
* **Perform small calculations.**
* **Generate conditional values (e.g., status labels like "Adult" or "Minor").**

Instead of doing this **directly inside the `return` block**, it's cleaner and more readable to:

> ✅ **Write a separate helper function inside the component.**

This keeps the UI code neat and allows logic to stay organized.

---

## 🟦 **Example Scenario: ProductCard Component**

We want to build a **ProductCard** component that:

* Receives via props:

  * `productName: string`
  * `price: number`
  * `inStock: boolean`
* Displays:

  * Product name
  * Price formatted like **`$99.99`**
  * Availability status:

    * **"Available"** if `inStock` is true
    * **"Out of Stock"** if false

---

## ✅ **Step 1: Define the Props Type**

```tsx
type ProductCardProps = {
  productName: string;
  price: number;
  inStock: boolean;
};
```

---

## ✅ **Step 2: Create the Component with Helper Functions**

```tsx
function ProductCard(props: ProductCardProps) {
  // Helper function to format the price
  function formatPrice(price: number): string {
    return `$${price.toFixed(2)}`;
  }

  // Helper function to get stock status
  function getStockStatus(inStock: boolean): string {
    return inStock ? "Available" : "Out of Stock";
  }

  return (
    <div style={{ border: "1px solid #ddd", padding: "10px", marginBottom: "10px" }}>
      <h2>{props.productName}</h2>
      <p>Price: {formatPrice(props.price)}</p>
      <p>Status: {getStockStatus(props.inStock)}</p>
    </div>
  );
}
```

> ✅ We use **`formatPrice`** to ensure price always shows **2 decimal places with a dollar sign**.

> ✅ We use **`getStockStatus`** to convert a **boolean** into a human-readable label.

---

## ✅ **Step 3: Use ProductCard in App.tsx**

```tsx
function App() {
  return (
    <div>
      <h1>Product List</h1>

      <ProductCard productName="Wireless Mouse" price={25.99} inStock={true} />
      <ProductCard productName="Mechanical Keyboard" price={89.49} inStock={false} />
    </div>
  );
}

export default App;
```

---

## ✅ **Full Example of App.tsx**

```tsx
type ProductCardProps = {
  productName: string;
  price: number;
  inStock: boolean;
};

function ProductCard(props: ProductCardProps) {
  function formatPrice(price: number): string {
    return `$${price.toFixed(2)}`;
  }

  function getStockStatus(inStock: boolean): string {
    return inStock ? "Available" : "Out of Stock";
  }

  return (
    <div style={{ border: "1px solid #ddd", padding: "10px", marginBottom: "10px" }}>
      <h2>{props.productName}</h2>
      <p>Price: {formatPrice(props.price)}</p>
      <p>Status: {getStockStatus(props.inStock)}</p>
    </div>
  );
}

function App() {
  return (
    <div>
      <h1>Product List</h1>

      <ProductCard productName="Wireless Mouse" price={25.99} inStock={true} />
      <ProductCard productName="Mechanical Keyboard" price={89.49} inStock={false} />
    </div>
  );
}

export default App;
```

---

## 🧠 **Summary of What We Learned**

| Concept              | Description                                                               |
| -------------------- | ------------------------------------------------------------------------- |
| **Helper Functions** | Small internal functions to handle logic or formatting inside a component |
| **Formatting**       | Transform raw data (like price) into a user-friendly format               |
| **Boolean Handling** | Convert `true`/`false` into readable text                                 |

---

