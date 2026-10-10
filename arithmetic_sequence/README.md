# Multi-Precision Arithmetic Sequence

An x86-64 assembly function that computes a term of an arithmetic sequence using signed, multi-word integers:

`A_k = A_0 + k(A_1 - A_0)`

It supports negative indices and operands wider than 64 bits.

## Implementation

- Processes integers as little-endian arrays of 64-bit words.
- Performs multi-precision arithmetic with explicit carry and borrow propagation.
- Handles signed indices and follows the System V AMD64 calling convention.

## Build

Requires Linux x86-64, NASM and `make`.

```sh
make
```

This produces `arithmetic_sequence.o`, **not a standalone executable**. To remove it:

```sh
make clean
```

## Interface

```c
typedef struct {
    uint64_t lo;
    int64_t hi;
} int128_t;

int128_t arithmetic_sequence(uint64_t const *A0, uint64_t const *A1,
                             uint64_t *Ak, size_t n, int64_t k);
```

`A0` and `A1` each point to `n` 64-bit words representing signed integers in two's complement. The function writes the lowest `64 * n` bits of `A_k` to `Ak` and returns the next 128 bits in `int128_t`.

Link the object file with a C caller, for example:

```sh
gcc -z noexecstack -o example example.c arithmetic_sequence.o
```
