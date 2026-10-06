# Switch Indications (Roxeter low level)

This page provides an easy reference for use when configuring indications near the panel switches in CBUS and 
when investigating any problems.

| Switch<br/>Number [1] | Idle [2] | Unavailable [3] | Setting [4] | Set [5] | Automatic [6] | Cancelling [7] | Wrong [8] |
| --------------------- | -------- | --------------- | ----------- | ------- | ------------- | -------------- | --------- |
| 1                     | 12289    | 12545           | 12801       | 13057   | 13313         | 13569          | 13825     |
| 2                     | 12290    | 12546           | 12802       | 13058   | 13314         | 13570          | 13826     |
| 3                     | 12291    | 12547           | 12803       | 13059   | 13315         | 13571          | 13827     |
| 4                     | 12292    | 12548           | 12804       | 13060   | 13316         | 13572          | 13828     |
| 5                     | 12293    | 12549           | 12805       | 13061   | 13317         | 13573          | 13829     |
| 6                     | 12294    | 12550           | 12806       | 13062   | 13318         | 13574          | 13830     |
| 7                     | 12295    | 12551           | 12807       | 13063   | 13319         | 13575          | 13831     |
| 8                     | 12296    | 12552           | 12808       | 13064   | 13320         | 13576          | 13832     |


1 - The number of the control switch on the panel, reading from left to right.

2 - Shows that the route associated with the switch is idle. The indication is a white light in the leftmost position.

3 - Shows that an attempt has been made to set the route, but it is locked and cannot be set. The indication is a flashing red light in the centre position.

4 - Shows that the route is actively being set. The indication is a flashing white light in the centre position.

5 - Shows that the route is set. The indication is a steady green light in the centre position.

6 - Shows that the route is set and configured for automatic operation. The indication is a steady green light in the centre position and a steady blue light in the rightmost position.

7 - Shows that the route is cancelling (and wasn't imemdiately cancelled). It may well be waiting for an approach release of the signal.

8 - Shows that the switch is in an incorrect position. This will happen at statup is any switch is not in the idle position. It will also occur if a route cancels because of a train passing and the route is not set to automatic.

The base numbers (to which the switch number is added) for each indication are as follows:

- 12288 - Idle
- 12544 - Unavailable
- 12800 - Setting
- 13056 - Set
- 13312 - Automatic
- 13568 - Cancelling
- 13824 - Wrong switch position

To request an update of the switch positions, message type 16 is sent. That is a base number of 16128. So for Roxeter Low Level which is signal box 2, the message to be sent is 16130.