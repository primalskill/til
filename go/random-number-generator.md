# Random Number Generator

Use `crypto/rand` for generating random numbers and the function below:

```golang
func genRand(l uint32) (b []byte, err error) {
	b = make([]byte, l)
	_, err = rand.Read(b)
	if err != nil {
		return
	}

	return
}
```

---

#### Refs

- Example: https://go.dev/play/p/RCLmHCQtgfh
