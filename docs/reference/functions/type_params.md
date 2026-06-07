# Type Parameters

Functions may be generic.

```rux
func Identity<T>(value: T) -> T {
    return value;
}
```

## Syntax

```rux
func Name<T, U>(params) -> ReturnType
```

## Example

```rux
func First<T>(value: T) -> T {
    return value;
}
```

Type parameters are part of the function signature and influence type resolution.

!!! warning
    Generic syntax is currently supported by the frontend of the compiler.
    Backend support is incomplete and generic code may fail during lowering or code generation.
