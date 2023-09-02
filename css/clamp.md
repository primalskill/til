# Clamp Values

CSS now supports `clamp()` that can define a minimum and maximum value for any CSS property (example shows `font-size` but can set it to any property).

The example below sets the `font-size` for `h2` to have a minimum value of `14px`, and a maximum value of `24px` or `3vw` otherwise.

```css
h2 {
  font-size: clamp(14px, 3vw, 24px);
}
```

This greatly simplifies setting CSS properties to different values by using media queries in the past.

---

#### Refs

- [Docs - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp)
- [Tutorial - Fluid Typography](https://css-tricks.com/simplified-fluid-typography/)
- [Example - Codepen](https://codepen.io/feketegy/pen/zYyBQoq)
