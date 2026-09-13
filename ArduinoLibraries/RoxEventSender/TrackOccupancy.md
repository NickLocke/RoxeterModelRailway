# Track Occupancy

## Low byte values

    TRACK_CLEAR = 0x0,
    TRACK_FLOOD = 0x1,
    TRACK_GROUP_A = 0x2,
    TRACK_GROUP_B = 0x3,
    TRACK_GROUP_C = 0x4,
    TRACK_GROUP_D = 0x5,
    TRACK_GROUP_E = 0x6,
    TRACK_GROUP_F = 0x7,
    TRACK_GROUP_G = 0x8,
    TRACK_GROUP_H = 0x9,
    SPARE_A = 0xA,
    SPARE_B = 0xB,
    SPARE_C = 0xC,
    SPARE_D = 0xD,
    SPARE_E = 0xE,
    REQUEST_UPDATE = 0xF

## Available functions

### requestUpdate();

### clearIndication(uint8_t trackCircuitNumber);

### showIndication(uint8_t trackCircutNumber, TrackOccupancyGroups trackOccupancyGroup);
