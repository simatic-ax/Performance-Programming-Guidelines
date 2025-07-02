# Recommendation R002: Dereference pass-by-reference to temporary variable

Passing structured parameters as reference provides performance benefits.
When accessing data that has been passed by reference, it is recommended to dereference the structure once into a temporary variable. This is especially advantageous when elements of the referenced structure are accessed multiple times in the current scope.

```iecst
VAR_INPUT
    data : REF_TO DWORD;
END_VAR
VAR_TEMP
    tempData : DWORD;
END_VAR
VAR
    x0, x1, x2, x3, x4, x5, x6, x7 : BOOL;
    x8, x9, x10, x11, x12, x13, x14, x15 : BOOL;
    x16, x17, x18, x19, x20, x21, x22, x23 : BOOL;
    x24, x25, x26, x27, x28, x29, x30, x31 : BOOL;
END_VAR 
tempData := data^;  
x0 := tempData.%X0;
x1 := tempData.%X1;
x2 := tempData.%X2;
x3 := tempData.%X3;
x4 := tempData.%X4;
x5 := tempData.%X5;
.
.
.
```

## Note

Temporary variables cannot be monitored or modified with the SIMATIC AX online tools.

Temporary variables are initialized by the system in every call, therefore big data structures consume more performance than static variables.
