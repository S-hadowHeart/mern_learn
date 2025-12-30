# Visualizing the DOM (Document Object Model)

---

## What is DOM?

- **DOM (Document Object Model)** is a programming interface for HTML and XML documents.
- It represents the **web page as a structured object**, so JavaScript can:
  - Read content
  - Modify content
  - Change styles
  - Add / remove elements
- When a browser loads an HTML page, it **creates the DOM**.

👉 JavaScript does **not directly work with HTML**  
👉 JavaScript works with the **DOM**

---

## DOM as an Object

- The entire document becomes an object called `document`
- Every HTML element becomes a **node (object)**
- JavaScript can access these nodes using the `document` object

Example:
```js
document.body
document.head
document.title
````

---

## DOM Tree

* DOM is represented in a **tree structure**
* Each HTML element is a **node**
* Parent–child relationship exists between elements

### Example HTML

```html
<p id="one"><span>Hello</span> Namaste</p>
```

### DOM Tree Representation

```
document
 └── html
     └── body
         └── p (id="one")
             ├── span
             │    └── "Hello"
             └── "Namaste"
```

* `document` → root node
* `html` → parent
* `body` → child of html
* `p` → child of body
* `span` → child of p

---

## Why DOM is Important?

* Allows **dynamic updates** without reloading the page
* Makes webpages **interactive**
* Core of modern frontend development (React, Vue, Angular)

---

## Different Ways to Write JavaScript in `index.html`

### 1. Inline JavaScript (Not Recommended)

```html
<button onclick="alert('Hello')">Click</button>
```

❌ Hard to maintain
❌ Not scalable

---

### 2. Internal JavaScript (Using `<script>` tag)

```html
<script>
  console.log("Hello World");
</script>
```

✔ Good for small demos
❌ Not good for large projects

---

### 3. External JavaScript (Best Practice)

```html
<script src="script.js"></script>
```

✔ Clean code
✔ Reusable
✔ Industry standard

---

## DOM Selection Methods (Based on Given HTML)

---

### HTML Elements Used

```html
<p id="one"><span>Hello</span> Namaste</p>

<li class="tech">One</li>
<li class="tech">Two</li>
<li class="tech">Three</li>

<h4>Hey</h4>
<h4>namaste</h4>
<h4>Hola</h4>

<h2>Hello</h2>
<h2 class="classs">Hola</h2>
<h2 id="ids">Hey</h2>
```

---

## Accessing Elements by ID

```js
let var1 = document.getElementById("one");
console.log(var1.innerText);
```

* Returns **single element**
* `innerText` → visible text only

---

## Accessing Elements by Class Name

```js
let var2 = document.getElementsByClassName("tech");
console.log(var2[2].innerText);
```

* Returns **HTMLCollection**
* Access using index

```js
var2[1].innerText = "Nodejs";
```

---

## Accessing Elements by Tag Name

```js
let var3 = document.getElementsByTagName("h4");
console.log(var3[1].innerHTML);
```

* Returns **HTMLCollection**

```js
var3[2].innerText = "Hello world";
var3[2].style.color = "red";
```

* DOM allows **style manipulation**

---

## Query Selector (Most Powerful)

```js
let var4 = document.querySelector(".classs");
console.log(var4);
```

* Accepts **CSS selectors**
* Returns **first matching element**

Examples:

```js
document.querySelector("#ids");     // id
document.querySelector(".classs"); // class
document.querySelector("h2");      // tag
```

---

## Modifying Attributes

```js
var4.setAttribute("title", "anurag");
```

* Adds or updates attributes dynamically


# Creating & Removing HTML Elements using JavaScript

---

## Creating HTML Elements using JavaScript

JavaScript allows us to **create, style, and insert HTML elements dynamically** using the DOM.

### Steps to Create an HTML Element

1. Create the element
2. Add class / styles / content
3. Append it to the DOM



### Example: Create an `<h1>` Element

```js
let title = document.createElement("h1");
````

* Creates an `h1` element in memory (not yet visible)

---

### Adding Class Name

```js
title.className = "title";
```

* Assigns a CSS class to the element

---

### Adding Styles

```js
title.style.fontSize = "24px";
```

* Styles can be applied directly using `.style`

---

### Adding Text Content

```js
title.textContent = "Creating HTML Element";
```

* `textContent` adds text safely (no HTML parsing)

---

### Appending to the Document

```js
document.body.appendChild(title);
```

* Adds the element to the page
* Now the element becomes visible

---

## Removing HTML Elements using JavaScript

### Select Parent Element

```js
const ul = document.querySelector("ul");
```

---

### Select Child Elements

```js
const lists = document.querySelectorAll("li");
```

* Returns a **NodeList** of `<li>` elements

---

### Remove Elements Using Loop

```js
for (list of lists) {
  ul.removeChild(list);
}
```

* Removes each `<li>` from the `<ul>`

---

## Key DOM Methods Used

| Method               | Purpose                  |
| -------------------- | ------------------------ |
| `createElement()`    | Create new element       |
| `appendChild()`      | Add element to DOM       |
| `removeChild()`      | Remove element           |
| `querySelector()`    | Select single element    |
| `querySelectorAll()` | Select multiple elements |

---

# Event Listeners in JavaScript

Events allow JavaScript to **respond to user actions** like clicks, double-clicks, keyboard input, etc.

---

## Inline Event (Not Recommended)

```html
<button ondblclick="hey()">Submit</button>
```

* Event written directly in HTML
* ❌ Not scalable
* ❌ Hard to maintain

---

## Event Listener using JavaScript (Recommended)

```js
document.addEventListener("click", hello);
```

* Separates HTML and JavaScript
* ✔ Clean
* ✔ Professional approach

---

## Example: Click Event

```js
function hello() {
  document.getElementById("js").innerText = "hello hi";
}
```

* Runs when the document is clicked
* Updates paragraph text

---

## Example: Double Click Event

```js
function hey() {
  let btn = document.getElementById("jss");

  btn.innerText = "hiiii";
  btn.style.color = "red";
  btn.style.backgroundColor = "black";
  btn.style.padding = "16px";
  btn.style.border = "2px solid yellow";
}
```

* Triggered on **double click**
* Dynamically updates:

  * Text
  * Color
  * Background
  * Padding
  * Border

---

## Common DOM Events

| Event       | Description          |
| ----------- | -------------------- |
| `click`     | Mouse click          |
| `dblclick`  | Double click         |
| `mouseover` | Mouse over element   |
| `mouseout`  | Mouse leaves element |
| `keydown`   | Key pressed          |
| `submit`    | Form submission      |

