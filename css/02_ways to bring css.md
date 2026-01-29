## 3 Ways to Apply CSS

CSS can be applied to HTML documents in **three different ways**:

1. Inline CSS
2. Internal CSS
3. External CSS

---

## 1. Inline CSS

* CSS is written **directly inside an HTML element**
* Uses the `style` attribute
* Applies styles to **only one element**
* Not recommended for large projects

### Example

```html
<p style="color: red; font-size: 18px;">
  Hello World
</p>
```

### Advantages

* Quick and easy for small changes
* Useful for testing styles

### Disadvantages

* Poor readability
* Hard to maintain
* No reusability
* Breaks separation of HTML and CSS

---

## 2. Internal CSS

* CSS is written inside a `<style>` tag
* Placed inside the `<head>` section of the HTML file
* Applies styles to a **single HTML page**

### Example

```html
<head>
  <style>
    p {
      color: blue;
      font-size: 16px;
    }
  </style>
</head>
```

### Advantages

* Better than inline CSS
* Useful for single-page styling
* Easy to manage small projects

### Disadvantages

* Not reusable across multiple pages
* Increases HTML file size

---

## 3. External CSS

* CSS is written in a **separate `.css` file**
* Linked to HTML using `<link>`
* Best and most professional approach

### Example

**style.css**

```css
p {
  color: green;
  font-size: 16px;
}
```

**index.html**

```html
<link rel="stylesheet" href="style.css">
```

### Advantages

* Clean and organized code
* Easy maintenance
* Reusable across multiple pages
* Faster loading (browser caching)
* Best practice for real-world projects

---

## Comparison Summary

| Type     | Scope          | Reusable | Recommended |
| -------- | -------------- | -------- | ----------- |
| Inline   | Single element | No       | No          |
| Internal | Single page    | Limited  | Sometimes   |
| External | Entire website | Yes      | Yes         |

---

### Rule of Thumb

* **Inline** → Avoid
* **Internal** → Small demos
* **External** → Real projects

---

###Priority of CSS in the file
The priority of CSS rules is important because it determines which styles are applied to an element when there are confllicting rules or multiple CSS applied to a single element 
Order of css priority : 
1. inline css
2. internal css
3. external css

if you change sequence of external css link and internal css priprity order may change but not always 
