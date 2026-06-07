# Unions

A union is a user-defined type where all fields share the same storage.

Unlike a struct, a union does not store every field at once. Instead, the same memory can be interpreted as one of several different types.

Unions are commonly used for low-level programming, compact data representations, interop, and runtime or compiler internals.

---

## Example

```rux
union Value {
    i: int32;
    f: float32;
    ptr: *opaque;
}
```

In this example, `i`, `f`, and `ptr` all refer to the same memory.

---

## Summary

A union declaration consists of:

* an optional `pub` modifier
* a name
* one or more fields
* a type for each field

```rux
pub union TokenData {
    kind: uint32;
    payload: uint64;
}
```

---

## Union vs Struct

A struct stores every field separately.

```rux
struct Point {
    x: float32;
    y: float32;
}
```

A union shares one storage area between all fields.

```rux
union Number {
    integer: int32;
    floating: float32;
}
```

Use a struct when all fields exist together.

Use a union when the fields represent alternative interpretations of the same data.

---

## Good Practice

Use unions when only one field is intended to be meaningful at a time.

```rux
union Number {
    i: int32;
    f: float32;
}
```

---

## Bad Practice

Do not use a union for ordinary records.

```rux
union PersonLike {
    name: char8[];
    age: uint32;
    height: float32;
}
```

If all fields are expected to be valid together, use a struct instead.
