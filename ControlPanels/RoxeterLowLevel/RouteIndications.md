# Route Indications (Roxeter low level)

This page provides an easy reference for use when configuring indications of route setting in CBUS and 
when investigating any problems.

| Route<br/>Number [1] | Route     | Clear [2] | Segment 1 Set [3] | Segment 2 Set [4] |
| -------------------- | --------- | --------- | ----------------- | ----------------- |
| 1                    | 411 left  | 20481     | 20737             | 20993             |
| 2                    | 411 right | 20482     | 20738             | 20994             |
| 3                    | 619 left  | 20483     | 20739             | 20995             |
| 4                    | 619 right | 20484     | 20740             | 20996             |
| 5                    | 578 - 577 | 20485     | 20741             | 20997             |
| 6                    | 579 - 577 | 20486     | 20742             | 20998             |
| 7                    | 731 - 730 | 20487     | 20743             | 20999             |
| 8                    | 732 - 730 | 20488     | 20744             | 21000             |


1 - The number of the route, same as the control switch on the panel, reading from left to right.

2 - Clears the route indication.

3 - Shows the first segment of the route as set (this can happen as soon as the route is confirmed to be free to set).

4 - Shows the second segment of the route set - for this panel, there is only one set of points per route, so it is always the remainder of the route.

The base numbers (to which the route number is added) for each indication are as follows:

- 20480 - Clear
- 20736 - Segment A
- 20992 - Segment B
- 21248 - Segment C
- 21504 - Segment D
- 21760 - Segment E
- 22016 - Segment F
- 22272 - Segment G
- 22528 - Segment H