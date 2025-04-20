---

# 🧱 CSS 3D Transforms

---

## ✨ What Are CSS 3D Transforms?

**CSS 3D transforms** allow you to manipulate elements in **three-dimensional space**, affecting the **X**, **Y**, and **Z** axes. They give your designs **depth**, **perspective**, and a more dynamic feel.

---

## 🧠 Syntax

```css
selector {
  transform: function3d(value);
}
```

You’ll use functions like `rotateX()`, `translateZ()`, and `scale3d()` to make elements pop off the page.

---

## 🔧 3D Transform Functions Overview

| Function        | What It Does                               |
|-----------------|---------------------------------------------|
| `rotateX()`     | Rotates around the X-axis                  |
| `rotateY()`     | Rotates around the Y-axis                  |
| `rotateZ()`     | Rotates around the Z-axis                  |
| `translate3d()` | Moves element in 3D space                  |
| `translateZ()`  | Moves element along Z-axis only           |
| `scale3d()`     | Scales element in 3D                       |
| `scaleZ()`      | Scales along the Z-axis                   |
| `rotate3d()`    | Rotates around a custom 3D axis           |
| `matrix3d()`    | Combines multiple 3D transforms            |
| `perspective()` | Adds depth to 3D space                     |

---

## 🔄 1. `rotateX(deg)`

Rotates the element around the **horizontal X-axis**.

### 📄 HTML: `rotateX.html`

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="rotateX.css">
</head>
<body>
  <div class="box"></div>
</body>
</html>
```

### 🎨 CSS: `rotateX.css`

```css
.box {
  width: 100px;
  height: 100px;
  background-color: lightcoral;
  transform: rotateX(150deg);
  transform-style: preserve-3d;
  transition: transform 1s;
}
.box:hover {
  transform: rotateX(0deg);
}
```

### 👀 Output

Hover to rotate the element smoothly back to 0°.  
*Transitions make the effect visible!*

---

## 🔄 2. `rotateY(deg)`

Rotates the element around the **vertical Y-axis**.

```css
.box {
  transform: rotateY(150deg);
  transition: transform 1s;
  width: 100px;
  height: 100px;
  width: 100px;
  height: 100px;
  background-color: lightcoral;
}
.box:hover {
  transform: rotateY(0deg);
}
```

---

## 🔄 3. `rotateZ(deg)`

Rotates the element around the **Z-axis** (like 2D rotate, but in 3D space).

```css
.box {
  transform: rotateZ(90deg);
  transition: transform 1s;
  width: 100px;
  height: 100px;
  width: 100px;
  height: 100px;
  background-color: lightcoral;
}
.box:hover {
  transform: rotateZ(0deg);
}
```

---

## 🚀 4. `translate3d(x, y, z)`

Moves an element in **3D space**. The Z value brings the element closer or farther from the viewer.

```css
.box {
  transform: translate3d(50px, 50px, 100px);
  transition: transform 1s;
  width: 100px;
  height: 100px;
  width: 100px;
  height: 100px;
  background-color: lightcoral;
}
.box:hover {
  transform: translate3d(0, 0, 0);
}
```

---

## 🔍 5. `scale3d(x, y, z)`

Scales the element in **3D** on all three axes.

```css
.box {
  transform: scale3d(2, 1.5, 1);
  transition: transform 1s;
  width: 100px;
  height: 100px;
  width: 100px;
  height: 100px;
  background-color: lightcoral;
}
.box:hover {
  transform: scale3d(1, 1, 1);
}
```

---

## 🧭 6. `rotate3d(x, y, z, angle)`

Rotates the element around a **custom 3D axis**.

```css
.box {
  transform: rotate3d(1, 1, 0, 45deg);
  transition: transform 1s;
  width: 100px;
  height: 100px;
  width: 100px;
  height: 100px;
  background-color: lightcoral;
}
.box:hover {
  transform: rotate3d(1, 1, 0, 0deg);
}
```

---


---

## 🛠️ Supporting Properties

| Property              | Description                                               |
|-----------------------|-----------------------------------------------------------|
| `transform-origin`    | Sets the pivot point for the transform                    |
| `transform-style`     | Enables 3D context for children (`preserve-3d`)           |
| `perspective`         | Adds 3D perspective to the parent container               |
| `perspective-origin`  | Sets where the "camera" looks from                        |
| `backface-visibility` | Hides the backside of the element during rotation         |

---

## ✅ Recap: What You Learned

| Function        | What It Does                      |
|-----------------|-----------------------------------|
| `rotateX()`     | Rotate around X-axis              |
| `rotateY()`     | Rotate around Y-axis              |
| `rotateZ()`     | Rotate around Z-axis              |
| `translate3d()` | Move in 3D                        |
| `scale3d()`     | Resize in 3D                      |
| `rotate3d()`    | Custom rotation in 3D             |
| `matrix3d()`    | Combine multiple 3D transforms    |

---

## 🪄 Pro Tip

Use **`transition: transform 1s`** for every example to actually see the change happen. Without it, 3D transforms snap instantly, making them hard to observe.

---

## 🚀 Coming Up Next