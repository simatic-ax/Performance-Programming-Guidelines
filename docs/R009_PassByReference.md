## Recommendation R006: Pass structured parameters as reference
SIMATIC AX and the SIMATIC runtime system offer different mechanisms for passing parameters.
_Pass by value_ means that the formal parameter is a copy of the argument value provided when calling the POU.
_Pass by reference_ means that the formal parameter is a reference to the provided argument.

With some exceptions regarding `ARRAY` and `STRING` parameters, parameter passing in SIMATIC AX follows these general rules:

| Section      | Parameter passing   |
|--------------|---------------------|
| `VAR_INPUT`  |  _Pass by value_    |
| `VAR_OUTPUT` |  _Pass by value_    |
| `VAR_IN_OUT` | _Pass by reference_ |

Regarding performance, _pass by reference_ has benefits for larger groups of formal parameters.
The performance advantage increases as the count of elements increases.

Therefore, it is recommended to group formal parameters into structures and pass these via reference (i. e. in the `VAR_IN_OUT` section of a `FUNCTION_BLOCK`).

### Example
```iecst
TYPE
    dynamicInfo : STRUCT
        posX : LREAL;
        posY : LREAL;
        posZ : LREAL;
        posA : LREAL;
        velX : LREAL;
        velY : LREAL;
        velZ : LREAL;
        velA : LREAL;
        accX : LREAL;
        accY : LREAL;
        accZ : LREAL;
        accA : LREAL;
        jerkX : LREAL;
        jerkY : LREAL;
        jerkZ : LREAL;
        jerkA : LREAL;
    END_STRUCT;
END_TYPE

FUNCTION_BLOCK
VAR_IN_OUT
    dynamics : dynamicInfo
END_VAR
    .
    .
    .
END_FUNCTION_BLOCK
```

### Note
Using this method, the original data may be modified.
