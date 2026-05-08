# RV-Sparse: CSR Matrix-Vector Multiplier

The code implements the `sparse_multiply` function, which scans a row-major matrix A and performs a CSR matrix-vector multiplication, writing the result into a caller-provided output buffer.

## CSR Format Explanation

The implementation uses a two-phase approach:

1. **Scanning:** The dense matrix is scanned to identify non-zero elements and populate the CSR buffers.
2. **Multiplication:** The dot product is performed using the compressed indices to compute y = A $\times$ x.

## Design Constraints

The solution adheres to the following constraints:

- **Zero Dynamic Memory Allocation:** No memory is allocated at runtime; all buffers are pre-allocated by the caller.
- **Direct Output:** The result is written directly into the caller-provided output buffer.

## Compilation and Usage

The implementation is verified using the provided test harness:

```
gcc -lm -o run challenge.c
./run
```
