# Recursive Stack Library

A C shared library implementing stacks whose elements can be unsigned 64-bit integers or references to other stacks. Nested stacks are shared rather than copied, and references may form cycles.

## Implementation

- Uses reference counting to manage shared stacks.
- Supports recursive stack queries while accounting for cyclic references.
- Reads and writes stack values as decimal numbers in text files, with input validation and cycle detection during writing.
- Reports failures through return values and `errno`.

## Build

Requires Linux, GCC with GNU C23 support, and `make`.

```sh
make
```

This produces `librstack.so`. To remove generated files:

```sh
make clean
```

## Interface

The public API is declared in `rstack.h`:

- `rstack_new`, `rstack_delete` — create and release stacks.
- `rstack_push_value`, `rstack_push_rstack`, `rstack_pop` — modify stack contents.
- `rstack_empty`, `rstack_front` — inspect nested stacks recursively.
- `rstack_read`, `rstack_write` — load values from, or save them to, text files.

To link a C program against the library (with the executable and library in the same directory):

```sh
gcc -o example example.c -L. -lrstack -Wl,-rpath,'$ORIGIN'
```
