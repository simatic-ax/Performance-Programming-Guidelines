# Recommendation R007: Avoid multiple access to Technology Objects (TO)

When accessing data from Motion Control Technology Objects (TO) it is recommended to read the data once and store it in temporary or static memory for repeated access. Access to Technology Object data is significantly slower than accessing temporary or static memory in a POU.

This recommendation applies both to the access via the reference to a Technology Object as well as calling the auxiliary functions like `Get<TO>Status`, `<Get<TO>Warnings` and `Get<TO>Warnings`.

```iecst
USING Siemens.Simatic.S71500.MotionControl.Native;
VAR_INPUT
    posAx : REF_TO TO_PositioningAxis;
END_VAR
VAR_OUTPUT
    posBasedCalculation : LREAL;
END_VAR
VAR_TEMP
    tempPosition : LREAL;
END_VAR


tempPos := posAx^.ActualPosition;

IF tempPos > LREAL#0.0 THEN
    posBasedCalculation := tempPos * 123.456;
ELSE
    posBasedCalculation := -1.0;
END_IF;
```

It is also recommended to read only the Technology Object data which is required in the user program.

Avoid cyclic evaluation of static configuration data (e. g. the leadscrew pitch of an axis).

Do not read Technology Object data in a higher frequency than the values are actually updated (i. e. MC_Servo cylce).

## Note

Temporary variables cannot be monitored or modified with the SIMATIC AX online tools.
