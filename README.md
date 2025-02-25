# False Sharing

## Description

This project compares the performance of two standard data structures: **std::vector<int>** and **std::list<int>**, focusing on the time taken to perform **10,000 insertions in the middle** of each. The program demonstrates the performance differences when repeatedly inserting new elements in the middle of both containers and explores why **std::vector** may outperform **std::list**, despite requiring element shifts. The project also includes an experiment with a **pre-allocated vector** to assess if it improves performance.

### Expected Outcome

- **std::vector** might outperform **std::list** in this test because although vector insertion requires shifting elements, the overhead of pointer manipulation in a list (especially when there are many nodes) could be more expensive.
- A **pre-allocated vector** could improve insertion performance by reducing the number of reallocations required as the vector grows.

## Example Code Workflow

The program will perform the following:

1. **Sequential Execution**:
   - Measure and compare the time taken to perform **10,000 insertions in the middle** of both `std::vector<int>` and `std::list<int>`.
   
2. **Pre-allocated Vector**:
   - Perform insertions using a pre-allocated vector with an initial capacity large enough to avoid reallocations.
   
3. **Performance Comparison**:
   - Output the execution time for each insertion approach.

Example output:

```
Pre-allocated vector insertions took: 1.7187 ms
Vector insertions took: 2.1003 ms
List insertions took: 73.148 ms
```

## How to Compile and Run the Code

1. **Clone the repository:**
   If you haven't cloned the repository yet, do so by running:
   ```bash
   git clone https://github.com/LyudmilaKostanyan/vector-vs-list-insert.git
   cd False-Sharing
   ```

2. **Build the project:**
   Once you're in the project directory, compile the code with:
   ```bash
   cmake -S . -B build
   cmake --build build --config Release
   ```

3. **Run the compiled executable:**
   After compiling, you can run the program:
   ```bash
   cd build
   ./main
   ```

