# Generate Random Strings Natively

A better and faster way to generate random strings in the browser with Web Crypto.

```javascript
var array = new Uint32Array(5);
self.crypto.getRandomValues(array);

for ( let i = 0; i < array.length; i++) {
  console.log(`str-${array[i]}`);
}
```

---

#### Refs

- Docs: https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API
- Example: https://codepen.io/feketegy/pen/abqzYKJ?editors=0011
