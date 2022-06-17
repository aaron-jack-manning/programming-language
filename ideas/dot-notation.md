# Dot Notation

Dot notation as used in `koka` will be implemented, such that a function can be called by providing the arguments in parenthesis to the right, or by using dot notation on a valid first argument to the function. For example:

Given a function `f (x : int)`, this function can be called on the variable `a` as `a.f()` or `f(a)`, and for functions with multiple arguments this applies to the first, for example: `g (x : int, y : int)` can be called as `a.g(4)` or `g(a, 4)`.



