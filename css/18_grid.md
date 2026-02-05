# CSS Grid Layout — Complete Notes

## Grid vs Flex & What Problem Was in Flexbox

### Problem with Flexbox

Flexbox is **one-dimensional**, meaning:

* It works **either in row OR column**, not both at the same time.
* Managing **complex layouts (rows + columns together)** becomes difficult.
* Aligning items across multiple rows and columns needs extra hacks.

### Why Grid Was Introdued

CSS Grid solves this by providing a **two-dimensional layout system**:

* Works with **rows and columns together**
* Ideal for **page layouts**, dashboards, forms, galleries
* Cleaner code, no floats or positioning tricks

---

## What is CSS Grid?

An **intersection of vertical and horizontal lines** is called a **Grid**.

CSS Grid provides a **grid-based layout system with rows and columns**, making webpage design easier and more structured.

Key points:

* Layout is defined in **CSS**, not HTML
* No need for `float` or complex `position`
* Similar to a table layout, but **far more powerful and flexible**
* Best suited for **two-dimensional layouts**

---

## Terminologies Associated with Grid

1. **Grid Container** – Parent element where grid is applied
2. **Grid Items** – Direct child elements of the grid container
3. **Row** – Horizontal track
4. **Column** – Vertical track
5. **Gap** – Space between rows and columns
6. **Grid Line** – Lines that divide rows and columns

---

## Grid Container

A **grid container** holds grid items arranged into rows and columns.

To create a grid container:

```css
.container {
  display: grid;
}
```

---

## Properties of Grid Container

### 1. `grid-template-rows`

Defines the **height of each row**.

```css
grid-template-rows: 100px 200px auto;
```

---

### 2. `grid-template-columns`

Defines the **number and width of columns**.

```css
grid-template-columns: 200px 1fr 1fr;
```

* `auto` → adjusts based on content
* `fr` → fraction of available space

---

### 3. `gap`

Controls spacing between rows and columns.

```css
gap: 20px;
row-gap: 10px;
column-gap: 15px;
```

---

### 4. `justify-content`

Aligns the **entire grid horizontally** inside the container.

Values:

* start
* center
* end
* space-between
* space-around
* space-evenly

```css
justify-content: center;
```

---

### 5. `align-content`

Aligns the **entire grid vertically** inside the container.

```css
align-content: space-between;
```

---

## Grid Items

Grid items are **direct children** of the grid container.

By default:

* Each item occupies **one cell**
* Items flow row by row

---

## Properties of Grid Items

### 1. `grid-row`

Defines **where the item starts and ends vertically**.

```css
grid-row: 1 / 3;
```

or using span:

```css
grid-row: span 2;
```

---

### 2. `grid-column`

Defines **where the item starts and ends horizontally**.

```css
grid-column: 2 / 4;
```

or:

```css
grid-column: span 3;
```

---

### 3. `grid-area` (Shorthand)

Shorthand for:

* grid-row-start
* grid-column-start
* grid-row-end
* grid-column-end

```css
grid-area: 1 / 2 / 3 / 4;
```

---

## Naming Grid Areas

Grid allows assigning **names to areas**, making layouts very readable.

### Example:

```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
}

.header { grid-area: header; }
.sidebar { grid-area: sidebar; }
.content { grid-area: content; }
.footer { grid-area: footer; }
```

---

## Benefits of CSS Grid

1. **Two-Dimensional Layout**

   * Handles rows and columns together

2. **Separation of Content & Design**

   * HTML stays clean
   * Layout controlled purely by CSS

3. **Less Code**

   * No extra wrapper divs
   * No floats or positioning hacks

4. **Smaller File Size**

   * No need for frameworks like Bootstrap

5. **Faster Development**

   * Quick prototyping
   * Easy layout changes

6. **Nested Grids**

   * Grids inside grids for complex designs

7. **Responsive Friendly**

   * Works perfectly with media queries

---

## When to Use Grid vs Flex

| Use Case                | Choose |
| ----------------------- | ------ |
| Page layout             | Grid   |
| Forms                   | Grid   |
| Dashboard               | Grid   |
| Navbar                  | Flex   |
| Small components        | Flex   |
| One-direction alignment | Flex   |

