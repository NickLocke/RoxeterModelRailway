# Roxeter Event Sender (RoxEventSender)

This library is responsible for sending all events to CBUS. It provides an API which allows various types of event to be sent, whilst not requiring any knowledge of the underlying CBUS implementation.

The produced events are taught to other CBUS modules to allow them to respond appropriately.

The following event groups are supported:

- [Signal](Signal.md) - 0x0
- [Points](Points.md) - 0x1
- [Track Occupancy](TrackOccupancy.md) - 0x2
- [Control Panel](ControlPanel.md) - 0x3
- [Accessory Control](AccessoryControl.md) - 0x4

A total of sixteen event groups could be supported if necessary. The available API calls for each event group are listed below.  To allow the function names to be kept short, the event groups are each in a separate namespace. Therefore, the structure of calls is similar to these examples:

```c
EventSender::Points::moveNormal(80);
EventSender::Signal::setGreenWithFeather(78, EventSender::SignalFeathers::LEFT_FIRST);
```

## [Signal](Signal.md)

    setRed(uint8_t signalNumber);
    setYellow(uint8_t signalNumber);
    setYellowWithFeather(uint8_t signalNumber, SignalFeathers feather);
    setGreen(uint8_t signalNumber);
    setGreenWithFeather(uint8_t signalNumber, SignalFeathers feather);
    setSubsidiary(uint8_t signalNumber);
    allSignalsOn(uint8_t areaNumber);

## Points

    moveNormal(uint8_t pointsNumber);
    moveReverse(uint8_t pointsNumber);
    showNormal(uint8_t pointsNumber);
    showReverse(uint8_t pointsNumber);
    showLocked(uint8_t pointsNumber);
    showOutOfCorrespondence(uint8_t pointsNumber);

## Track Occupancy

    requestUpdate();
    clearIndication(uint8_t trackCircuitNumber);
    showIndication(uint8_t trackCircutNumber, TrackOccupancyGroups trackOccupancyGroup);

## Control Panel

    setElementOn(uint8_t controlPanelNumber, ControlPanelGroups controlPanelGroup);
    setElementOff(uint8_t controlPanelNumber, ControlPanelGroups controlPanelGroup);

## Accessory Control

    setRailwayLight(uint8_t lightNumber, bool state);
    setGeneralLight(uint8_t lightNumber, bool state);
    playSoundEffect(uint8_t effectNumber);
    selectLongLinePublicAddress(uint8_t publicAddressNumber);
    cancelLongLinePublicAddress();
    playStationAnnouncement(uint8_t announcementNumber);

