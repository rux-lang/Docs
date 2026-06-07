# Declaration Syntax

The general shape of a union is:

```rux
union Name {
    field1: Type;
    field2: Type;
}
```

## Example

```rux
union Value {
    integer: int32;
    floating: float32;
    pointer: *opaque;
}
```

## Public unions

A union may be marked `pub`.

```rux
pub union ExportedValue {
    a: uint64;
    b: uint64;
}
```

Public visibility controls whether the union is visible outside the defining scope, following the same visibility rules used by the rest of the language.

### Notes

* The parser recognizes `union` declarations as top-level items.
* Union declarations may appear at module level or inside nested modules.
* The current parser does not show a type-parameter list for unions.
