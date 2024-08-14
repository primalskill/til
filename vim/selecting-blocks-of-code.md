# Selecting Blocks of Code

- `va{` or `va}` - select everything around `{}` - `v` enter visual mode, `a{` select _around_ `{}`
- `vi{` or `vi}` - select everything inside `{}` - `v` enter visual mode, `i{` select _inside_ `{}`
- `va(`, `vi(` - works the same way, selecting everything _around_ or _inside_ `()`
- `vat` or `vit` - select everything _around_ or _inside_ a tag, if working with HTML for example. Tag means `<` or `>`

## Selecting a whole function

1. Go to the beginning of the function line
2. Press `vf{%`, `v` enter visual mode, `f{` find `{` on the line, `%` select matching curly brace.

Note: This works with parens, tags, and square brackets.

### Example:

```javascript
function Hello() {
  const a = 'Hello, World!';
  console.log(a);
}
```

1. Go to the beginning of of the `function` line
2. Press `v` to enter visual mode
3. Press `f{` to find the first occurence of `{`
4. Press `%` to find the matching curly brace.

This will select the whole function.
