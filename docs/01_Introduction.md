# Preface

SIMATIC AX is an engineering system for SIMATIC controllers.
It offers an environment to program a PLC using Structured Text (ST). The ST compiler (STC) converts the user program into a binary which can be executed by the SIMATIC runtime.

When programming a PLC system, the achievable runtime performance of the user program is of high importance.

SIMATIC AX offers many programming features in combination with SIMATIC, which are not available in TIA Portal (e. g. object-oriented programming) and uses a different data structure.
Therefore, comparing the (expected) runtime performance of applications from TIA Portal and SIMATIC AX is not straightforward.

## Objective of the guideline

This guideline provides tips and suggestions regarding the programming in SIMATIC AX with a focus on performance impacts.

## Recommendations

1. [R001_Temporary Variables](R001_TempVariables.md)
2. [R002_Dereferencing](R002_Dereferencing.md)
3. [R003_Repeated Array Access](R003_MultipleArrayAccess.md)
4. [R004_Control variables](R004_ControlVariables.md)
5. [R005_FastMath library](R005_FastMath.md)
6. [R006_Array boundaries](R006_ArrayBoundaries.md)
7. [R007_Accessing Technology Objects](R007_AccessTO.md)
8. [R008_Limit string lenght](R008_LimitStringLength.md)
9. [R009_Pass by reference](R009_PassByReference.md)
10. [R010_If-else expectation](R010_IfElseExpectation.md)
