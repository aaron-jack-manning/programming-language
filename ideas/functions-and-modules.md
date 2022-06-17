# Functions and Modules

Code on the top level may be any one of the following:
1. A function
2. An immutable variable (which can be the result of a function call, bound directly).
3. A module

There will be no notion of classes, nor methods on a type.

All three of the above may appear within a module, only a function or variable may appear in a function.

Variables at the top level of a function which are not compile time constants will be evaluated lazily (upon first use).
