# Signal

## Low byte values

    RED = 0x0,
    YELLOW = 0x1,
    GREEN = 0x2,
    SUBSIDIARY = 0x3,
    FEATHER_LEFT_1 = 0x4,
    FEATHER_LEFT_2 = 0x5,
    FEATHER_RIGHT_1 = 0x6,
    FEATHER_RIGHT_2 = 0x7,
    FEATHER_NONE = 0x8

## Available functions

### setRed(uint8_t signalNumber);

### setYellow(uint8_t signalNumber)

### setYellowWithFeather(uint8_t signalNumber, SignalFeathers feather);

### setGreen(uint8_t signalNumber);

### setGreenWithFeather(uint8_t signalNumber, SignalFeathers feather);

### setSubsidiary(uint8_t signalNumber);

### allSignalsOn(uint8_t areaNumber);