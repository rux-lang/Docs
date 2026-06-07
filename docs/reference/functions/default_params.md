# Default Parameters

A parameter may have a default value.

```rux
func DrawLine(x: int32, y: int32 = 0) {
    // ...
}
```

This allows a caller to omit trailing arguments when the compiler can safely fill them in.

## Example

```rux
func CreatePoint(x: float64, y: float64 = 0.0) -> Point {
    return Point { x: x, y: y };
}
```

## Call usage

```rux
CreatePoint(5.0);
CreatePoint(5.0, 7.0);
```

## Rules

* Default arguments are used for omitted trailing parameters.
* Defaults are applied in order from left to right.
* Default values must be compatible with the parameter type.

## Common mistake

```rux
func Foo(a: int32 = 1, b: int32) {
    // ...
}
```

Defaults only help when the omitted arguments are at the end of the call.
