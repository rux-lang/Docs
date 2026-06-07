# Common Errors

## Missing field type

```rux
union Bad {
    value;
}
```

## Missing semicolon after a field

```rux
union Bad {
    value: int32
}
```

## Duplicate field names

```rux
union Bad {
    value: int32;
    value: float32;
}
```

## Unknown field type

```rux
union Bad {
    value: UnknownType;
}
```

## Bad practice: treating a union like a struct

```rux
union BadModel {
    name: char8[];
    age: uint32;
}
```

If both values are always needed together, this should be a struct instead.
