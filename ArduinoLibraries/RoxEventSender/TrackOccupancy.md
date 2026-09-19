# Track Occupancy

Track occupancy on Roxeter is detected by DTC modules feeding CANMIO inputs. The events produced by track occupancy are documented elsewhere, as this section of the documentation is concerned only with produced events. The one exception to that is the `requestUpdate` function described below.

## Available functions

### requestUpdate(uint8_t areaNumber)

This function will send a single ACON event numbered 12032 plus the specific area number. The event should be taught as a Start of Day event to any module which handles detection for track circuits in the area concerned. Those modules should respond to that event by sending the current occupancy status for all tracks that they are monitoring. Those incoming events can then be processed as necessary.

### clearIndication(uint8_t trackCircuitNumber)

This function will send a single ACON event numbered 8192 plus the specific track circuit number. The consuming module should extinguish all track occupancy indications for the track circuit concerned.

### showIndication(uint8_t trackCircutNumber, TrackOccupancyGroups trackOccupancyGroup)

This function will send a single ACON event numbered one of

- 8704 Group A
- 8960 Group B
- 9216 Group C
- 9472 Group D
- 9728 Group E
- 9984 Group F
- 10240 Group G
- 10496 Group H

plus the specific signal number. Each group will identify a specific route through the track section concerned. The consuming module should illuminate all of the track segments which are relevant to the route. All other track segments should be extinguished. Where there are also route lights for the section of track, they should also be extinguished.

### floodIndication(uint8_t trackCircutNumber)

This function will send a single ACON event numbered 8448 plus the specific track circuit number. The consuming module should illuminate all track occupancy indications for the track circuit concerned. Where there are also route lights for the same section of track, they should be extinguished although, of course, if RGB LEDs rather than individual LEDs are used that will be implicit.