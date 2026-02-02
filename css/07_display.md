# CSS `display` Property

The `display` property in CSS specifies **how an element is displayed** in the document flow.  
It affects **layout**, **width/height behavior**, and **whether the element starts on a new line**.

---

## 1. `block`

- Default for elements like `<p>`, `<div>`, `<h1>` etc.
- Starts on a **new line**.
- **Occupies full width** of the parent container.
- Can set **width** and **height**.

### Example:

```html
<p>This is a block element</p>
<div style="width:200px; height:100px; background-color: lightgreen;">
  Block div
</div>
````

---

## 2. `inline`

* Default for elements like `<span>`, `<a>`, `<strong>`.
* Does **not start on a new line**.
* Only takes up **space required by content**.
* **Width and height cannot be set.**

### Example:

```html
<span style="color: red;">This is inline</span>
<a href="#">This is also inline</a>
```

> ⚠️ Trying to set width/height on inline elements will not work:

```css
span {
  width: 100px; /* ignored */
  height: 50px; /* ignored */
}
```

---

## 3. `inline-block`

* Behaves like `inline` (does not start on a new line).
* **Width and height can be set**.
* Useful for layouts that need inline behavior but also sizing.

### Example:

```html
<span style="display:inline-block; width:150px; height:50px; background-color: lightblue;">
  Inline-block span
</span>
```

---

## 4. `none`

* **Hides the element completely**.
* The element **does not occupy space** in the layout.

### Example:

```html
<div style="display:none;">
  You cannot see me
</div>
```

---

## 5. `visibility: hidden`

* The element is **invisible**, but **still occupies space** in the layout.

### Example:

```html
<div style="visibility:hidden; width:200px; height:100px; background-color: pink;">
  Hidden but space reserved
</div>
```

---

## 6. Changing Display

You can change the display type of any element using CSS:

```css
p {
  display: inline; /* Makes block element behave like inline */
}

span {
  display: block; /* Makes inline element behave like block */
}

div {
  display: inline-block; /* Inline with width/height control */
}
```

---

## 7. Summary Table

| Display Type        | New Line | Width/Height | Space Occupied | Example         |
| ------------------- | -------- | ------------ | -------------- | --------------- |
| `block`             | Yes      | Yes          | Yes            | `<p>`, `<div>`  |
| `inline`            | No       | No           | Yes            | `<span>`, `<a>` |
| `inline-block`      | No       | Yes          | Yes            | `<span>`        |
| `none`              | N/A      | N/A          | No             | Any element     |
| `visibility:hidden` | No       | Yes          | Yes            | Any element     |



