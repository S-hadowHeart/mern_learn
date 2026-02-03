# CSS Transition & Tooltips

CSS transitions allow changes in CSS properties to happen **smoothly over time** instead of instantly.

Tooltips are small text boxes that appear when the user **hovers** over an element.

---

## 1. CSS Transition

A transition defines **how a property changes** from one value to another.

### Basic Syntax:
```css
transition: property duration timing-function delay;
````

---

## 2. Transition Properties

### 2.1 `transition-property`

Specifies which CSS property to animate.

```css
div {
  transition-property: background-color, transform;
}
```

---

### 2.2 `transition-duration`

Defines how long the transition takes.

```css
div {
  transition-duration: 0.5s;
}
```

---

### 2.3 `transition-timing-function`

Controls the **speed curve** of the transition.

#### Common Timing Functions:

* `ease` (default)
* `ease-in`
* `ease-out`
* `ease-in-out`
* `linear`

```css
div {
  transition-timing-function: ease-in-out;
}
```

---

### 2.4 `transition-delay`

Adds a delay **before** the transition starts.

```css
div {
  transition-delay: 0.3s;
}
```

---

### 2.5 Shorthand Transition

```css
div {
  transition: all 0.4s ease-in-out 0.2s;
}
```

---

## 3. Transition Example (Hover Effect)

```css
.box {
  width: 150px;
  height: 150px;
  background-color: steelblue;
  transition: background-color 0.5s ease, transform 0.5s ease;
}

.box:hover {
  background-color: tomato;
  transform: scale(1.1);
}
```

---

## 4. Timing Function Explanation

| Timing Function | Behavior           |
| --------------- | ------------------ |
| `ease`          | Slow → Fast → Slow |
| `ease-in`       | Slow start         |
| `ease-out`      | Slow end           |
| `ease-in-out`   | Slow start and end |
| `linear`        | Constant speed     |

---

## 5. CSS Tooltips

A tooltip displays **extra information** when hovering over an element.

---

## 6. Simple Tooltip Example

### HTML:

```html
<div class="tooltip">
  Hover me
  <span class="tooltip-text">This is a tooltip</span>
</div>
```

### CSS:

```css
.tooltip {
  position: relative;
  display: inline-block;
}

.tooltip-text {
  visibility: hidden;
  width: 120px;
  background-color: black;
  color: white;
  text-align: center;
  padding: 5px;
  border-radius: 4px;

  position: absolute;
  bottom: 125%;
  left: 50%;
  transform: translateX(-50%);

  transition: opacity 0.3s ease;
  opacity: 0;
}

.tooltip:hover .tooltip-text {
  visibility: visible;
  opacity: 1;
}
```

---

## 7. Tooltip with Transition

* Tooltip appears **smoothly**
* Uses `opacity` and `transition`

```css
.tooltip-text {
  transition: opacity 0.3s ease-in-out;
}
```

---

