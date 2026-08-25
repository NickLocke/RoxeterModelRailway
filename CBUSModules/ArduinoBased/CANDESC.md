# CANDESC

Control of train descriptions for the entire layout, including the display on Roxeter PSB panel.

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

TODO: Get this from the code.
