# CSS Flexbox

The **Flexible Box Layout Module**, commonly known as **Flexbox**, is a powerful CSS layout model used to create **efficient, flexible, and responsive one-dimensional layouts**.

Flexbox allows elements to be aligned in a **row or a column** and provides better control over spacing, alignment, and order.

---

## Fundamental Terminologies of Flexbox

### 1. Flex Container
- The **parent element**
- Created by applying `display: flex` or `inline-flex`

### 2. Flex Items
- The **direct children** of a flex container

### 3. Main Axis
- The primary axis along which flex items are laid out
- Direction depends on `flex-direction`

### 4. Cross Axis
- Axis perpendicular to the main axis

---

## Benefits of Using Flexbox

- Creates **one-dimensional layouts** (row or column)
- Easy alignment and spacing
- Flexible and responsive
- Automatic space distribution
- Less code compared to traditional layouts

---

## Flex Container Properties
These properties are applied to the **parent (flex container)**.

---

### a. `display`

Defines a flex container.

```css
.container {
  display: flex;
}

/* Inline flex */
.container {
  display: inline-flex;
}
````

---

### b. `flex-direction`

Defines the direction of the main axis.

Values:

* `row` (default)
* `row-reverse`
* `column`
* `column-reverse`

```css
.container {
  flex-direction: row;
}
```

---

### c. `flex-wrap`

Controls whether flex items wrap to the next line.

Values:

* `nowrap` (default)
* `wrap`
* `wrap-reverse`

```css
.container {
  flex-wrap: wrap;
}
```

---

### d. `flex-flow`

Shorthand for `flex-direction` and `flex-wrap`.

```css
.container {
  flex-flow: row wrap;
}
```

---

### e. `justify-content`

Aligns items **along the main axis**.

Values:

* `flex-start`
* `flex-end`
* `center`
* `space-between`
* `space-around`
* `space-evenly`

```css
.container {
  justify-content: space-between;
}
```

---

### f. `align-items`

Aligns items **along the cross axis**.

Values:

* `stretch` (default)
* `flex-start`
* `flex-end`
* `center`
* `baseline`

```css
.container {
  align-items: center;
}
```

---

### g. `align-content`

Aligns **multiple rows** of flex items (works only when wrapping is enabled).

Values:

* `flex-start`
* `flex-end`
* `center`
* `space-between`
* `space-around`
* `stretch`

```css
.container {
  align-content: space-around;
}
```

---

### h. Gap Properties

Used to control spacing between flex items.

#### i. `row-gap`

```css
.container {
  row-gap: 20px;
}
```

#### ii. `column-gap`

```css
.container {
  column-gap: 15px;
}
```

#### Shorthand:

```css
.container {
  gap: 20px 15px;
}
```

---

## Flex Item Properties

These properties are applied to **child elements (flex items)**.

---

### a. `order`

Controls the **order** of flex items.

```css
.item {
  order: 2;
}
```

---

### b. `flex-grow`

Defines how much an item **grows relative to others**.

```css
.item {
  flex-grow: 1;
}
```

---

### c. `flex-shrink`

Defines how much an item **shrinks** when space is limited.

```css
.item {
  flex-shrink: 1;
}
```

---

### d. `flex-basis`

Defines the **initial size** of a flex item.

```css
.item {
  flex-basis: 150px;
}
```

---

### e. `flex` (Shorthand)

Shorthand for:

```css
flex: flex-grow flex-shrink flex-basis;
```

Example:

```css
.item {
  flex: 1 1 200px;
}
```

---

### f. `align-self`

Overrides `align-items` for an individual item.

```css
.item {
  align-self: flex-end;
}
```

---

## Simple Flexbox Example

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
}

.item {
  width: 100px;
  height: 100px;
  background-color: steelblue;
}
```

---

## Key Takeaways

* Flexbox is for **one-dimensional layouts**
* Use container properties for layout control
* Use item properties for individual behavior
* Makes responsive layouts easier

