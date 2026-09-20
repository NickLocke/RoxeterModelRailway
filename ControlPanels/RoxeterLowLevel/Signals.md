# Signals (Roxeter low level)

This page provides an easy reference for use when configuring signals in CBUS and when investigating any problems.

| Signal<br/>Number | Internal<br/>Number [1] | Red [2] | Yellow | Green |
| ----------------- | ----------------------- | ------- | ------ | ----- |
| 409               | 15                      | 15      | 271    | 527   |
| 410               | 16                      | 16      | 272    | 528   |
| 411               | 17                      | 17      | 273    | 529   |
| 576               | 19                      | 19      | 275    | 531   |
| 577               | 20                      | 20      | 276    | 532   |
| 578               | 21                      | 21      | 277    | 533   |
| 579               | 22                      | 22      | 278    | 534   |
| 580               | 23                      | 23      | 279    | 535   |
| 581               | 24                      | 24      | 280    | 536   |
| 582               | 25                      | 25      | 281    | 537   |
| 583               | 26                      | 26      | 282    | 538   |
| 617               | 31                      | 31      | 287    | 543   |
| 618               | 32                      | 32      | 288    | 544   |
| 619               | 33                      | 33      | 289    | 545   |
| 729               | 36                      | 36      | 292    | 548   |
| 730               | 37                      | 37      | 293    | 549   |
| 731               | 38                      | 38      | 294    | 550   |
| 732               | 39                      | 39      | 295    | 551   |
| 733               | 40                      | 40      | 296    | 552   |
| 734               | 41                      | 41      | 297    | 553   |
| 735               | 42                      | 42      | 298    | 554   |
| 736               | 43                      | 43      | 299    | 555   |






1 - The definitive source of these numbers is `RoxeterSignalData.cpp` in the `RoxSignals` library.

2 - These are the event number which drive signal aspects on the layout. Control panels, which only show red or green, should treat the yellow and green events in the same way.