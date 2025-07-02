# Recommendation R010: Order `IF`/`ELSIF` instructions by expectation

It is recommended to order `IF`/`ELSIF` statements by decreasing likelihood.
The condition with the highest expectation of being `TRUE` should be placed at the top.
Ordering the conditions in this way reduces the amount of occurences where less likley conditions need to be check, thereby improving the runtime performance.

## Example

```iecst
IF myLikelyCondition THEN
    ; // react to likely event
ELSIF myUnlikelyCondition THEN
    ; // react to unlikely event - only checked if myLikelyCondition was FALSE
END_IF;
```
