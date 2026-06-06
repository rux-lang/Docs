# Function Declaration Syntax

The general shape of a function is:

```rux
func Name<TypeParams>(params) -> ReturnType {
    body
}
```

or:

```rux
func Name(params) -> ReturnType;
```

## Example

```rux
pub func Clamp(value: int32, min: int32, max: int32) -> int32 {
    if value < min {
        return min;
    }
    if value > max {
        return max;
    }
    return value;
}
```

## Public functions

`pub` marks the function as publicly visible.

```rux
pub func Exported() -> int32 {
    return 1;
}
```

Public visibility is especially important for packages and libraries.
