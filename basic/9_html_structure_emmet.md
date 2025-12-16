
# HTML Notes

## 1. HTML Boilerplate

The basic structure of every HTML document.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

</body>
</html>
````

---

## 2. HTML Comments

Used to add notes inside HTML, ignored by the browser.

```html
<!-- This is a comment -->
```

---

## 3. HTML Tags

A tag usually has:

* Opening tag: `<tag>`
* Content
* Closing tag: `</tag>`

Example:

```html
<p>This is a paragraph</p>
```

Self-closing tags (no closing tag required):

```html
<br />
<hr />
<img src="" alt="">
<input type="text" />
```

Full-line elements (block elements):

```html
<div>Content</div>
<section>Content</section>
<article>Content</article>
```

---

## 4. HTML Attributes

Attributes add extra power or information to HTML tags.

```html
<img src="image.png" alt="Sample Image">
<a href="https://example.com">Visit</a>
<input type="text" placeholder="Enter name">
```

---

## 5. HTML Entities

Used to display reserved characters.

Common entities:

| Entity   | Meaning            |
| -------- | ------------------ |
| `&lt;`   | <                  |
| `&gt;`   | >                  |
| `&amp;`  | &                  |
| `&copy;` | ©                  |
| `&quot;` | "                  |
| `&nbsp;` | non-breaking space |
| `&#63;`  | ?                  |

Examples:

```html
<p>5 &lt; 3</p>
<p>Copyright &copy; 2025</p>
<p>Question mark: &#63;</p>
```

---

## 6. Introduction to Emmet

Emmet is a plugin for text editors that allows writing HTML and CSS faster using abbreviations.

Example:

Typing:

```
div.container>ul>li*3
```

Expands to:

```html
<div class="container">
    <ul>
        <li></li>
        <li></li>
        <li></li>
    </ul>
</div>
```
---

## 🔹 **Parent → Child (`>`)**

### **Emmet**

```emmet
div>p>li
```

### **HTML Output**

```html
<div>
  <p>
    <li></li>
  </p>
</div>
```

---

## 🔹 **Multiple Elements (`*`)**

### **Emmet**

```emmet
div*2
```

### **HTML Output**

```html
<div></div>
<div></div>
```

---

## 🔹 **Class (`.`) and ID (`#`)**

### **Emmet**

```emmet
div.class1>p.classp>p#un1>li*5
```

### **HTML Output**

```html
<div class="class1">
  <p class="classp">
    <p id="un1">
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
    </p>
  </p>
</div>
```

---

## 🔹 **Sibling Elements (`+`)**

### **Emmet**

```emmet
div>p+p+p
```

### **HTML Output**

```html
<div>
  <p></p>
  <p></p>
  <p></p>
</div>
```

---

## 🔹 **Parent + Sibling Combo**

### **Emmet**

```emmet
div>p+span+ul
```

### **HTML Output**

```html
<div>
  <p></p>
  <span></span>
  <ul></ul>
</div>
```

---

## 🔹 **Text inside element (`{}`)**

### **Emmet**

```emmet
p{Hello World}
```

### **HTML Output**

```html
<p>Hello World</p>
```

---

## 🔹 **Numbered items (`$`)**

### **Emmet**

```emmet
li.item$*3
```

### **HTML Output**

```html
<li class="item1"></li>
<li class="item2"></li>
<li class="item3"></li>
```

---

## 🔥 **Most Useful Emmet (Remember This!)**

| Symbol | Meaning   |
| ------ | --------- |
| `>`    | Child     |
| `+`    | Sibling   |
| `*`    | Multiple  |
| `.`    | Class     |
| `#`    | ID        |
| `{}`   | Text      |
| `$`    | Numbering |

---

### Features of Emmet

* Abbreviation expansion
* Code formatting
* Code snippets
* Customization
* Cross-editor compatibility

---

## 7. Meta Tags in HTML

Meta tags provide information about the webpage (information about information).

Examples:

```html
<meta charset="UTF-8">
<meta name="description" content="Website description here">
<meta name="keywords" content="html, css, javascript">
<meta name="author" content="Your Name">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

The browser and search engines use these tags for SEO, page rendering, and responsive behavior.

---




