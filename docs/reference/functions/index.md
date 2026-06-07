# Functions

Functions are callable declarations that group executable behavior behind a name.

They are one of the primary building blocks of a Rux program and are used to implement reusable logic, APIs, methods, operators, foreign-function interfaces, and low-level runtime functionality.

A function may be:

* a normal function with a body
* a signature-only declaration
* an operator function
* a method declared inside an `extend` block
* an `extern` declaration bound to an external symbol
* an `asm` function backed by hand-written assembly

Functions may also be overloaded, variadic, generic, and optionally public.

---

## Summary

```rux
func Add(a: int32, b: int32) -> int32 {
    return a + b;
}

func Add(a: float64, b: float64) -> float64 {
    return a + b;
}

func PrintLine(text: char8[]);

extern func GetCurrentProcessId() -> uint32;
```

A function declaration may include:

* an optional `pub` modifier
* an optional `asm` prefix
* a name
* optional type parameters
* a parameter list
* an optional return type
* either a body or a trailing semicolon

---

## What a Function Means

A function represents a callable unit of behavior.

Functions accept zero or more arguments, optionally produce a return value, and may perform arbitrary computation.

Unlike variables or types, functions describe actions rather than stored data.

```rux
func Square(value: int32) -> int32 {
    return value * value;
}
```

The function above accepts an integer and returns its square.

---

## Function Kinds

Rux supports several categories of functions.

### Regular functions

```rux
func Add(a: int32, b: int32) -> int32 {
    return a + b;
}
```

### Signature-only functions

```rux
func PrintLine(text: char8[]);
```

### Methods

```rux
extend Vector {
    func Length(self) -> float64 {
        return Sqrt(self.x * self.x + self.y * self.y);
    }
}
```

### Operator functions

```rux
func +(a: Vector, b: Vector) -> Vector {
    return Vector {
        x: a.x + b.x,
        y: a.y + b.y,
    };
}
```

### External functions

```rux
extern func MessageBoxA(
    text: char8[],
    caption: char8[]
) -> int32;
```

### Assembly functions

```rux
asm func FastAdd(a: int32, b: int32) -> int32;
```

---

## Parameters and Return Values

Functions communicate through parameters and return values.

```rux
func Clamp(
    value: int32,
    min: int32,
    max: int32
) -> int32 {
    // ...
}
```

Parameter types participate in:

* type checking
* overload resolution
* lowering
* code generation

Return types describe the result produced by the function.

```rux
func IsValid(value: int32) -> bool {
    return value > 0;
}
```

---

## Calling Functions

Functions are invoked using parentheses.

```rux
Add(1, 2);
```

Method calls use receiver syntax.

```rux
value.Length();
```

The compiler verifies argument count, argument types, variadic usage, and overload resolution before a call is considered valid.

---

## Related Topics

The following pages provide detailed information about specific function features:

* Declaration Syntax
* Parameters
* Return Types
* Calling Functions
* Variadic Functions
* Default Parameters
* Type Parameters
* Overloads
* Methods
* External Functions
* Calling Conventions
* Common Errors
* Implementation Notes
