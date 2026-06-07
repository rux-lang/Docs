# Common Errors

## Missing parameter type

```rux
func Bad(x) {
}
```

## Wrong number of arguments

```rux
Add(1);
```

## Calling an immutable-typed or unresolved overload incorrectly

```rux
Add("hello", "world");
```

## Invalid reassignment inside the function body

```rux
func Test() {
    let x = 1;
    x = 2;
}
```

## Invalid variadic usage

```rux
func Log(values: int32...) {
}

Log(1, 2, ...);
```

## Missing body when a body is required

```rux
func Compute(x: int32) -> int32
```

Depending on context, the compiler expects either a body or a trailing semicolon.
