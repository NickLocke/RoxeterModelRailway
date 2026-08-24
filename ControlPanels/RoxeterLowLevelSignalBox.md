# Roxeter Low Level Signal Box
This panel controls the low level loops at the right side of the layout, under the Roxeter terminus. The signal box exists because the two loops each have a branch from them to allow for the storage of additional trains.

## Operation
The panel is representative of a One Control Switch (OCS) prototype. In summary, that style of panel allows for an entire route to be set by operation of a single switch, rather than in an Individual Function Switch (IFS) panel where there are separate switches for each signal, point etc. 

## Construction
The panel faces were laser engraved/cut from acrylic, whilst the casing was laser cut from MDF.

TODO: Add more here

## Technical Details
There are two CBUS modules located within the panel:

- CANRGB - node 6010
- CANMIO - node 6020

In addition, the interlocking is handled by an Arduino-based module which has been named CANOCS:

- CANOCS - node 3150
