# Examples

## Simple union

```rux
union Number {
    integer: int32;
    floating: float32;
}
```

## Union with pointers

```rux
union Data {
    ptr: *opaque;
    id: uint64;
}
```

## Public union

```rux
pub union Payload {
    bytes: uint8[];
    count: uint32;
}
```

## Compact enum-like storage

```rux
union TokenData {
    kind: uint32;
    payload: uint64;
}
```

This is a reasonable union shape when the code needs one of several interpretations but does not want a larger record type.
