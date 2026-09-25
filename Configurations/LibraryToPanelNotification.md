# Library to Panel Event Notification

Because functionality is abstracted away into libraries such as RoxRouting, it is necessary for those libraries to be able to report things happening to the controlling panel. Because we will have three different types of panel, the reportin mechanism needs to be generic - so we use interfaces.

For example, `RoxRouting` may need to report:

- a route being set
- a route being cancelled
- a route becoming inhibited
- a route being released
- a route failing

The routing library must not know which type of signal-box panel is using it. The same `RoxRouting` library is used by:

- `RoxNxPanel`
- `RoxOcsPanel`
- `RoxIfsPanel`

## Listener interface

This is implemented using a listener interface.

`RoxRouting` holds a pointer to a `RoxRoutingListener`:

`RoxRoutingListener *listener;`

RoxRoutingListener defines the events which RoxRouting can report:

```
class RoxRoutingListener
{
public:
    virtual void routeEvent(
        uint8_t routeNumber,
        RouteEvent event) = 0;
};
```

The `= 0` makes `routeEvent()` a pure virtual function, making RoxRoutingListener an abstract class. It is therefore **not instantiated directly**.

## Panel implementation

Each panel which uses `RoxRouting` inherits from `RoxRoutingListener`:

```
class RoxOcsPanel : public RoxRoutingListener
{
public:
    void routeEvent(
        uint8_t routeNumber,
        RouteEvent event) override;

    ...
};
```

The panel passes `this` to `RoxRouting` when constructing it:

```
roxRouting(
    &roxSignals,
    &roxPoints,
    &roxTrackCircuits,
    this)
```

Because `RoxOcsPanel` inherits from `RoxRoutingListener`, its `this` pointer can be passed as a `RoxRoutingListener *`.

`RoxRouting` can then report an event without knowing which panel is receiving it:

```
listener->routeEvent(
    routeNumber,
    RouteEvent::SET);
```

C++ dispatches this to the appropriate panel's implementation of `routeEvent()`.

Resulting relationship
                    RoxRoutingListener
                           ▲
                           │
             ┌─────────────┼─────────────┐
             │             │             │
        RoxNxPanel    RoxOcsPanel    RoxIfsPanel
             ▲             ▲             ▲
             │             │             │
             └─────────────┼─────────────┘
                           │
                      RoxRouting

`RoxRouting` therefore depends only on the `RoxRoutingListener` interface, rather than on any particular panel library.

This is important because the routing logic is common to all three signal boxes, whereas the way each panel responds to a routing event may be different.

## General principle

This pattern should also be considered for other common libraries which need to report events to the panel.

For example, `RoxPoints` may eventually need to report events such as:

- point movement started
- point movement completed
- point failed
- point detected in the wrong position
- point operation timed out

Rather than making `RoxPoints` know about `RoxNxPanel`, `RoxOcsPanel` or `RoxIfsPanel`, a corresponding listener interface can be introduced.

The general architecture is therefore:

Common library
      │
      │ reports events through
      ▼
    Listener
      ▲
      │ implemented by
      │
Signal-box-specific panel

This keeps the common libraries independent of the particular signal-box implementation while allowing each panel to respond to events in whatever way is appropriate for that type of signalling system.