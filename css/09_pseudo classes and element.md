# CSS Pseudo-Classes & Pseudo-Elements

CSS pseudo-classes and pseudo-elements allow you to style elements **based on their state** or **specific parts of an element**, without adding extra HTML.

---

## List of Contents
1. Introduction to Pseudo-Classes  
2. Pseudo-Class Selectors  
3. Pseudo-Elements  
4. Difference Between Pseudo-Class and Pseudo-Element  
5. CSS Specificity  

---

## 1. Introduction to Pseudo-Classes

Pseudo-classes are used to select elements **based on their state**.

They apply styles when:
- A user interacts with an element
- An element is in a specific position in the DOM

### Examples of element states:
- When hovered
- When focused
- When clicked
- When it is the first or last child

### Syntax:
```css
selector:pseudo-class {
  property: value;
}
````

---

## 2. Most Frequently Used CSS Pseudo-Class Selectors

### 2.1 `:hover`

Applies when the user **hovers** over an element.

```css
button:hover {
  background-color: blue;
  color: white;
}
```

---

### 2.2 `:focus`

Applies when an element **receives focus** (e.g., input field).

```css
input:focus {
  border: 2px solid green;
  outline: none;
}
```

---

### 2.3 `:link`

Targets **unvisited links**.

```css
a:link {
  color: blue;
}
```

---

### 2.4 `:visited`

Targets **visited links**.

```css
a:visited {
  color: purple;
}
```

---

### 2.5 `:active`

Applies when an element is **being clicked**.

```css
button:active {
  transform: scale(0.95);
}
```

---

### 2.6 `:first-child`

Selects an element that is the **first child of its parent**.

```css
p:first-child {
  color: red;
}
```

---

### 2.7 `:lang()`

Selects elements based on the **language attribute**.

```css
p:lang(en) {
  font-style: italic;
}
```

---

### 2.8 `:nth-child()`

Selects elements based on their **position**.

```css
li:nth-child(2) {
  color: green;
}

li:nth-child(odd) {
  background-color: lightgray;
}
```

---

## 3. Pseudo-Elements

Pseudo-elements allow you to style **specific parts of an element**, not the entire element.

### Syntax:

```css
selector::pseudo-element {
  property: value;
}
```

---

### Common Pseudo-Elements

#### 3.1 `::first-line`

Styles the **first line of text**.

```css
p::first-line {
  font-weight: bold;
}
```

---

#### 3.2 `::first-letter`

Styles the **first letter** of text.

```css
p::first-letter {
  font-size: 30px;
  color: red;
}
```

---

#### 3.3 `::before`

Inserts content **before** an element.

```css
h1::before {
  content: "🔥 ";
}
```

---

#### 3.4 `::after`

Inserts content **after** an element.

```css
h1::after {
  content: " ✔";
}
```

---

#### 3.5 `::marker`

Styles list markers (`•`, numbers).

```css
li::marker {
  color: red;
}
```

---

#### 3.6 `::selection`

Styles text when **selected by the user**.

```css
::selection {
  background-color: yellow;
  color: black;
}
```

---

## 4. Difference Between Pseudo-Class and Pseudo-Element

| Feature | Pseudo-Class              | Pseudo-Element                 |
| ------- | ------------------------- | ------------------------------ |
| Purpose | Selects element **state** | Selects **part of an element** |
| Syntax  | `:`                       | `::`                           |
| Example | `:hover`, `:focus`        | `::before`, `::after`          |
| Affects | Entire element            | Partial content                |

---

## 5. CSS Specificity

CSS specificity determines **which rule is applied** when multiple rules target the same element.

### Specificity Order (Low → High):

1. Element selector (`p`, `div`)
2. Class / pseudo-class (`.box`, `:hover`)
3. ID selector (`#main`)
4. Inline styles

### Example:

```css
p {
  color: blue;
}

p:hover {
  color: red; /* higher specificity */
}
```

---
