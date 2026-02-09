# Advanced CSS Grid Concepts

## `grid-template-rows` / `grid-template-columns`

These properties define **structure of the grid**.

---

## `repeat()`

Used to **avoid writing same values again and again**.

### Syntax

```css
repeat(number, value)
```

### Example

```css
grid-template-columns: repeat(3, 1fr);
```

➡ Creates **3 equal columns**

```css
grid-template-rows: repeat(2, 150px);
```

➡ Creates **2 rows of 150px each**

---

## `minmax()`

Used to define a **range (minimum and maximum size)** for rows or columns.

### Syntax

```css
minmax(min, max)
```

### Example

```css
grid-template-columns: repeat(3, minmax(150px, 1fr));
```

Meaning:

* Column width will be **at least 150px**
* Can expand up to **1fr**

💡 Very useful for **responsive layouts**

---

## Combining `repeat()` + `minmax()`

```css
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

✔ Automatically adjusts number of columns
✔ Best for galleries and albums

---

## Grid Row / Column Start & End

These properties control **where a grid item is placed**.

---

### `grid-row-start` & `grid-row-end`

```css
.item {
  grid-row-start: 1;
  grid-row-end: 3;
}
```

➡ Item spans **row 1 to row 3**

---

### `grid-column-start` & `grid-column-end`

```css
.item {
  grid-column-start: 2;
  grid-column-end: 4;
}
```

➡ Item spans **column 2 to column 4**

---

### Shorthand

```css
grid-row: 1 / 3;
grid-column: 2 / 4;
```

---

### Using `span`

```css
grid-column: span 2;
grid-row: span 3;
```

➡ Item spans **2 columns** or **3 rows**

---

## `justify-content` vs `justify-items`

⚠️ **Very important difference**

---

### `justify-content`

* Aligns the **entire grid**
* Works on the **grid container**
* Horizontal alignment

```css
justify-content: center;
```

Affects:

* start
* center
* end
* space-between
* space-around
* space-evenly

---

### `justify-items`

* Aligns **items inside their grid cells**
* Works on **grid container**
* Horizontal alignment of items

```css
justify-items: center;
```

Values:

* start
* center
* end
* stretch (default)

---

## `align-items`

* Aligns items **vertically inside grid cells**
* Applied on **grid container**

```css
align-items: center;
```

Values:

* start
* center
* end
* stretch

---

## Summary Table

| Property        | Works On  | Purpose                                |
| --------------- | --------- | -------------------------------------- |
| justify-content | container | aligns whole grid horizontally         |
| align-content   | container | aligns whole grid vertically           |
| justify-items   | container | aligns items horizontally inside cells |
| align-items     | container | aligns items vertically inside cells   |

---

# Grid Album Example (Color Album)

### HTML

```html
<div class="album">
  <div class="box red"></div>
  <div class="box blue"></div>
  <div class="box green"></div>
  <div class="box yellow"></div>
  <div class="box purple"></div>
  <div class="box orange"></div>
</div>
```

---

### CSS

```css
.album {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  grid-auto-rows: 150px;
  gap: 15px;

  justify-items: center;
  align-items: center;
}

.box {
  width: 100%;
  height: 100%;
  border-radius: 12px;
}

/* Colors */
.red { background: red; }
.blue { background: blue; }
.green { background: green; }
.yellow { background: yellow; }
.purple { background: purple; }
.orange { background: orange; }
```
