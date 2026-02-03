# CSS Gradient

## What is a Gradient? (Simple Answer)
A **gradient** is a smooth transition between **two or more colors** instead of using a single solid color.

Gradients are commonly used as **backgrounds** in CSS.

---

## Types of CSS Gradients

### 1. Linear Gradient
- Colors change in a **straight line**
- Direction can be set using keywords or angles

### Syntax:
```css
background: linear-gradient(direction, color1, color2);
````

### Directions:

* `to right`
* `to left`
* `to top`
* `to bottom` (**default**)

### Example:

```css
div {
  background: linear-gradient(to right, red, blue);
}
```

---

### 2. Radial Gradient

* Colors spread **from the center outward**
* Shape can be circle or ellipse

### Syntax:

```css
background: radial-gradient(color1, color2);
```

### Example:

```css
div {
  background: radial-gradient(circle, yellow, orange, red);
}
```

---

### 3. Conic Gradient

* Colors rotate **around a center point**
* Works like a **pie chart**

### Syntax:

```css
background: conic-gradient(color1, color2);
```

### Example:

```css
div {
  background: conic-gradient(red, yellow, green);
}
```

---

## Direction in Linear Gradient

```css
/* Default */
background: linear-gradient(to bottom, red, blue);

/* Other directions */
background: linear-gradient(to right, red, blue);
background: linear-gradient(to left, red, blue);
background: linear-gradient(to top, red, blue);
```

---

## Repeating Gradients

Gradients can repeat automatically.

### Repeating Linear Gradient:

```css
background: repeating-linear-gradient(
  to right,
  red 0px,
  red 50px,
  blue 50px,
  blue 100px
);
```

### Repeating Radial Gradient:

```css
background: repeating-radial-gradient(
  circle,
  red,
  yellow 20px
);
```

### Repeating Conic Gradient:

```css
background: repeating-conic-gradient(
  red 0deg,
  yellow 30deg
);
```

---

## Degree in Conic Gradient

* Conic gradients use **degrees (`deg`)** to control color rotation.
* Full circle = **360°**

### Example:

```css
div {
  background: conic-gradient(
    red 0deg,
    yellow 120deg,
    green 240deg,
    red 360deg
  );
}
```

---

## Summary

| Gradient Type | Description                      |
| ------------- | -------------------------------- |
| Linear        | Colors change in a straight line |
| Radial        | Colors spread from center        |
| Conic         | Colors rotate around center      |


