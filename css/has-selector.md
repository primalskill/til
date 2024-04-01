# :has() Selector

CSS now supports `has()` that looks for elements **inside** or an **immediate sibling** of the property it's defined on.

## Sibling Element

Having this HTML example:

```html
<h1>This is a title elem</h1>
<h2>This is a sub-title elem</h1>

<h1>This is another title elem</h1>
<p>There is no sub-title on this section</p>
```

Target the `h1` elem but only that has an immediate `h2` sibling:

```css

h1:has(+ h2) {
  color: red;
}

```

## Child Element

Target child elements of parent then style the parent element accordingly.

Having this HTML example:

```html

<div class="image">
  <img src="https://placedog.net/500/280" alt="doggo 1" />
</div>

 <div class="image">
  <img src="https://placedog.net/400/240" alt="doggo 1" />
  <em>This is a doggo</em>
</div>

```

Target `.image` elements that have `em` child elements.

```css

.image:has(em) {
  padding: 20px;
  border: 1px solid red;
}

```

---

#### Refs

- [Docs - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/:has)
- [Example - Codepen](https://codepen.io/feketegy/pen/gOyXWNO)
