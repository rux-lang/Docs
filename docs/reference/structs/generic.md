# Generic Structs

Structs may declare type parameters.

```rux
struct Box<T> {
    value: T;
}
```

Type parameters are parsed, preserved through semantic analysis, and carried into lowering.

## Example

```rux
struct Pair<T, U> {
    first: T;\
    second: U;
}
```
 
## Construction with type arguments

```rux
let p = Pair<int32, float64> { first: 1, second: 2.5 };
```

## Notes

* Generic type arguments appear in angle brackets.
* The compiler preserves generic type information in the type system and lowering layers.
* Backend code generation for generics is a separate concern from parsing and semantic tracking.
* Generics are **not** yet implemented in the backend.

!!! warning
    Generic syntax is currently supported by the frontend of the compiler.
    Backend support is incomplete and generic code may fail during lowering or code generation.
