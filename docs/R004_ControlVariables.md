# Recommendation R004: Declaring control variables as DINT

It is recommended to use the data type `DINT` for control variables used in loops, iterations, and array access.
There is a slight performance advantage as the least amount of (implicit) type conversion occur when using `DINT`.

## Note

The effect of this recommendation is small.
