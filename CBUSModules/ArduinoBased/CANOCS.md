# CANOCS

Interlocking for a One Control Switch (OCS) signalling panel.

The CANOCS maintains an internal table of routes.

Note that track occupancy events on the layout are directly coupled to the CANARGB so there is no involvement of the CANOCS in that. The same occupancy events are also fed to the CANOCS though for use by its internal processing.


## Consumed Events

The CANOCS has five types of consumed event:

- Route Setting
- Automated Reset
- Track Occupancy

Each of the event types is described below.

### Route Setting
These events are raised by the control switches on the panel being moved from idle to route set and vice versa.

Note that events 1 through 8 are set to Event Inverted because the standard switch wiring is on when the switch is in the leftmost position, but in this instance, that is a logical off.

### Automated Reset
These events are raised by the control switches on the panel being moved from route set to automatic and vice versa.

### Track Occupancy
These events are raised by the layout's track occupancy sensors changing from clear to occupied or vice versa.

## Produced Events

Route idle - white / off / off
Route called and checking availability - off / white (flashing) / off
Route called but inhibited - off / red (flashing) / off
Route called and setting up - off / white / off
Route set - off / green / off
Route set and in automatic mode - off / green / blue


