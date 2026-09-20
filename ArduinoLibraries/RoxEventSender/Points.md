# Points

All points on Roxeter are driven by servos connected to a CANMIO. Conceptually, the points are Normal when the CANMIO output is off and Reverse when it is on. Incoming events from the CANMIO are used to gain feedback on the position of the points, but that is documented elsewhere as this section of the documentation is concerned only with produced events.

## Available functions    

### moveNormal(uint8_t pointsNumber)

This function will send a single ACON event numbered 4096 plus the specific points number. The consuming module should be configured to drive the servo to its Normal position.

### moveReverse(uint8_t pointsNumber)

This function will send a single ACOF event numbered 4096 plus the specific points number. The consuming module should be configured to drive the servo to its Reverse position.

### showNormal(uint8_t pointsNumber)

This function will send a single ACON event numbered 4352 plus the specific points number. The consuming modules should be configured to switch on the Normal indication and extinguish any conflicting indications (Reverse and Out of Correspondence, for example).

### showReverse(uint8_t pointsNumber)

This function will send a single ACON event numbered 4608 plus the specific points number. The consuming modules should be configured to switch on the Reverse indication and extinguish any conflicting indications (Normal and Out of Correspondence, for example).

### showLocked(uint8_t pointsNumber)

This function will send a single ACON event numbered 4864 plus the specific points number. The consuming modules should be configured to switch on the Locked indication and extinguish any conflicting indications (Out of Correspondence, for example).

### showOutOfCorrespondence(uint8_t pointsNumber)

This function will send a single ACON event numbered 5120 plus the specific points number. The consuming modules should be configured to switch on the Out of Correspondence indication and extinguish any conflicting indications (Normal, Reverse and Locked, for example).
