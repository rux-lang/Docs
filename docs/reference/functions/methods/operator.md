# Operator Methods

Functions may implement operators for a type.

```rux
extend Vector {
    func +(self, other: Vector) -> Vector {
        return Vector { x: self.x + other.x, y: self.y + other.y, z: self.z + other.z };
    }
}
```

This lets values of the type participate in operator syntax.

```rux
let sum = a + b;
```

Operator methods are still functions, so they follow the same type and overload rules as regular methods.
