# Examples

## Simple function

```rux
func Add(a: int32, b: int32) -> int32 {
    return a + b;
}
```

## Function with default parameter

```rux
func Greet(name: char8[] = "world") {
    Print("Hello, ");
    Print(name);
}
```

## Generic function

```rux
func Identity<T>(value: T) -> T {
    return value;
}
```

## Variadic function

```rux
func Sum(values: int32...) -> int32 {
    var total = 0;
    for value in values {
        total += value;
    }
    return total;
}
```

## Method

```rux
extend Point {
    func Length(self) -> float64 {
        return Sqrt(self.x * self.x + self.y * self.y);
    }
}
```

## Operator function

```rux
extend Point {
    func +(self, other: Point) -> Point {
        return Point { x: self.x + other.x, y: self.y + other.y };
    }
}
```

## External function

```rux
@[Import(lib: "Kernel32.dll")]
extern func GetCurrentProcessId() -> uint32;
```
