## Introduction to CSS Selectors

CSS selectors are used to **select HTML elements** that you want to style. They are a **fundamental part of CSS**.

In theory, selectors are **patterns** used to target elements to which a set of CSS rules will be applied. CSS selectors allow us to select elements based on:

* Element type
* Class
* ID
* Attributes
* State or position in the document

---

## Types of CSS Selectors

CSS selectors can be divided into **five categories**:

1. Simple selectors
2. Combinators
3. Attribute selectors
4. Pseudo-class selectors
5. Pseudo-element selectors

**Note:** CSS selectors cannot be used with **inline CSS**.
We use **internal CSS** (or external CSS) to demonstrate selectors.

---

## Simple Selectors

Simple selectors are the **most commonly used selectors** in CSS. They are straightforward and easy to understand.

Simple selectors include:

1. Universal selector
2. Element selector
3. Class selector
4. ID selector
5. Selector list

---

### 1. Universal Selector

Selects **all elements** on the page.

```css
* {
  margin: 0;
  padding: 0;
}
```

---

### 2. Element Selector

Selects elements based on their **HTML tag name**.

```css
h1 {
  color: #808081;
}
```

---

### 3. Class Selector

Selects elements with a **specific class name**.
Multiple elements can share the same class.

**HTML**

```html
<p class="pra">hello</p>
<h1 class="pra">haha</h1>
<p class="pra mil">ok</p>
```

**CSS**

```css
.pra {
  color: #d0ae26;
}

.hello {
  font-size: 60px;
}
```

---

### 4. ID Selector

Selects a **single unique element**.
IDs must be **unique** in an HTML document.

**HTML**

```html
<p id="id1">hello</p>
```

**CSS**

```css
#id1 {
  color: whitesmoke;
  background-color: black;
}
```

---

### 5. Selector List

Allows you to apply the **same styles to multiple selectors**.

```css
.class1, .class7, .class10 {
  /* styles */
}
```

---

## CSS Combinators

A CSS selector can contain **more than one simple selector**.
Between selectors, we use **combinators** to define relationships.

### Types of combinators:

1. Descendant selector
2. Child selector
3. Adjacent sibling selector
4. General sibling selector

---

### Example HTML Structure

```html
<h1>Hello World</h1>

<main>
  <p>Hello I am a paragraph</p>
</main>

<h1>
  <p>Hola World</p>
</h1>

<section>
  <p>Hello World</p>
</section>

<p>Hello I am second paragraph</p>
<p>hool</p>

<a href="Google.com" target="_blank">Google</a>
<img src="hello.png" alt="im" />
<img src="hello.png" alt="im1" />
```

---

### 1. Descendant Selector

Selects elements that are **inside another element** (at any level).

```css
main p {
  color: red;
}
```

---

### 2. Child Selector

Selects elements that are **direct children only**.

```css
h1 > p {
  color: blue;
}
```

---

### 3. Adjacent Sibling Selector

Selects the **immediately next sibling** element.

```css
section + p {
  color: yellow;
}
```

---

### 4. General Sibling Selector

Selects **all sibling elements** that come after a specified element.

```css
section ~ p {
  color: yellow;
}
```

---

## Attribute Selectors

Attribute selectors target elements based on the **presence or value of attributes**.

### Exact Attribute Match

```css
[target="_blank"] {
  color: pink;
  text-decoration: none;
}
```

---

### Attribute Contains Word

Selects elements whose attribute value **contains a specific word**.

```css
[alt~="im"] {
  background-color: black;
}
```

---
