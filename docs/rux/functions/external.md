# External Functions

External functions describe symbols that live outside Rux source.

```rux
extern func MessageBoxA(text: char8[], caption: char8[]) -> int32;
```

## External blocks

Rux also supports grouped external declarations:

```rux
extern {
    func CreateFileA(...);
    func WriteFile(...);
    handle: *opaque;
}
```

## Calling conventions

Functions may use a calling convention.

```rux
@[Call(.Win64)]
extern func GetTickCount64() -> uint64;
```

Calling conventions matter when interfacing with foreign code, especially on Windows.

They affect how arguments are passed and how the backend emits calls.

## Attributes

External functions may be decorated with attributes such as:

* `@[Import(lib: "...")]`
* `@[Call(.Win64)]`
* `@[Target("Windows")]`

These control import libraries, calling conventions, and target-specific availability.

## Example

```rux
@[Import(lib: "Kernel32.dll")]
extern func GetCurrentProcessId() -> uint32;
```

## Notes

* External declarations usually do not have bodies.
* They are intended for FFI and platform integration.
* The compiler uses the declaration to generate the correct link and call information.
