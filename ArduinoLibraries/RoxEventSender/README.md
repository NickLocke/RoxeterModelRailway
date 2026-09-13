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

## Signal

    static bool setRed(uint8_t signalNumber);
    static bool setYellow(uint8_t signalNumber);
    static bool setYellowWithFeather(uint8_t signalNumber, SignalFeathers feather);
    static bool setGreen(uint8_t signalNumber);
    static bool setGreenWithFeather(uint8_t signalNumber, SignalFeathers feather);
    static bool setSubsidiary(uint8_t signalNumber);

## Points

    static bool moveNormal(uint8_t pointsNumber);
    static bool moveReverse(uint8_t pointsNumber);
    static bool showNormal(uint8_t pointsNumber);
    static bool showReverse(uint8_t pointsNumber);
    static bool showLocked(uint8_t pointsNumber);
    static bool showOutOfCorrespondence(uint8_t pointsNumber);

## Track Occupancy

    static bool requestUpdate();
    static bool clearIndication(uint8_t trackCircuitNumber);
    static bool showIndication(uint8_t trackCircutNumber, TrackOccupancyGroups trackOccupancyGroup);

## Control Panel

    static bool setElementOn(uint8_t controlPanelNumber, ControlPanelGroups controlPanelGroup);
    static bool setElementOff(uint8_t controlPanelNumber, ControlPanelGroups controlPanelGroup);

## Accessory Control

    static bool setRailwayLight(uint8_t lightNumber, bool state);
    static bool setGeneralLight(uint8_t lightNumber, bool state);
    static bool playSoundEffect(uint8_t effectNumber);
    static bool selectLongLinePublicAddress(uint8_t publicAddressNumber);
    static bool cancelLongLinePublicAddress();
    static bool playStationAnnouncement(uint8_t announcementNumber);

