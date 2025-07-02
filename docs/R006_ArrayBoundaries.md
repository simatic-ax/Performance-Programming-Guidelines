# Recommendation R006: Passing arrays as formal parameters

If an array needs to be passed as a formal parameter, there is an performance impact with regard to the _size specification_ of the array.
The concrete size and limits of an array of unspecified size (`ARRAY[*]`) need to be evaluated with the system functions `UPPER_BOUND` and `LOWER_BOUND`.
This creates additional computational demand. Therefore, arrays of specified size (e. g. `ARRAY[0..63]`) are the more performant solution.

## Note

Passing `ARRAY[*]` allows for the implementation of more generalized functionality. The decision on whether to use a specified or unspecified size needs to be taken depending on the concrete circumstances.
