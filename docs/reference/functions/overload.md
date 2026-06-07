# Overloads

Rux allows multiple functions with the same name.

```rux
func Add(a: int32, b: int32) -> int32 {
    return a + b;
}

func Add(a: float64, b: float64) -> float64 {
    return a + b;
}
```

## Overload selection

The compiler chooses a candidate based on the argument types.

In practice, overload resolution prefers:

1. exact matches
2. assignable matches
3. compatible variadic forms when relevant

If the compiler cannot prove a better match, it falls back to a reasonable candidate rather than leaving the call unresolved.

## Method overloads

Methods can also be overloaded.

```rux
extend Vector {
    func Scale(self, factor: float64) -> Vector {
        return Vector { x: self.x * factor, y: self.y * factor, z: self.z * factor };
    }

    func Scale(self, factor: int32) -> Vector {
        return self.Scale(float64(factor));
    }
}
```

## Example

```rux
Add(1, 2);       // picks the int overload
Add(1.0, 2.0);   // picks the float overload
```

### Overload names in lowering

If a function name is overloaded, the compiler mangles the callee name using the parameter types so each overload gets a distinct internal symbol.

That means the source-level name stays the same, but the backend sees a unique implementation name.
