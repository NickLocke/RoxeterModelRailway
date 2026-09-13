# Roxeter Event Sender (RoxEventSender)

This library is responsible for sending all events to CBUS. It provides an API which allows various types of event to be sent, whilst not requiring any knowledge of the underlying CBUS implementation.

The produced events are taught to other CBUS modules to allow them to respond appropriately.

The following event groups are supported:

- [Signal](Signal.md) - 0x0
- [Points](Points.md) - 0x1
- [Track Occupancy](TrackOccupancy.md) - 0x2
- [Control Panel](ControlPanel.md) - 0x3
- [Accessory Control](AccessoryControl.md) - 0x4

A total of sixteen event groups could be supported if necessary.

The event number sent to CBUS is made up of one Word, so a high Byte and a low Byte. The low Byte is used to identify a specific target for the event - a switch, a signal mast, etc. 

The high Byte is used to specify what type of device is being targeted in the high Nibble and what it is required to do in the low Nibble.

The hexadecimal values of the high Nibble are as shown in the list above. The values for the low Nibbles are defined on the approriate specific pages.

Note that this detail is useful when monitoring events on the CBUS, but is not needed to actually use the API calls.

## Worked Example

Assume that we have a set of points which we have chosen to number as 78 which is 4E in hexadecimal. We wish to send an event to show a Reverse indication for those points. We can see from above that the high Nibble value to indicate points is 0x1. We can see from the points documentation page that the low Nibble vale for a reverse indication is 0x2.

So the first byte of the event number is made up from those two Nibbles, giving 0x12. The second byte contains only the number for the points, so that is 0x4E.

Combining those two Bytes to make the Word to send to CBUS give 0x124E which is 4686 in decimal.