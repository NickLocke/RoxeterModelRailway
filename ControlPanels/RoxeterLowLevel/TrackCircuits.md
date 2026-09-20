# Track Circuits (Roxeter low level)

This page provides an easy reference for use when configuring track circuits in CBUS and when investigating any problems.

| Track<br/>Circuit<br/>Number | Alternate<br/>Number | Internal<br/>Number [1] | Detection<br/>Node &<br/>Channel [2] | Flood [3] | First [4] | Second |
| ---------------------------- | -------------------- | ----------------------- | ------------------------------------ | --------- | --------- | ------ |
| 6406                         |                      | 23                      | 453 / 14                             | 8471      |           |        |
| 6407                         |                      | 24                      | 453 / 16                             | 8472      |           |        |
| 6408                         |                      | 25                      | 431 / 13                             | 8473      |           |        |
| 6409                         |                      | 26                      | 421 / 7                              | 8474      | 8730      | 8986   |
| 6410                         |                      | 27                      | 421 / 6                              | 8475      |           |        |
| 6411                         |                      | 28                      | 421 / 5                              | 8476      |           |        |
| 6412                         | 9111                 | 29                      | 421 / 13                             | 8477      |           |        |
| 6413                         | 9110                 | 30                      | 421 / 14                             | 8478      |           |        |
| 6414                         | 9109                 | 31                      | 421 / 11                             | 8479      |           |        |
| 6415                         | 9108                 | 32                      | 421 / 12                             | 8480      |           |        |
| 7202                         |                      | 39                      | 453 / 11                             | 8487      |           |        |
| 7203                         |                      | 40                      | 453 / 9                              | 8488      |           |        |
| 7204                         |                      | 41                      | 431 / 12                             | 8489      |           |        |
| 7205                         |                      | 42                      | 421 / 3                              | 8490      | 8746      | 9002   |
| 8510                         |                      | 45                      | 453 / 12                             | 8493      |           |        |
| 8511                         |                      | 46                      | 453 / 10                             | 8494      |           |        |
| 8512                         |                      | 47                      | 431 / 9                              | 8495      |           |        |
| 8513                         |                      | 48                      | 431 / 10                             | 8496      | 8752      | 9008   |
| 8514                         |                      | 49                      | 421 / 1                              | 8497      |           |        |
| 8515                         |                      | 50                      | 421 / 2                              | 8498      |           |        |
| 8516                         | 7209                 | 51                      | 421 / 15                             | 8499      |           |        |
| 8517                         | 7208                 | 52                      | 421 / 16                             | 8500      |           |        |
| 8518                         | 7207                 | 53                      | 421 / 8                              | 8501      |           |        |
| 8519                         | 7206                 | 54                      | 421 / 4                              | 8502      |           |        |
| 9104                         |                      | 62                      | 453 / 13                             | 8510      |           |        |
| 9105                         |                      | 63                      | 453 / 15                             | 8511      |           |        |
| 9106                         |                      | 64                      | 431 / 14                             | 8512      |           |        |
| 9107                         |                      | 65                      | 431 / 16                             | 8513      | 8769      | 9025   |






1 - The definitive source of these numbers is `RoxeterTrackCircuitData.cpp` in the `RoxTrackCircuits` library.

2 - The hardware modules which will raise events when the track becomes occupied or clear.

3 - For track circuits with a single route this is the event to show occupied. For track circuits with multiple routes, this is the event to show a flood indication when no route has been set through the track circtui. In both cases, an ACOF event is sent to chow the track as clear.

4 - For track circuits with more than one route through, these events selectively illuminate the appropriate track segments.