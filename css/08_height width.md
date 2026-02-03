# CSS Width, Height & Box Model Properties

These properties control the **size**, **limits**, and **behavior** of HTML elements.

---

## 1. `width`

- Sets the **horizontal size** of an element.
- Works on `block` and `inline-block` elements.
- Default value: `auto`

### Example:
```css
div {
  width: 300px;
  background-color: lightblue;
}
````

---

## 2. `min-width`

* Sets the **minimum width** an element can shrink to.
* Useful for **responsive design**.
* The element will not go smaller than this value.

### Example:

```css
div {
  min-width: 200px;
  background-color: lightgreen;
}
```

---

## 3. `max-width`

* Sets the **maximum width** an element can grow to.
* Helps prevent layouts from stretching too much on large screens.

### Example:

```css
div {
  max-width: 500px;
  background-color: lightcoral;
}
```

---

## 4. `height`

* Sets the **vertical size** of an element.
* Works on `block` and `inline-block`.

### Example:

```css
div {
  height: 150px;
  background-color: lightyellow;
}
```

---

## 5. `min-height`

* Defines the **minimum height** of an element.
* The height will grow if content is larger.

### Example:

```css
div {
  min-height: 100px;
  background-color: lavender;
}
```

---

## 6. `max-height`

* Defines the **maximum height** of an element.
* Extra content may overflow.

### Example:

```css
div {
  max-height: 200px;
  background-color: peachpuff;
}
```

---

## 7. `box-sizing`

Controls how **width and height are calculated**.

### 7.1 `content-box` (default)

* Width & height apply only to **content**
* Padding and border are added outside

```css
div {
  box-sizing: content-box;
}
```

### 7.2 `border-box`

* Width & height include **padding + border**
* Makes layouts easier to manage

```css
div {
  box-sizing: border-box;
}
```

✅ Recommended for most layouts:

```css
* {
  box-sizing: border-box;
}
```

---

## 8. `overflow: hidden`

* Hides content that **overflows** the element’s box.
* Extra content is clipped and not visible.

### Example:

```css
div {
  width: 200px;
  height: 100px;
  overflow: hidden;
  background-color: lightgray;
}
```

---

## Summary Table

| Property          | Purpose                   |
| ----------------- | ------------------------- |
| `width`           | Sets element width        |
| `min-width`       | Minimum allowed width     |
| `max-width`       | Maximum allowed width     |
| `height`          | Sets element height       |
| `min-height`      | Minimum allowed height    |
| `max-height`      | Maximum allowed height    |
| `box-sizing`      | Controls size calculation |
| `overflow:hidden` | Hides overflowing content |



