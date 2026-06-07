# Static methods

Methods that do not use `self` behave like associated functions.

```rux
extend Vector {
    func New(x: float64, y: float64, z: float64) -> Vector {
        return Vector { x: x, y: y, z: z };
    }
}
```

These are called with `::`:

```rux
let v = Vector::New(1.0, 2.0, 3.0);
```
