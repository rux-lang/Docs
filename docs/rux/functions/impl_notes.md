# Implementation Notes

This section describes how the compiler currently handles functions internally.

## Parsing

The parser recognizes:

* normal function declarations
* generic parameters
* parameter lists
* optional return types
* bodies or signatures
* `asm func`
* `extern func`
* methods inside `extend`
* operator function names

Parameters can also be marked variadic or given default values.

## Semantic analysis

The semantic analyzer:

* records function symbols
* resolves parameter and return types
* checks argument compatibility
* manages overload sets
* performs overload resolution during calls

Function overloads are grouped under the same name.

When a function is called, the analyzer selects a matching overload using argument count and assignability rules.

## Method resolution

Method lookup is based on the receiver type.

The analyzer also handles interface methods and associated function types, allowing method calls and method references to be typed correctly.
