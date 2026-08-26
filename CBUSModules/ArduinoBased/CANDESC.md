# CANDESC

Control of train descriptions for the entire layout, including the display on Roxeter PSB panel.

Because the Roxeter PSB clock display uses the same CANLED64 clone display hardware, the CANDESC also produces an update to the clock display once per minute.

TODO: Description of operation.

## Consumed Events
The CANDESC has five types of consumed event:

- Data Input
- Action
- Alarm
- Track Occupancy
- Route Setting

Each of the event types is described below.

### Data Input
The train describer keyboard provides keys for:

- A to Z
- 0 to 9
- Asterisk
- Hyphen
- Blank

On the control panel, a CANSCAN listens for any key bring pressed and raises an event. Each of those events is added to the CANDESC as a data input event, using an MMC dropdown.

### Action
The train describer keyboard provides keys for:

- Cancel
- Interpose
- Interrogate
- Reset

On the control panel, a CANSCAN listens for any key bring pressed and raises an event. Each of those events is added to the CANDESC as an action event, using an MMC dropdown.

### Alarm
The train describer keyboard provides keys for:

- Describer Fault
- Not Described

On the control panel, a CANSCAN listens for either key bring pressed and raises an event. Each event is added to the CANDESC as an alarm event, using an MMC dropdown.

### Track Occupancy
The CANDESC needs to be aware of track circuits becoming occupied or clear, because that drives the processing which steps train descriptions from one berth to another.

The CANDESC application holds a table of relevant track circuits, listing the berth stepping rules. An event is added for each track occupancy detector, allowing the CANDESC to react to tracks on the layour becoming occupied and clear.

### Route Setting
The CANDESC needs to be aware of routes being set and cleared. The CANDESC application holds a table of relevant routes. An event is added to show when each route is set or cleared, allowing the CANDESC to react appropriately.

## Produced Events
The application maintains an internal state for each describer berth, meaning that there is no external interface for the majority of berths. However, events are sent to the bus for any describer berth which phyically exists on the Roxeter PSB panel.

The events are long on events (ACON) containing the node number of the describer berth which is being addressed and the event number which indicates what to display and in which character position. To fully set a berth, four events need to be sent - one for each of the four character positions in the display berth. 

The CANLED64 clones cannot cope with four events (which they have to action) being sent in quick succession, so each of the events is interspersed with two additional ACON events (sending event number zero to node zero) simply to allow the CANLED64 clones a chance to breathe.


