# Programming Language

This repository is a set of ideas, which will ultimately become a more thorough specification for a currently unnamed programming language which I plan on implementing when I have the time at some point in the future. The high level idea for the language is to have F# like syntax with C style memory management but with better support for polymorphism and some basic abstractions over C's unsafe features.

## Sample Programs

### Hello, World!

```
let main () =
    io::display "Hello, World\n"
```

### Recursive Factorial

```
let factorial (n : Int) -> Int =
    if n = 0 then
        1
    else
        n * factorial (n - 1)

let main () =
    io::display (factorial (5))
```

### Linked List and Related Functions

```
type 'a LinkedList =
    | Nil
    | Cons : ('a, &'a LinkedList)

// Unliked F#/OCaml, no annotation for recursive functions is required as shadowing is not a feature.
let sum (list : &'a LinkedList) -> 'a =
    match list
    | Nil -> 
        0
    | Cons (x, xs) ->
        x + sum (xs)
```

### Loops

```
let main () =
    let sum = 0

    // Specifying inclusivity with <, = and > is required.
    for i in 0<..=10 run
        sum := sum + i
    
    io::display sum
```

```
let main () =
    let sum = 0

    let i = 1

    while i <= 10 run
        sum := sum + i

    io::display sum
```

### Custom Type with Memory Allocations

```
type Point = {
    x : Float
    y : Float
}

let add(a : Point, b : Point) -> Point =
    Point {
        x = a.x + b.x
        y = a.y + b.y
    }

let main () =
    let p : &Point = mem::alloc()
    p.x = 1
    p.y = 2

    let q = Point {
        x = 2
        y = 3
    }

    let r = (*p) + q
    
    mem::dealloc(p)
```

These overloading operations will be from the `stdlib` modules:

```
module op
    sig (+) add(x : 'a, y : 'b) -> 'c

module mem
    sig alloc() -> &'a
    sig free(to_free : &'a)
```

## Contents

- [Composite Types](composite-types.md)
- [Memory Management](memory-management.md)
- [Polymorphism](polymorphism.md)
- [Dot Notation](dot-notation.md)
- [Functions and Modules](functions-and-modules.md)
