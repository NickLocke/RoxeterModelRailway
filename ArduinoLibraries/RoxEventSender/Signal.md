# Signal

All signals on Roxeter have each separate light connected to a separate CANMIO output. The CANMIO's response to events must be configured in a way which prevents invalid aspects being shown. Signals are three aspect or fewer, there are no four aspect signals. The layout also has stand alone shunt signals and subsidiary aspects on main signals. Feathers on main signals are supported, to a maximum of two in each direction. 

## Available functions

### setRed(uint8_t signalNumber)

This function will send a single ACON event numbered 0 plus the specific signal number. Consuming modules should be configured to switch on the red aspect and extinguish all others, including feathers and subsidiary aspects.

Where the signal is a shunt rather than a main signal, consuming modules should switch on the On indication and extinguish the Off indication.

### setYellow(uint8_t signalNumber)

This function will send a single ACON event numbered 256 plus the specific signal number. Consuming modules should be configured to switch on the yellow aspect and extinguish red, green and subsidiary, but not feathers.

### setYellowWithFeather(uint8_t signalNumber, SignalFeathers feather)

This function will send two events. The first ACON event will illuminate the feather and will be numbered one of

- 1024 Feather left 1
- 1280 Feather left 2
- 1536 Feather right 1
- 1792 Feather right 2

plus the specific signal number. Consuming modules should illuminate the requested feather and extinguish the other three feathers.

The second ACON event will be the standard yellow aspect setting, 256 plus the specific signal number.

### setGreen(uint8_t signalNumber)

This function will send a single ACON event numbered 512 plus the specific signal number. Consuming modules should be configured to switch on the green aspect and extinguish all others, including feathers and subsidiary aspects.

### setGreenWithFeather(uint8_t signalNumber, SignalFeathers feather)

This function will send two events. The first ACON event will illuminate the feather and will be numbered one of

- 1024 Feather left 1
- 1280 Feather left 2
- 1536 Feather right 1
- 1792 Feather right 2

plus the specific signal number. Consuming modules should illuminate the requested feather and extinguish the other three feathers.

The second ACON event will be the standard green aspect setting, 512 plus the specific signal number.

### setSubsidiary(uint8_t signalNumber)

This function will send a single ACON event numbered 768 plus the specific signal number. Consuming modules should be configured to switch on the red and subsidiary aspects and extinguish all others, including feathers. 

Where the signal is a shunt rather than a subsidiary, consuming modules should switch on the Off indication and extinguish the On indication.

### allSignalsOn(uint8_t areaNumber)

This function will send a single ACON event numbered 3840 plus the specific area number. It is intended for use during startup and, possibly, in an emergency scenario. It addresses a conceptual area rather than a specific signal. The event may be consumed by multiple signal-driving modules. In each case, consuming modules should be configured to switch on the red aspect and extinguish all others, including feathers and subsidiary aspects.