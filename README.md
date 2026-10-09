# AKSO Projects

Projects completed as part of the **Computer Architecture and Operating Systems (AKSO)** course at the University of Warsaw, written in C and x86-64 assembly.

## Projects

### [Recursive Stack Library](rstack/)
A C library implementing stacks that can contain both integers and references to other stacks. Supports shared references, reference counting, and memory reclamation for cyclic structures.

### [Discrete Fractal Generator](discrete_fractal/)
An x86-64 assembly program that generates strings by repeatedly applying substitution rules. Uses an explicit stack, dynamic memory allocation through Linux syscalls, and buffered output to avoid storing intermediate results.

### [Multi-Precision Arithmetic](arithmetic_sequence/)
An x86-64 assembly routine for computing arithmetic sequences on multi-word integers, including support for negative indices and carry/borrow propagation across 64-bit words.
