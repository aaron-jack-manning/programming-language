# Programming Language

This repository is a set of ideas, which will ultimately become a more thorough specification for a currently unnamed programming language which I plan on implementing when I have the time at some point in the future. The high level idea for the language is to have F# like syntax with C style memory management but with better support for polymorphism and some basic abstractions over C's unsafe features.

## TL:DR;

- Statically Typed: Yes
- Garbage Collected: No
- Whitespace Significant: Yes
- Type Inference: Yes (under certain circumstances)
- Classes and Objects: No
- Produces Standalone Executables: Yes

## Sample Programs

### Hello, World!

![hello-world](samples/hello-world.txt)

### Recursive Factorial

![recursive-factorial](samples/recursive-factorial.txt)

### Linked List

![linked-list](samples/linked-list.md)

### For Loop

![for-loop](samples/for-loop.md)

### While Loop

![while-loop](samples/while-loop.md)

### Memory Allocation

![memory-allocation](samples/memory-allocation.txt)

### Interfaces in Stdlib

![interfaces-in-stdlib](samples/interfaces-in-stdlib.txt)

## Detailed Notes on Specific Things

- [Composite Types](details/composite-types.md)
- [Memory Management](details/memory-management.md)
- [Polymorphism](details/polymorphism.md)
- [Dot Notation](details/dot-notation.md)
- [Functions and Modules](details/functions-and-modules.md)
