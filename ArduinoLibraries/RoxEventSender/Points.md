# Points
## Low byte values

    REQUEST_MOVEMENT = 0x0,
    NORMAL_INDICATION = 0x1,
    REVERSE_INDICATION = 0x2,
    LOCKED_INDICATION = 0x3,
    OUT_OF_CORRESPONDENCE_INDICATION = 0x4,    

## Available functions    

### moveNormal(uint8_t pointsNumber)

### moveReverse(uint8_t pointsNumber);

### showNormal(uint8_t pointsNumber);

### showReverse(uint8_t pointsNumber);

### showLocked(uint8_t pointsNumber);

### showOutOfCorrespondence(uint8_t pointsNumber);
