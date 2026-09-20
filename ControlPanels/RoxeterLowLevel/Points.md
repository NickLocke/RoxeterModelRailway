# Points (Roxeter low level)

This page provides an easy reference for use when configuring points in CBUS and when investigating any problems.

| Points<br/>Number | Internal<br/>Number [1] | Node &<br/>Channel [2] | Move [3] | Normal [4] | Reverse | Locked | O O C |
| ----------------- | ----------------------- | ---------------------- | -------- | ---------- | ------- | ------ | ----- |
| 2601              | 1                       | 432 / 1                | 4097     | 4353       | 4609    | 4865   | 5121  |
| 2602              | 2                       | 432 / 2                | 4098     | 4354       | 4610    | 4866   | 5122  |
| 2603              | 3                       | 432 / 3                | 4099     | 4355       | 4611    | 4867   | 5123  |
| 2604              | 4                       | 432 / 4                | 4100     | 4356       | 4612    | 4868   | 5124  |


1 - The definitive source of these numbers is `RoxeterPointsData.cpp` in the `RoxPoints` library.

2 - the hardware module to which the points are connected. Drives the format of detection events as described [here](/CBUSModules/EventCribSheet.md). In summary:

- Detected normal = Channel number + 100.
- Detected reverse = Channel number + 200.

3 - This event is sent to instruct the points to move. ACOF is for Normal and ACON is for Reverse.

4 - Events from here onwards are for indications so should be taught to the display modules.