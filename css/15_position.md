# CSS Position Property

The `position` property in CSS controls **how an element is positioned** in the document.

It works together with:
- `top`
- `bottom`
- `left`
- `right`

---

## Position Offset Properties

These properties are used to **move positioned elements**.

```css
top: 20px;
bottom: 10px;
left: 15px;
right: 25px;
````

⚠️ Offset properties work **only when position is NOT `static`**.

---

## Types of CSS Position

1. `static`
2. `relative`
3. `absolute`
4. `fixed`
5. `sticky`

---
<img width="1207" height="703" alt="image" src="https://github.com/user-attachments/assets/37e545cc-d526-42c5-90d4-9c9601a34617" />


## 1. `position: static`

* **Default** position for all elements
* Follows the **normal document flow**
* `top`, `left`, `right`, `bottom` **do not work**

### Example:

```css
.box {
  position: static;
  top: 20px; /* ignored */
}
```

---

## 2. `position: relative`

* Element remains in **normal flow**
* Can be moved using offset properties
* Space occupied **does not change**

### Example:

```css
.box {
  position: relative;
  top: 20px;
  left: 30px;
}
```

---

## 3. `position: absolute`

* Element is **removed from normal flow**
* Positioned relative to the **nearest positioned ancestor**
* If no positioned ancestor exists → positioned relative to `body`

### Example:

```css
.parent {
  position: relative;
}

.child {
  position: absolute;
  top: 10px;
  right: 10px;
}
```

```html
<div class="parent">
  <div class="child"></div>
</div>
```

---

## 4. `position: fixed`

* Element is positioned relative to the **viewport**
* Does **not move when scrolling**
* Removed from normal flow

### Example:

```css
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
}
```

---

## 5. `position: sticky`

* Hybrid of `relative` and `fixed`
* Behaves like `relative` until a scroll point
* Then sticks like `fixed`

### Example:

```css
.header {
  position: sticky;
  top: 0;
  background-color: white;
}
```

⚠️ `sticky` requires a **scrollable container** to work.

---

## Position Comparison Table

| Position | In Normal Flow | Scroll Affected | Offset Works |
| -------- | -------------- | --------------- | ------------ |
| static   | Yes            | Yes             | ❌ No         |
| relative | Yes            | Yes             | ✅ Yes        |
| absolute | ❌ No           | Yes             | ✅ Yes        |
| fixed    | ❌ No           | ❌ No            | ✅ Yes        |
| sticky   | Yes / Fixed    | Partial         | ✅ Yes        |

---

## Key Takeaways

* `static` is default and cannot be moved
* `relative` is used as a **reference for absolute**
* `absolute` positions inside nearest positioned parent
* `fixed` stays fixed on screen
* `sticky` sticks on scroll
