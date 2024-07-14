# Limit characters to multiple lines

Use `line-clamp` to limit the numbers of **lines** a text can take. The value defines the maximum number of lines that the text can take up.

```css

p {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  line-clamp: 2; 
  -webkit-box-orient: vertical;
}
```

### Notes

- `text-overflow: ellipsis` is optional, it just shows three dots after the cut-off text
- `display: -webkit-box` and `-webkit-box-orient: vertical` are mandatory for WebKit browsers

---

### Refs

- Docs: https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-line-clamp
- Usage statistics: https://caniuse.com/?search=line-clamp
- Example: https://codepen.io/feketegy/pen/zYVGeBP?editors=1100
