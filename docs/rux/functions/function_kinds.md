# Function Kinds

## Regular functions

Regular functions are declared with `func`.

```rux
func Add(a: int32, b: int32) -> int32 {
    return a + b;
}
```

These are the standard callable declarations used for ordinary code.

## Signature-only functions

A function may be declared without a body.

```rux
func PrintLine(text: char8[]);
```

This form is useful for declarations that are defined elsewhere or only needed as a signature.

## Operator functions

Functions may use operator names.

```rux
func +(a: Vector, b: Vector) -> Vector {
    return Vector { x: a.x + b.x, y: a.y + b.y, z: a.z + b.z };
}
```

Operator functions participate in overload resolution like normal named functions.

## Methods

Methods are functions declared inside an `extend` block.

```rux
extend Vector {
    func Length(self) -> float64 {
        return Sqrt(self.x * self.x + self.y * self.y + self.z * self.z);
    }
}
```

Methods are called using the `.` syntax on a value, and the compiler resolves the correct method based on the receiver type.

## External functions

External functions are declared with `extern`.

```rux
extern func CreateFileA(name: char8[], access: uint32) -> *opaque;
```

These declarations describe symbols that are provided by a DLL, system library, or another external object file.

## Assembly functions

A function may be marked `asm`.

```rux
asm func FastAdd(a: int32, b: int32) -> int32;
```

Assembly functions are part of the function system, but their implementation is expected to come from assembly rather than normal Rux source.
