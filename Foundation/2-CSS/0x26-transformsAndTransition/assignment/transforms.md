### Only take this when you are done with the whole content in this folder.

### 1. 🔄 **Interactive Card Flip**

**Goal:** Create a card that flips 180° on hover using `rotateY` (we'll still use `rotate` for 2D illusion) and `scale()` for visual emphasis.

**What You’ll Practice:**

- `rotate()`, `scale()`, `transition`, and layering (`z-index`, `backface-visibility`).

**Twist:** Add a hover zoom effect that subtly enlarges the card when hovered.

### OUTPUT
<video controls src="./asset/11-09-29.mp4" title="card Flip"></video>


### 2. 🎯 **Animated Target Lock-In UI**

**Goal:** Create a "target" UI where rings skew and scale slightly on hover, giving a responsive ripple effect.

**What You’ll Practice:**

- `scale()`, `skew()`, `translate()`, `transition-delay`.

**Twist:** Use multiple `div`s nested in a circular layout and animate them in **sequence** on hover.

### Expected Output
<video controls src="./asset/11-15-39.mp4" title="Title"></video>

---

## 3. 🧊 **3D Hover Cube Reveal**  
> ⚠️ **Heads-up:** This one’s **tricky**! 😮‍💨 It requires combining everything you’ve learned so far — from 3D transforms to perspective, layering, and hover logic. Don’t rush this — take your time, read the guidelines carefully, and experiment! Its more of something for you to study rather than an assingment because i have already done the work for you. "You are welcome. haha"

--- 
### 🎥 OUTPUT  
<video controls src="./asset/11-25-36.mp4" title="Title"></video>

---

### ✅ **Goal:**  
Create a **3D cube** using **only HTML & CSS** that **rotates on hover** to reveal different sides.

---

### 🧠 **What You’ll Practice:**

- `rotateX()` & `rotateY()`  
- `transform-style: preserve-3d`  
- `perspective`  
- `backface-visibility`  
- Positioning in 3D space

---

### 🌀 **Twist:**  
Make the cube rotate both **vertically and horizontally** depending on the direction the mouse comes from (optional advanced bonus!). Add **content** on each face of the cube to showcase the 3D layering.

---

### 🛠️ **Step-by-Step Guidelines:**

#### 1. 🧱 Create the Structure

- Parent container: `.scene`  
- Inside `.scene`, place `.cube`  
- Inside `.cube`, create 6 divs for the faces:  
```<div class="face front">😎</div>
      <div class="face back">🚀</div>
      <div class="face left">💡</div>
      <div class="face right">🔥</div>
      <div class="face top">🧠</div>
      <div class="face bottom">🎯</div>
```

#### 2. 📐 Set Up the Perspective

```css
.scene {
  width: 200px;
  height: 200px;
  perspective: 1000px;
}
```

- This gives us 3D depth. Apply it to the **scene**, not the cube!

#### 3. 🎲 Cube Basics

```css
.cube {
  width: 100%;
  height: 100%;
  position: relative;
  transform-style: preserve-3d;
  transition: transform 1s ease;
}
```

- `preserve-3d` keeps faces in 3D space.
- `transition` makes the cube rotate smoothly.

#### 4. 🔲 Cube Faces (all 6 sides)

```css
.face {
  position: absolute;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  font-weight: bold;
  backface-visibility: hidden;
}

/* Positioning each face */
.front  { transform: translateZ(100px); }
.back   { transform: rotateY(180deg) translateZ(100px); }
.right  { transform: rotateY(90deg) translateZ(100px); }
.left   { transform: rotateY(-90deg) translateZ(100px); }
.top    { transform: rotateX(90deg) translateZ(100px); }
.bottom { transform: rotateX(-90deg) translateZ(100px); }
```

- Each face is pushed outwards to form a box.

#### 5. 🖱️ Add Hover Interaction

```css
.scene:hover .cube {
  transform: rotateX(-20deg) rotateY(20deg);
}
```

- This rotates the cube when the user hovers over it.
- Want to get fancy? Use `mousemove` with JavaScript to make the rotation follow the mouse (advanced).

---

### 🧪 Sample HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>3D Hover Cube</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="scene">
    <div class="cube">
      <div class="face front">😎</div>
      <div class="face back">🚀</div>
      <div class="face left">💡</div>
      <div class="face right">🔥</div>
      <div class="face top">🧠</div>
      <div class="face bottom">🎯</div>
    </div>
  </div>
</body>
</html>
```

---

### 📁 Sample CSS (`cube.css`)

```css
body {
  margin: 0;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #111;
  perspective: 800px;
}

.scene {
  width: 200px;
  height: 200px;
  perspective: 1000px;
}

.cube {
  width: 100%;
  height: 100%;
  position: relative;
  transform-style: preserve-3d;
  transition: transform 1s ease;
}

.scene:hover .cube {
  transform: rotateX(-20deg) rotateY(40deg);
}

.face {
  position: absolute;
  width: 200px;
  height: 200px;
  background: #222;
  color: white;
  font-size: 3rem;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 2px solid #555;
  backface-visibility: hidden;
}

/* Faces placement */
.front  { transform: translateZ(100px); }
.back   { transform: rotateY(180deg) translateZ(100px); }
.left   { transform: rotateY(-90deg) translateZ(100px); }
.right  { transform: rotateY(90deg) translateZ(100px); }
.top    { transform: rotateX(90deg) translateZ(100px); }
.bottom { transform: rotateX(-90deg) translateZ(100px); }

```

---