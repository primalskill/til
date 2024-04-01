# Dependency Injection

- Go implements structural typing or duck-typing.
- A struct doesn't have to implement an interface explicitly.

```go
package main

import (
 "fmt"

 "play.ground/bar"
 "play.ground/foo"
)

// sayHello defines the method(s) that the struct needs to implement.
// The services doesn't have to implement the interface explicitly, if the Hello() method with the same signature is implemented
// on a struct it implements the interface "automatically". This is called structural typing or duck-typing.
type sayHello interface {
 Hello(str string) string
}

// printHello outputs the message by passing srv in the argument and running the Hello() method on it.
// Notice that the argument signature is `srv sayHello` where sayHello is the interface above.
func printHello(srv sayHello) {
 fmt.Printf(srv.Hello("exec hello service"))
}

func main() {
 // init the services
 fooSrv := foo.Service{}
 barSrv := bar.Service{}

 // print the messages
 printHello(fooSrv)
 printHello(barSrv)
}
-- go.mod --
module play.ground
-- foo/foo.go --
package foo

import "fmt"

type Service struct{}

// Hello returns str with `foo - ` prefixed.
// Notice that foo.Service doesn't have to implement the sayHello interface explicitly.
func (p Service) Hello(str string) string {
 return fmt.Sprintf("\nfoo - %s", str)
}
-- bar/bar.go --
package bar

import "fmt"

type Service struct{}

// Hello returns str with `bar - ` prefixed.
// Notice that bar.Service doesn't have to implement the sayHello interface explicitly.
func (p Service) Hello(str string) string {
 return fmt.Sprintf("\nbar - %s", str)
}

```

-----------

**Refs**

- https://en.wikipedia.org/wiki/Structural_type_system
- https://en.wikipedia.org/wiki/Duck_typing
- Working example: https://go.dev/play/p/OvTdfmwwXlt