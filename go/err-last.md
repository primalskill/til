# Return Errors as the Last Variable in Functions

It's an unwritten rule to return error variables as the last variable in a function signature. A lot of packages adopted this pattern.

```golang
func myFunc(str string) (parsed string, err error) {
  ...
}
```
