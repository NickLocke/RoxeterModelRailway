# Roxeter Low Level Signal Box

This panel controls the low level loops at the right side of the layout, under the Roxeter terminus. The signal box exists because the two loops each have a branch from them to allow for the storage of additional trains.

## Operation

The panel is representative of a One Control Switch (OCS) prototype. In summary, that style of panel allows for an entire route to be set by operation of a single switch, rather than in an Individual Function Switch (IFS) panel where there are separate switches for each signal, point etc. Prototype documentation of exactly how an OCS panel functions is pretty scarce. In this case, operation has been implemented as follows.

The normal position for each switch is turned fully to the left. In that position, the route is idle and the leftmost indication will be illuminated in white.

When a route is to be set, the switch will be moved to the centre position. That will cause the leftmost indication to extinguish. The interlocking will then check whether the route is available - if not, then the centre indication will be illuminated in red. Moving the switch back to the left will cancel the route setting attempt, extinguishing the red indication and re-illuminating the leftmost indication.

However, if the route is available, the centre indication will be illuminated in white. Any conflicting routes will have their centre indication illuminated in red. The route setting process will begin, with points being moved as necessary and then the signal cleared. The centre indication will remain white for as long as the route is set.

The route is cancelled by moving the switch back to the left. If a train has not yet passed, the signal will be returned to danger and there will be a two minute timeout before a conflicting route can be set. However, the same route may be selected again immediately.

Once a train passes, the signal will return to danger and the route may be cleared.

If several trains will pass through the same route, then the switch may be moved to the rightmost position, in which case the route is set to automatic operation and the signal will clear again after the passage of each train. A blue light in the rightmost indication indicates that automatic operation is in effect.

## Construction

The panel faces were laser engraved/cut from acrylic, whilst the casing was laser cut from MDF.

TODO: Add more here

## Technical Details

There are two CBUS modules located within the panel:

- CANRGB - node 6010
- CANMIO - node 6020

In addition, the interlocking is handled by an Arduino-based module which has been named CANOCS:

- CANOCS - node 3150
