# Packages and Export Rules in Go

## Concepts and Notes

### Export Rules (Visibility)

- **Uppercase = Public (Exported)**: To access a function, variable, or type from this package (or any package) from another package, we have to name the func/variable/type with an **uppercase letter**.
  - Example: `Money`, `Add` are exported.
- **Lowercase = Private (Unexported)**: If the name starts with a lowercase letter, it is unexported. We **cannot** access the file/function/variable from any other file outside the package.
- **Package Scope**: Visibility is determined strictly by the first letter of the identifier.

### Module Initialization

- **Command**: To run and import a custom package (like `mathlib`), we need to initialize a module first.
- **Syntax**: `go mod init <module_name>`
  - Example: `go mod init example.com`
- **Naming Convention**: Instead of `example.com`, we can just put any name or domain, but it's **recommended to use something unique** (like a domain you own or a specific project path) to maintain standards and avoid conflicts.

## Code Implementation

### Package: `mathlib`

```go
package mathlib

import "fmt"

// Money is exported because it starts with an uppercase letter.
var Money = 100

// Add is exported because it starts with an uppercase letter.
func Add(x int, y int) {
	z := x + y
	fmt.Println(z)
}

// to access func variable and types of this or any package from other package we have to name the func with uppercase letter, neither we can't access the file from any other file.
// to run and import mathlib package we need to run the command: go mod init example.com, instead of example.com we can just put any name or domain but it's recommended to use sth unique to maintain standard.
```
