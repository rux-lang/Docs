# Parameters

A function parameter has a name and a type.

```rux
func Add(a: int32, b: int32) -> int32 {
    return a + b;
}
```

## Parameter syntax

```rux
name: Type
```

Example:

```rux
func Square(value: int32) -> int32 {
    return value * value;
}
```

## Parameter names

Parameter names are part of the declaration and are available inside the function body.

```rux
func Mix(left: int32, right: int32) -> int32 {
    return left + right;
}
```

## Parameter types

Every non-variadic parameter has a type.

```rux
func PrintNumber(value: int32);
```

The compiler uses parameter types for type checking, overload resolution, and lowering.
