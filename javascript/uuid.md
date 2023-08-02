# Generate UUID Natively

No need for JS modules to generate UUID v4 IDs anymore because it can be done natively in the browser by using WebCrypto,

```javascript
let uuid = self.crypto.randomUUID();
console.log(uuid);
```

---

#### Refs

- Docs: https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API
- Example: https://codepen.io/feketegy/pen/abqzYKJ?editors=0011
