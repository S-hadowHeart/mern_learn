# CSS Text Properties

CSS text properties are used to **style and format text content** on a web page.
They help improve **readability, alignment, and visual appearance** of text.

---

## List of Text Properties

1. `color`
2. `text-align`
3. `text-decoration`
4. `text-transform`
5. `text-indent`
6. `letter-spacing`
7. `line-height`
8. `word-spacing`

---

## Example HTML

```html
<h3>Hey Mico</h3>
<p>Lorem ipsum dolor sit amet...</p>
```

---

## Text Color

Defines the color of the text.

```css
p {
  color: red;
}
```

---

## Text Alignment

Controls horizontal alignment of text.

```css
h3 {
  text-align: right;   /* left, center, right, end, justify */
}
```

### What is `justify`?

* Aligns text evenly on **both left and right sides**
* Commonly used in newspapers and articles
* Adds spacing between words to align text edges

```css
p {
  text-align: justify;
}
```

---

## text-align-last

Aligns the **last line** of a text block.

```css
p {
  text-align-last: center;   /* left, right, justify */
}
```

Useful when text is justified but the last line needs different alignment.

---

## Text Direction

Controls the direction of text flow.

```css
p {
  direction: rtl;   /* ltr (default), rtl */
}
```

Used for languages like Arabic and Hebrew.

---

## Text Decoration

Adds decorative lines to text.

```css
p {
  text-decoration: underline;   /* overline, line-through, none */
}
```

Advanced styles:

* `underline`
* `double`
* `dashed`
* `wavy`

---

## Text Transform

Controls letter casing.

```css
p {
  text-transform: uppercase;   /* lowercase, capitalize */
}
```

---

## Text Indentation

Adds space before the first line of text.

```css
p {
  text-indent: 100px;
}
```

Mostly used in paragraphs.

---

## Letter Spacing

Controls spacing between characters.

```css
p {
  letter-spacing: 7px;
}
```

---

## Line Height

Controls spacing between lines of text.

```css
p {
  line-height: 1.5;   /* recommended over fixed px */
}
```

Better readability when using unit-less values.

---

## Word Spacing

Controls spacing between words.

```css
p {
  word-spacing: 10px;
}
```

---

## Summary

* Text properties improve **readability and layout**
* `justify` aligns text on both sides
* `line-height` should usually be unit-less
* Proper spacing makes content easier to read

---
