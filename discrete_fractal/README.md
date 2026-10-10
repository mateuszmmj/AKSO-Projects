
# Discrete Fractal Generator

An x86-64 assembly program that generates strings through iterative ASCII symbol substitution.

The first input line is the initial string. Each following line defines a replacement rule: its first character is the symbol to replace, and the remaining characters are its replacement (possibly empty). All substitutions are applied simultaneously in each iteration.

## Implementation

- Uses Linux system calls directly for input/output and memory management (`mmap`, `mremap`, `munmap`).
- Expands rules with an explicit stack rather than recursion or storing intermediate strings.
- Uses buffered output and optimizations for disappearing symbols and substitution cycles.

## Build

Requires Linux x86-64, NASM, GNU `ld`, and `make`.

```sh
make
```

To remove generated files:

```sh
make clean
```

## Usage

```sh
./discrete_fractal n < input.txt
```

`n` is the number of iterations. For example, given `input.txt`:

```text
A
AAB
BA
```

Running:

```sh
./discrete_fractal 4 < input.txt
```

Produces:

```text
ABAABABA
```

The program prints the result followed by a newline. Exit status is `0` on success and `1` on error.
