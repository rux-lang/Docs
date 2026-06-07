# Calling Functions

Functions are called by writing the function name followed by parentheses.

```rux
Add(1, 2);
```

## Argument checking

The compiler checks:

* number of arguments
* argument types
* variadic usage
* spread usage
* whether overload resolution can find a match

## Example

```rux
func Add(a: int32, b: int32) -> int32 {
    return a + b;
}

let result = Add(10, 20);
```

## Result type

The result of a call expression is the function’s return type.
