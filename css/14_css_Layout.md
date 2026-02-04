# Introduction to CSS Layout

CSS Layout is a **very important part of web design**.  
It allows developers to **position and size elements** on a web page so that the page is **visually appealing and user-friendly**.

In simple words, CSS layout is the process of using CSS to **control the position and size of elements** on a web page.

---

## Benefits of Using CSS Layout

1. **Better presentation and structure**
2. **Better accessibility**
3. **Flexible and responsive design**
4. **Reusability of layouts**
5. **Browser compatibility**

---

## Types of CSS Layout

1. Normal Flow  
2. Float  
3. Position  
4. Flexbox  
5. Grid  

---

## 1. Normal Flow

- Default layout behavior of HTML elements
- Elements appear **one after another**
- Block elements start on a **new line**
- Inline elements stay **in the same line**

### Example:
```html
<p>This is a paragraph</p>
<p>This is another paragraph</p>
````

---

## 2. Float Layout

The `float` property specifies **how an element is positioned within its container**.

* Mainly used to **align elements horizontally**
* Elements float to the **left or right**
* Other content wraps around the floated element

---

### Float Property Values

1. `none` (default)
2. `left`
3. `right`

---

### 2.1 `float: none`

* Default behavior
* Element stays in the **normal document flow**
* Does not float

#### Example:

```css
.box {
  width: 100px;
  height: 100px;
  background-color: black;
  float: none;
}
```

```html
<div class="box"></div>
```

---

### 2.2 `float: left`

* Element moves to the **left side** of its container
* Other elements wrap around it on the right

#### Example:

```css
.box {
  width: 100px;
  height: 100px;
  background-color: black;
  float: left;
}
```

```html
<div class="box"></div>
<p>This text wraps around the floated element.</p>
```

---

### 2.3 `float: right`

* Element moves to the **right side** of its container
* Other elements wrap around it on the left

#### Example:

```css
.box {
  width: 100px;
  height: 100px;
  background-color: black;
  float: right;
}
```

```html
<div class="box"></div>
<p>This text wraps around the floated element.</p>
```

---

## Important Note About Float

* Floated elements are **removed from normal flow**
* Parent elements may **collapse**
* Commonly fixed using `clear` or clearfix

---

## Summary Table

| Layout Type | Purpose                 |
| ----------- | ----------------------- |
| Normal Flow | Default document layout |
| Float       | Horizontal alignment    |
| Position    | Exact placement         |
| Flexbox     | One-dimensional layout  |
| Grid        | Two-dimensional layout  |

---

