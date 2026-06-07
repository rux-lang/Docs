# Fields

Each union field is declared as:

```rux
name: Type;
```

Example:

```rux
union FlagValue {
    bits: uint32;
    raw: uint32;
}
```

## Field rules

* Field names must be identifiers.
* Each field must have a type.
* Each field ends with a semicolon.
* Field order is preserved in the declaration.

## Good practice

Keep field names descriptive of the active interpretation.

```rux
union PacketData {
    headerBytes: uint8[];
    checksum: uint32;
}
```

## Bad practice

Do not use vague field names like `x`, `y`, `z` unless the meaning is actually obvious.

```rux
union BadNaming {
    x: int32;
    y: float32;
    z: *opaque;
}
```

A reader should be able to tell what each alternative means without decoding the whole codebase.

## Field Type Rules

Fields may use any valid Rux type.

```rux
union Storage {
    byte: uint8;
    text: char8[];
    ptr: *opaque;
}
```

### Good practice

Choose field types that represent meaningful alternative interpretations of the same storage.

```rux
union Value {
    flag: bool8;
    code: uint8;
}
```

### Bad practice

Do not hide huge or unrelated payloads behind a union unless that is really the intended model.

```rux
union EverythingBagel {
    number: uint64;
    name: char8[];
    nested: SomeHugeStruct;
}
```

That kind of design can become unclear fast if the active alternative is not tracked carefully.
