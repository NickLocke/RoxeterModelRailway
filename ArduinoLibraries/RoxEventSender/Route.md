# Route

These events are sent to allow control panels to show the route setting process happening.

## Available functions

### showRouteClear(uint8_t routeNumber)

This function will send a single ACOF event numbered 20480 plus the specific route number. The consuming module should extinguish all route set indications for the route concerned.

### showRouteSet(uint8_t routeNumber, uint8_t segmentNumber)

This function is used to give a prototypical indication of the route lights gradually growing through the route. Where a route has only a single segment, using segment A is the suggested approach.

This function will send a single ACON event numbered one of

- 20736 Segment A
- 20992 Segment B
- 21248 Segment C
- 21504 Segment D
- 21760 Segment E
- 22016 Segment F
- 22272 Segment G
- 22528 Segment H

plus the specific route number. This will allow the route indication to be built up in stages, by sending successive segment events as the setting process proceeds.