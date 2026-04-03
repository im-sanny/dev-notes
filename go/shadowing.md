# Variable Shadowing in Go

## Concepts and Notes

### What is Variable Shadowing?

- **Definition**: Variable shadowing happens when a local scope variable name matches with any outer scope variable.
- **Behavior**: When you declare a new variable with the same name inside an inner block (like an `if` statement, loop, or function), it "shadows" or hides the outer variable within that specific block.
- **Scope Isolation**: The inner variable is completely independent of the outer one. Changes to the inner variable do not affect the outer variable.
- **Visibility**: Once the inner block ends, the shadowed variable goes out of scope, and the outer variable becomes visible again with its original value intact.

### Key Takeaways

- **Re-declaration**: Using `:=` inside a block with an existing variable name creates a _new_ variable limited to that block.
- **No Conflict**: Go allows this without error, but it can sometimes lead to confusion if not noticed.
- **Best Practice**: Be careful when reusing variable names in nested scopes to avoid accidental shadowing.

## Code Implementation

```go
package main

import "fmt"

var a = 10

func main() {
	age := 30

	if age < 18 {
		a := 47 // This 'a' shadows the global 'a' only inside this if block
		fmt.Println(a) // Prints 47
	}

	// Outside the if block, the global 'a' is visible again
	fmt.Println(a) // Prints 10
}

//variable shadowing happens when a local scope variable name match's with any outer scope variable
```
