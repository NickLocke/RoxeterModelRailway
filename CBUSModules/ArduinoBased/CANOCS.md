# CANOCS

Interlocking for a One Control Switch (OCS) signalling panel.

The CANOCS maintains an internal table of routes.

Note that track occupancy events on the layout are directly coupled to the CANARGB so there is no involvement of the CANOCS in that. The same occupancy events are also fed to the CANOCS though for use by its internal processing.


## Consumed Events

The CANOCS has seven types of consumed event:

- Route setting
- Automated reset
- Track occupancy
- Points detected normal
- Points detected reverse

Each of the event types is described below.

### Route Setting
These events are raised by the control switches on the panel being moved from idle to route set and vice versa.

Note that events 1 through 8 are set to Event Inverted because the standard switch wiring is on when the switch is in the leftmost position, but in this instance, that is a logical off.

Event Type = 1

### Automated Reset
These events are raised by the control switches on the panel being moved from route set to automatic and vice versa.

Event Type = 2

### Track Occupancy
These events are raised by the layout's track occupancy sensors changing from clear to occupied or vice versa.

Event Type = 3

### Points Detected (normal or reverse)
These events are raised by the layout's point drivers detecting (or losing detection) of each set of points.

Event Type = 4 (normal)
Event Type = 5 (reverse)

## Produced Events

### Switch Indications
The numbers at the end of each entry are the high-byte value (the value of the byte
and the resulting value of the event) - add the second number to the switch number between 1 and 8 to get the actual event number.

Route idle - white / off / off - 0
Route called and checking availability - off / white (flashing) / off - 256
Route called but inhibited - off / red (flashing) / off - 512
Route called and setting up - off / white / off - 768
Route set - off / green / off - 1024
Route set and in automatic mode - off / green / blue - 1280

### Point Control
Will produce an on event to reverse the points and an off event to restore them to the normal position.

The high-byte value required is 6 which translates as 1536 as the event number to add to the point number.

### Signal Control
Will produce an on event to clear the signal and an off event to restore it to danger. Note that further work will be needed if three aspect signals are deployed
on the layout, in order to control the yellow/green display.

The high-byte value required is 7 which translates as 1792 as the event number to add to the signal number.
