# Return Types

A function may declare a return type with `->`.

```rux
func Add(a: int32, b: int32) -> int32 {
    return a + b;
}
```

If no return type is written, the compiler treats the function as returning an opaque or implicit default return type depending on the compilation stage.

```rux
func Log(text: char8[]) {
    Print(text);
}
```

## Why explicit return types matter

Explicit return types help with:

* readability
* overload resolution
* API stability
* FFI compatibility
* compiler diagnostics
