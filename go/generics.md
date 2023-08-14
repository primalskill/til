# Generics

## Define the type in the function signature

Code in square brackets `[T any]` defines the type that the func argument will use `(thing T)`

```golang
func AnyExample[T any](thing T) {
	fmt.Println(thing)
}

MyPrint("hello world")
MyPrint(42)
MyPrint(true)
```

---

## Constraints in types

Constrain the func argument to either `int` or `string`.

```golang
func ContstraintsExample[T int | string](intOrString T) {
	fmt.Println(intOrString)
}
```


```golang
func MultiTypeExample[A any, B int | string](a A, b B) {
	fmt.Printf("a: %+v, b: %+v", a, b)
}
```

## Constraints with interfaces

Constrain with an interface that must implement a method. `[T Stringer]` defines an interface type that needs to satisfy `Stringer`

```golang
type Stringer interface {
	String() string
}

type myStringer struct{}
func (p myStringer) String() string {
	return "hello"
}

func StringerExample[T Stringer](thing T) {
	fmt.Println(thing.String())
}
```

---

## Comparables

If a type can constrain to interfaces that need to define the functions on the interface, so as operators. This is what Go calls _comparables_.
Comparable defines the `==` and `!=` operators on the type.

```golang
func NotComparableExample[T any](a, b T) {
	fmt.Println(a == b)
}

NotComparableExample(1, 1) // invalid operation: a == b (incomparable types in type set)
```

```golang

func ComparableExample[T comparable](a, b T) {
	fmt.Println(a == b)
}

ComparableExample(1, 1) // true
ComparableExample(1, 2) // false
```

---

#### Refs

- Examples: https://go.dev/play/p/IomNXLIBXGU
- Tutorial: https://bitfieldconsulting.com/golang/generics
















