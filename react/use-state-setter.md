# Setting a New Value with useState

Always pass a function that takes the previous state as an argument when setting the new state. Otherwise, it will use the initial state when the component was initialized.

### Bad

```javascript
function MyComponent() {
  const [counter, setCounter] = useState(0);

  ...

  setCounter(counter + 1);
}
```

### Good

```javascript
function MyComponent() {
  const [counter, setCounter] = useState(0);

  ...

  setCounter((prevCounter) => prevCounter + 1);
}
```

---

#### Refs

- https://react.dev/reference/react/useState#setstate
