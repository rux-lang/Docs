# Variadic Functions

A function may accept a variadic parameter.

```rux
func PrintAll(...items: char8[]) {
    // ...
}
```

Or in parameter form:

```rux
func Sum(values: int32...) -> int32 {
    // ...
}
```

Variadic parameters collect extra arguments into a slice-like value during lowering.

## Example

```rux
func LogAll(prefix: char8[], values: int32...) {
    // ...
}
```

## Call behavior

Variadic calls can be made in two ways:

* by passing separate trailing arguments
* by passing a spread argument when the language supports it

Example:

```rux
LogAll("sum", 1, 2, 3);
```

## Notes

* Variadic parameters are treated specially by the compiler.
* Only the last parameter may be variadic.
* Extra arguments beyond the fixed parameters are gathered into a slice.
