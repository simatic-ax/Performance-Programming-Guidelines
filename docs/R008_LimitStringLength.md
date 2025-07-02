# Recommendation R008: Specify string lengths

String data types (`STRING` and `WSTRING`) can be declared with an optional maximum capacity. The limit is `254` for `STRING` and `16328` for `WSTRING`.

If strings are passed as formal parameters via the `VAR_INPUT` and `VAR_OUTPUT` sections of a `FUNCTION_BLOCK` they are _passed by value_.
In this case it is recommended to specify the required string length via a symbolic constant.

## Example

```iecst
VAR CONSTANT
    MSG_LENGTH : DINT := DINT#300;
END_VAR
    
VAR_INPUT
    statusMessage : WSTRING[MSG_LENGTH];
END_VAR
```

## Note

The usage of string variables with appropriate size limitation also reduces the memory allocated by the system.

Back to [Overview](./01_Introduction.md)
