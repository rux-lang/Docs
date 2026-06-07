# Notes

## Functions are first-class at the type level

The compiler tracks function signatures as types.

That is why functions can be resolved, overloaded, lowered, and passed through the backend in a structured way.

## Methods are still functions

A method is not a separate language species.
It is a function attached to a type, with `self` handled specially by the compiler.

## Overload names may be mangled internally

Source code uses the same name for overloaded functions.
The backend uses a mangled form so each overload can be emitted as a distinct symbol.

## Variadic arguments become a slice-like value

Trailing variadic arguments are collected into a slice representation during lowering.

## Default arguments are inserted during lowering

If a call omits trailing parameters with defaults, the compiler fills them in before reaching the lower-level representation.
