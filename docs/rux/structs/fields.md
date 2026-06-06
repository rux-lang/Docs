# Fields

## Field Rules

A struct field is declared as:

```rux
name: Type;
```

Example:

```rux
struct Size {
    width: uint32;
    height: uint32;
}
```

### Public fields

A field may be marked public:

```rux
struct Token {
    pub kind: uint32;
    value: char8[];
}
```

Public fields are intended to be visible outside the defining module or package according to the language’s visibility rules.

### Notes

* Field names must be identifiers.
* Field types may be any valid Rux type.
* Fields cannot currently be declared without a type.

---

## Field Access

Fields are accessed using the `.` operator.

```rux
let p = Point { x: 1.0, y: 2.0 };
let x = p.x;
```

Example:

```rux
Print(person.name);
```

Field access is a normal postfix expression and participates in later semantic checks and lowering.

## Nested Structs and Named Types

Struct fields may use other named types, including other structs.

```rux
struct Address {
    city: char8[];
    zip: uint32;
}

struct Person {
    name: char8[];
    address: Address;
}
```

In this example, `Person` contains an `Address` value as one of its fields.

Nested fields can be accessed through normal field access syntax:

```rux
let city = person.address.city;
```

The compiler resolves named field types during semantic analysis and uses the resolved types when computing struct layout.

### Notes

* Named types are stored as fields and are not flattened automatically.
* Nested structs retain their own fields and layout.
* Struct layout is computed recursively using the layouts of nested types.
* Field access can be chained through nested values.

