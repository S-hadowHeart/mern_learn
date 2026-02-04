# CSS Overflow & Z-Index

---

## 1. CSS `overflow`

The `overflow` property controls **what happens when content is larger than its container**.

It is commonly used to:
- Prevent content overlap
- Add scrolling
- Hide extra content

---

## Overflow Values

### 1. `overflow: hidden`
- Hides overflowing content
- No scrollbars shown
- Extra content is clipped

```css
.box {
  width: 200px;
  height: 100px;
  overflow: hidden;
}
````

---

### 2. `overflow: scroll`

* Always shows scrollbars
* Scrollbars appear even if content fits

```css
.box {
  width: 200px;
  height: 100px;
  overflow: scroll;
}
```

---

### 3. `overflow: auto`

* Shows scrollbars **only when needed**
* Automatically decides based on content size

```css
.box {
  width: 200px;
  height: 100px;
  overflow: auto;
}
```

---

## Auto vs Scroll (Important Difference)

| Feature           | `auto`           | `scroll`       |
| ----------------- | ---------------- | -------------- |
| Scrollbar visible | Only when needed | Always visible |
| Cleaner UI        | ✅ Yes            | ❌ No           |
| Recommended       | ✅ Yes            | ⚠️ Rare cases  |

---

## 2. CSS `z-index`

The `z-index` property controls the **vertical stacking order** of elements.

* Higher `z-index` → element appears **on top**
* Works only on **positioned elements**
  (`relative`, `absolute`, `fixed`, `sticky`)

---

### Example:

```css
.box1 {
  position: absolute;
  z-index: 1;
  background-color: red;
}

.box2 {
  position: absolute;
  z-index: 2;
  background-color: blue;
}
```

---

## Important Notes About `z-index`

* Default value is `auto`
* Negative values are allowed
* `z-index` does not work on `position: static`

---

## Key Takeaways

* `overflow` controls extra content behavior
* `hidden` hides content
* `scroll` always shows scrollbar
* `auto` shows scrollbar only when required
* `z-index` controls stacking order
