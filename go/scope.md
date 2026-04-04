# Scope in Go

## Concepts and Notes

### Global vs Local Scope

- **Global Variables**: Variables declared outside of any function (like `a`, `b`, `c`, `d`) are accessible from anywhere in the package.
- **Local Variables**: Variables declared inside a function (like `z` in `add`, `res` in `sum`, `p` and `q` in `main`) are only accessible within that specific function.
- **Scope Rule**: A local scope can't be accessed globally. If you try to use a local variable outside its function, the compiler will give an "undefined" error.

### Function Declaration Order

- In Go, it doesn't matter the position of the function or whether it's aligned properly in the file.
- The code will work even if you keep the function anywhere in the file.
- **Condition**: The function must have no errors to execute. The Go compiler doesn't care about the order of the function declaration; it resolves calls regardless of where the function is defined relative to the caller.

## Code Implementation

### Example 1: Global and Local Variable Access

```go
package main

import "fmt"

var (
	a = 20
	b = 30
)

func add(x int, y int) {
	z := x + y
	fmt.Println(z)
}

func main() {
	p := 40
	q := 50

	add(p, q)
	add(a, b)
	add(a, p)
	// add(b, z) //it will give undefined because z is in add func's local scope and local scope can't be access globally.
}
```

### Example 2: Function Order Independence

```go
package main

import "fmt"

var (
	c = 10
	d = 20
)

func sum(x int, y int) {
	res := x + y
	printNum(res)
}

func main() {
	sum(c, d)
}

func printNum(num int) {
	fmt.Println(num)
}

//in this example it doesn't matter the position of the func and wether it's align properly or not, it'll work even if u keep the func anywhere of the file but the func must have no error to execute, because go compiler doesn't care about the order of the func declaration.
```
