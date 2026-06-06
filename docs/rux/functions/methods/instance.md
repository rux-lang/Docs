# Instance methods

Instance methods receive `self` as their first parameter.

```rux
func Length(self) -> float64 {
    return Sqrt(self.x * self.x + self.y * self.y + self.z * self.z);
}
```

When a method is called, the compiler automatically passes the receiver as the first argument.

```rux
let len = value.Length();
```

The call above is equivalent to:

```rux
let len = Length(value);
```

That last equivalence is especially useful because it explains what method calls actually become during semantic analysis/lowering.
