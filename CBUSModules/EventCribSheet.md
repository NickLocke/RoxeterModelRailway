# Event Crib Sheet

Blah blah.....

## Point feedback

Where points are driven using the servo settings in the universal firmware, three events are provided which give feedback on the movement of the servos.

The events are numbered as follows, where x is the channel number to which the servo is connected:

- Normal position 10x (channel number + 100)
- Mid position 30x (channel number + 300)
- Reverse position 20x (channel number + 200)

The mid position event is used in some cases to do frog switching, but does not form part of the interfacing to panels, so is ignored here. As an example, for a servo attached to channel 5 of a CANMIO, and assumed to be in the normal position, the following events will be raised as the points move to the reverse position:

- 105 off
- 205 on

When the points are returned to the normal position, the expected events will be:

- 205 off
- 105 on