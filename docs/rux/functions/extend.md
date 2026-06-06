# Extend

The `extend` construct associates functions with an existing type.

```rux
extend Vector {
    func Length(self) -> float64 {
        return Sqrt(self.x * self.x + self.y * self.y + self.z * self.z);
    }
}
```

Functions declared inside an extend block become methods of the target type.

Methods may be instance methods, static methods, or operator methods depending on how they are declared.

Method calls use normal receiver syntax:

```rux
let len = value.Length();
```
