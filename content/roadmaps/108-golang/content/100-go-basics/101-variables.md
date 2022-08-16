# Variables
Go is a strictly typed language, meaning every variable needs to have a type, and the value of that variable can not switch types.

Go makes use of the `var` and `const` keywords to declare either variables, or constants. Variables can be reassigned a value after being declared, while constants can only be assigned a value while being declared.

The basic syntax to declare a variable is 
>`[var or const] [variable name] [type]`

Example:
```go
func main() {

  var foo string
  foo = "foo"

  const bar string = "bar"
}
```

You can also declare multiple variables at once, by stacking them on a single line, seperated by a comma. Example:
```go
func main() {

  var foo, bar string
  foo, bar = "foo", "bar"

  // OR

  var foo, bar string = "foo", "bar"
}
```

Altough every variable needs to have a type, you don't always have to identify the type yourself. Go is in most cases smart enough to figure out variable types itself. Take a look below:
```go
func main() {

  var foo = "foo"  
  const bar = "bar"

}
```

Lastly, Go has a shorthand notation to declare variables, note that this declares variables, and not constants. 
```go
func main() {

  foo := "foo" // same as `var foo string = "foo"`
  bar := "bar" // same as `var bar string = "bar"`

  // OR

  foo, bar := "foo", "bar" // same as above

}
```

## Nil
Within Go and variable declaration there is a special case called nil. Nil is the null value of Go. You can't assign it to atomic types, such as string, integer, uinteger, etc. It can be assigned to more complex types, such as structs, which will be handled later on.

When assigning nil, you have to declare a type, since nil is not a type of it's own. This will throw the UntypedNil error.
```go
func main() {

  var foo = nil
  // Error: UntypedNil (meaning, nil doesn't have a type, Go doesn't know what type foo is)

}
```

