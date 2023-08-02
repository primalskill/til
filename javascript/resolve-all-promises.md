# Resolve All Promises Regardless of Status

Instead of using `Promise.all(...)` that only resolves if all the promises succeed, use `Promise.allSettled(...)` that resolves regardless of the promise statuses.

```javascript
const p1 = new Promise((resolve, reject) => {  
  setTimeout(() => {
    resolve('p1 resolved');
  }, 100)
});

const p2 = new Promise((resolve, reject) => {
  setTimeout(() => {
    reject('p2 rejected');
  }, 100)
});

// Will fail at p2
Promise.all([p1, p2]).then((values) => {
  console.log(values);
});

// Will resolve all and show the status of each promise
Promise.allSettled([p1, p2]).then((values) => {
  console.log(values);
});

```

---

#### Refs

- Docs: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/allSettled
- Example: https://codepen.io/feketegy/pen/XWZWLOR?editors=0011
