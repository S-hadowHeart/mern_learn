# CSS Animation

## What is Animation?
An **animation** allows an element to **gradually change from one CSS style to another** over time.

- You can animate **multiple CSS properties**
- Animations can run **once, multiple times, or infinitely**
- To use CSS animation, you must define **keyframes**

---

## Key Concepts of CSS Animation
1. `@keyframes` rules  
2. Animation duration  
3. Animation delay  
4. Animation iteration count  
5. Animation direction  
6. Animation timing function (speed curve)  
7. Animation fill-mode  
8. Animation shorthand property  

---

## 1. `@keyframes` Rules

The `@keyframes` rule defines **how the animation changes styles over time**.

### Syntax:
```css
@keyframes animationName {
  from {
    /* starting styles */
  }
  to {
    /* ending styles */
  }
}
````

### Example:

```css
@keyframes changeColor {
  from {
    background-color: red;
  }
  to {
    background-color: blue;
  }
}
```

---

## 2. Binding Animation to an Element

To make an animation work, it must be **attached to an element** using `animation-name`.

```css
.box {
  animation-name: changeColor;
  animation-duration: 2s;
}
```

⚠️ If `animation-duration` is **not specified**, the animation will **not run** (default is `0s`).

---

## 3. Using `from`, `to`, and `%`

### Using `from` and `to`

```css
@keyframes moveBox {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(200px);
  }
}
```

### Using Percentages

```css
@keyframes multiStep {
  0% {
    background-color: red;
  }
  50% {
    background-color: yellow;
  }
  100% {
    background-color: green;
  }
}
```

---

## 4. `animation-duration`

Defines **how long** the animation takes to complete.

```css
.box {
  animation-duration: 3s;
}
```

---

## 5. `animation-delay`

Delays the **start** of the animation.

```css
.box {
  animation-delay: 1s;
}
```

---

## 6. `animation-iteration-count`

Controls **how many times** the animation runs.

```css
.box {
  animation-iteration-count: 3;
}

/* Infinite animation */
.box {
  animation-iteration-count: infinite;
}
```

---

## 7. `animation-direction`

Controls the **direction** of the animation.

### Values:

* `normal` (default)
* `reverse`
* `alternate`
* `alternate-reverse`

```css
.box {
  animation-direction: alternate;
}
```

---

## 8. Animation Timing Function (Speed Curve)

Controls the **speed curve** of the animation.

### Common values:

* `ease` (default)
* `linear`
* `ease-in`
* `ease-out`
* `ease-in-out`

```css
.box {
  animation-timing-function: ease-in-out;
}
```

---

## 9. `animation-fill-mode`

Defines the **style of the element before and after animation**.

### Values:

#### `none` (default)

Element does not retain animation styles.

```css
animation-fill-mode: none;
```

#### `forwards`

Keeps the **last keyframe style** after animation ends.

```css
animation-fill-mode: forwards;
```

#### `backwards`

Applies the **first keyframe style before animation starts**.

```css
animation-fill-mode: backwards;
```

#### `both`

Applies **both forwards and backwards** behavior.

```css
animation-fill-mode: both;
```

---

## 10. Animation Shorthand Property

All animation properties can be written in **one line**.

### Syntax:

```css
animation: name duration timing-function delay iteration-count direction fill-mode;
```

### Example:

```css
.box {
  animation: moveBox 2s ease-in-out 1s infinite alternate forwards;
}
```

---

## Complete Animation Example

```css
@keyframes slide {
  0% {
    transform: translateX(0);
    background-color: red;
  }
  100% {
    transform: translateX(200px);
    background-color: blue;
  }
}

.box {
  width: 100px;
  height: 100px;
  animation: slide 2s ease-in-out 0.5s infinite alternate both;
}
```

---

## Summary Table

| Property                    | Purpose                       |
| --------------------------- | ----------------------------- |
| `@keyframes`                | Defines animation steps       |
| `animation-name`            | Animation name                |
| `animation-duration`        | Length of animation           |
| `animation-delay`           | Start delay                   |
| `animation-iteration-count` | Number of runs                |
| `animation-direction`       | Direction of animation        |
| `animation-timing-function` | Speed curve                   |
| `animation-fill-mode`       | Styles before/after animation |
| `animation`                 | Shorthand property            |
