# CSS Media Queries

---

## What is Mobile-First UI?
**Mobile-first UI** is a design approach where you:
- Design the layout **for mobile devices first**
- Then scale up for tablets and desktops using media queries

### Why Mobile-First?
- Most users browse on **mobile devices**
- Improves **performance**
- Easier to manage responsive layouts

---

## What is Responsive Design?
Responsive design ensures that a website:
- Adapts to **different screen sizes**
- Avoids **overlapping elements**
- Provides a good user experience on all devices

---

## Introduction to Media Queries

Media queries are a feature of CSS that allow you to apply **different styles** based on the **device characteristics**.

They are commonly used to make websites responsive for:
- Smartphones
- Tablets
- Laptops
- Desktop computers

---

## Advantages of Media Queries

1. **Responsive design**
2. **Customized user experience**
3. **Improved performance**
4. **Enhanced accessibility**
5. **Simplified maintenance**
6. **Print support**

---

## General Syntax of Media Queries

```css
@media media_target and (media_feature: value) {
  /* CSS styles */
}
````

### Example:

```css
@media screen and (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

---

## Media Query in Action (Code Walkthrough)

### Default Styles (Mobile First)

```css
.container {
  width: 100%;
  padding: 10px;
}
```

### Tablet and Above

```css
@media screen and (min-width: 768px) {
  .container {
    width: 70%;
    margin: auto;
  }
}
```

---

## What is Viewport?

The **viewport** is the **visible area of the web page** on a device.

* On desktops, it matches the browser width
* On mobile, it depends on device resolution and scaling

---

## Viewport Meta Tag

To make media queries work correctly on mobile devices, you must define the viewport using a **meta tag**.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Why It Is Important?

* Without the viewport meta tag:

  * Media queries work on **desktop**
  * Media queries **fail on mobile devices**
* With the viewport tag:

  * Layout scales correctly
  * Media queries behave as expected

---

## Using Logical Conditions in Media Queries

Media queries support logical operators like `and`.

### Example:

```css
@media screen and (min-width: 600px) and (max-width: 900px) {
  body {
    background-color: lightgreen;
  }
}
```

---

## Writing Media Queries for Different Screens

### Typical Breakpoints

Since there are many devices, we group them into **common screen sizes**.

---

### Extra Small Devices (Phones)

```css
@media only screen and (max-width: 600px) {
  /* styles */
}
```

---

### Small Devices (Portrait Tablets & Large Phones)

```css
@media only screen and (min-width: 600px) {
  /* styles */
}
```

---

### Medium Devices (Landscape Tablets)

```css
@media only screen and (min-width: 768px) {
  /* styles */
}
```

---

### Large Devices (Laptops / Desktops)

```css
@media only screen and (min-width: 992px) {
  /* styles */
}
```

---

### Extra Large Devices (Large Screens)

```css
@media only screen and (min-width: 1200px) {
  /* styles */
}
```

---

## Why Media Queries Are Popular?

Media queries became popular because of:

* The increasing number of devices
* The rise of mobile browsing
* Better user experience
* Improved accessibility
* Better performance
* Print support

---

## Media Query Example (Complete Walkthrough)

```css
body {
  font-size: 14px;
}

/* Tablets */
@media screen and (min-width: 768px) {
  body {
    font-size: 16px;
  }
}

/* Desktops */
@media screen and (min-width: 992px) {
  body {
    font-size: 18px;
  }
}
```

