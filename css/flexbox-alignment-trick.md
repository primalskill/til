# Flexbox Alignment Trick

If you want a specific number of elements in a row and the rest fill up the next row(s) use this on the child elements:

```css
.item {
  flex: 1 0 calc(100% * 1/7);
}
```

---

#### Refs

- Example: https://codepen.io/feketegy/pen/jOwBoLe
