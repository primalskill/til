# RGB Values as CSS Variables

It's common practice to use only the RGB values in a CSS variable, this way it can add the alpha channel on it if necessary. In the example below, `h2` will have a 30% opacity of the parent CSS color value.

```css
body {
  --red-rgb: 255, 0, 0;
}

h1 {
  color: rgb(var(--red-rgb));
}

h2 {
  color: rgba(var(--red-rgb), 0.3);
}
```

---

#### Refs

- Example: https://codepen.io/feketegy/pen/BambxWw
