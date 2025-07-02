# Recommendation R005: Using the `System.FastMath` library

The `System.Math` library contains numerical and arithmetic functionality. The internal implementation is based on algorithms with a higher degree of portability.
The library `System.FastMath` provides more performant implementations for a number of functions.
It is recommended to use the `System.FastMath` library for performance optimization.

Regarding the `SQRT`, `SIN`, `COS`, and `TAN` function, the `System.FastMath` provides a substantial performance improvement.

## Note

Different targets (i. e. the "1500" and "llvm" target) may behave differently in corner cases in the `System.FastMath` library. More information is found in the individual function documentation.

Back to [Overview](./01_Introduction.md)
