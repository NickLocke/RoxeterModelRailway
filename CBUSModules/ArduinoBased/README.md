# Arduino Based CBUS Modules

## Hardware
A Raspberyy Pi Pico mounted on a partially populated CANETHERX board.
The Pico supports driving the CAN IC (MCP2562) from software, so the alternate MCP2515 IC is not needed.

Although the Pico has a number of GPIO pins, these have not been used to date. The only interface with the outside world is via CBUS.

## CBUS Events
The modules can consume events to understand what is happening on the layout and control panels. They can also produce events to drive the layout and indications on the control panel.

Note that wherever possible, the intrinsic ability of CBUS to do multiple actions based on a single event is used to limit the number of separate events needed.

### Consumed Events
Existing events around the layout can be taught to the application. Typically there are two event variables, set up as follows:

- Event Type - used to tell the application the nature of the event which has occured (track occupied, switch operated, etc.).
- Identification Number - used to tell the application the specific thing which raised the event (which track, which switch, etc).

### Produced Events
The application can raise events to pass to the layout and control panels. It is possible to teach the application to raise custom events which already exist on the layout, but it easier to raise events (typically long events with the module's node number) and teach those to other CBUS modules as necessary.

Generally, these are simple on/off events (ACON and ACOF) with no additional parameters.

Nore that in a few cases, it has been necessary to spoof the node number, such that the event being raised appears to come from a different node (typically the node that the even is being sent to rather than the source node). Specifically, this has been necessary in the [CANDESC](CANDESC.md), because of the way the CANLED64 clones have been configured.

## Configuration
The events are configured using the Module Management Console (MMC). The MMC support for Module Definitioon Files (MDF) allows a helpful user interface to be created. This includes the ability to use dropdowns to make appropriate selections, for example selecting the type of event.

## Modules
The following module designs have been implemented:

- [CANDESC](CANDESC.md) - control of train descriptions for the entire layout, including the display on Roxeter PSB panel.
- [CANGATEXL](CANGATEXL.md) - Duncan Greenwood's design. Used on the Roxeter PSB panel to control the complex route light displays based on simple CBUS events.
- [CANIFS](CANIFS.md) - interlocking for an Individual Function Switch (IFS) signalling panel.
- [CANNXP](CANNXP.md) - Sven Rosvall's design, with some enhancements to control LEDs. Used as the basis for route setting on the Roxeter PSB panel.
- [CANOCS](CANOCS.md) - interlocking for a One Control Switch (OCS) signalling panel.
- [CANPOINT](CANPOINT.md) - controls the interaction between route setting and individual point switches on the Roxeter PSB panel.
