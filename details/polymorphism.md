# Polymorphism

The approach to polymorphism is best explained with an example.

To create a function which can be overloaded one would declare an interface for the function as follows:

```
sig do_something (x : 'a) -> 'a
```

and then the above can be implemented with any combination of the generic types, for example:

```
let do_something (x : int) -> int =
    ...

let do_something (x : float) -> float =
    ...
```

Then any function which calls `do_something` is automatically overloaded to accept the appropriate types:

```
let do_something_else (x : 'a) -> 'a =
    do_something (x) + do_something (x)
```

If for example `do_something` has an implementation for a type which cannot be added, then the restrictions on `do_something_else` are simply tighter than on `do_something`. Hence, a generic type `'a` is able to be any type in the intersection of the sets of available types for each overloaded function call.

It is important to note that a function which implements an interface must specify all concrete types.

The above will also be how operator overloads are handled. For example, the implementation of `+` will be tied to an interface:

```
sig sum (x : 'a, y : 'a) -> 'a
```

similarly for `*`, `/`, `-`, `=`, `<>`, etc.

Scoping rules around modules and implementing interfaces from other modules as well as namespacing interfaces across modules needs to be worked out. I think an overloaded function should be called at the interface, and implementations within scope will be considered.

If polymorphic output type needs to be disambiguated `<Type>` will be placed after the function call.
