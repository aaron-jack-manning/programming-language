# Memory Management

Memory management will be reminiscent of C, without the ability to cast between pointers arbitrarily.

An overloaded function `alloc` will be used for memory allocations, with an overloaded function `dealloc` handling deallocation. These will be implemented automatically but optional custom implementations will be allowed for easy manual reference counting.

There will be no notion of pointer arithmetic, and references can only be constructed from `alloc` or by taking a reference to an existing variable by `&`.
