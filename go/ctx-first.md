# Context As First Argument in Functions

It's an unwritten rule to accept context variables as the first function argument. A lot of packages use this pattern.

```golang
func myFunc(ctx context.Context, str string) {
  ...
}
```
