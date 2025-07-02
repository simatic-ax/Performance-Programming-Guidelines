# Recommendation R001: Use temporary variables

Use temporary variables (`VAR_TEMP`) as intermediate memory in the current cylce if the calculation results are not required over multiple cycles. The access time for temporary variables is shorter than for static variables.

## Note

Temporary variables cannot be monitored or modified with the SIMATIC AX online tools.

Temporary variables are initialized by the system in every call, therefore big data structures consume more performance than static variables.

Back to [Overview](./01_Introduction.md)
