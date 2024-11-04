# PrevInRange
Efficient Data Structure for Range Queries in Sequence X

This project implements an efficient data structure for handling specific queries on a dynamically growing sequence of integers. The goal is to optimize the time complexity for various operations on the sequence, including initialization, range queries, and appending new elements.

## Project Overview

The data structure provides the following functions:

- **`void init(const vector<int>& x)`**  
  Initializes the sequence with the provided values. It ensures optimal setup with a time complexity of \(O(|X| \log z)\), where \(z\) is the range of integer values.

- **`int prevInRange(int i, int lo, int hi)`**  
  Returns the largest index `j` such that \(0 \le j \le i\) and \(x_j \in [lo, hi]\). If no such `j` exists, the function returns -1. The expected time complexity for this function is \(O(\log z)\).

- **`void pushBack(int v)`**  
  Appends a new element to the sequence. The amortized cost of this function is also expected to be \(O(\log z)\).

- **`void done()`**  
  Releases all memory used by the data structure, ensuring no memory leaks.

## Requirements and Compilation

The code requires a C++ compiler and uses `g++` for compilation. To compile the project:

```bash
g++ @opcjeCpp main.cpp prev.cpp -o main.e
```

## Memory Leak Checks

The solution will be tested with `valgrind` to ensure memory efficiency and avoid leaks. You can verify this by running:

```bash
valgrind --tool=memcheck --leak-check=yes ./main.e
```

## Performance and Constraints

- **Time Complexity Requirements**: To achieve the maximum score, `prevInRange` and `pushBack` must have an amortized time complexity of \(O(\log z)\), and `init` should not exceed \(O(|X| \log z)\).
- **Memory Efficiency**: The project must pass `valgrind` tests to confirm no memory leaks occur.
