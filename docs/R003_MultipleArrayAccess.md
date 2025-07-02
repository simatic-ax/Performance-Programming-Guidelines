# Recommendation R003: Avoid multiple acces to same array index

When accessing an array index with the bracket syntax, internal checks for the validity of the array boundaries are performed. When access to the same index of an array is required (e. g. to access underlying nested elements), use a temporary variable as a cache. Write back the changes to the array (if applicable) once, after the operation is finished.

```iecst
VAR
    statArray : ARRAY[0..7] OF Point6D;
END_VAR
VAR_TEMP
    tempData : Point6D;
    iterator : DINT;
END_VAR

FOR iterator := 0 TO 7 DO
    tempData := statArray[iterator];
    tempData.x := value * iterator;
    tempData.y := value * iterator;
    tempData.z := value * iterator;
    tempData.a := value * iterator;
    tempData.b := value * iterator;
    tempData.c := value * iterator;
    statArray[iterator] := tempData;
END_FOR;
```

Back to [Overview](./01_Introduction.md)
