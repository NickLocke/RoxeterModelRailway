# Roxeter Event Sender (RoxEventSender)

This library is responsible for sending all events to CBUS. It provides an API which allows various types of event to be sent, whilst not requiring any knowledge of the underlying CBUS implementation.

The produced events are taught to other CBUS modules to allow them to respond appropriately.

The following event groups are supported:

- [Signal](Signal.md) - 0x0
- [Points](Points.md) - 0x1
- [Track Occupancy](TrackOccupancy.md) - 0x2
- [Control Panel](ControlPanel.md) - 0x3
- [Accessory Control](AccessoryControl.md) - 0x4
- [Route](Route.md) - 0x5

A total of sixteen event groups could be supported if necessary. To allow the function names to be kept short, the event groups are each in a separate namespace. Therefore, the structure of calls is similar to these examples:

```c
EventSender::Points::moveNormal(80);
EventSender::Signal::setSignalGreen(78, FeatherPosition featherPosition);
```

