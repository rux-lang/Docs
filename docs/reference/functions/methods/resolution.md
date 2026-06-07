# Method resolution

Method lookup is performed using the receiver type.

For pointer receivers, the pointer type is used directly.

For value receivers, the compiler may insert an implicit address-of operation when necessary, allowing methods with pointer-based `self` parameters to be invoked on values.
