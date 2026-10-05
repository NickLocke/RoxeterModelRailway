# High Level Architecture

<div class="mermaid">

flowchart TB

    subgraph Panels["Signal Box / Panel Applications"]
        NX["RoxNxPanel"]
        OCS["RoxOcsPanel"]
        IFS["RoxIfsPanel"]
    end

    subgraph Signalling["Common Signalling Libraries"]
        Routing["RoxRouting"]
        Signals["RoxSignals"]
        Points["RoxPoints"]
        TrackCircuits["RoxTrackCircuits"]
    end

    subgraph Interfaces["Callback Interfaces"]
        RoutingListener["RoxRoutingListener"]
        PointsListener["RoxPointsListener"]
        SignalsListener["RoxSignalsListener"]
    end

    subgraph Hardware["Hardware / Event Handling"]
        EventHandler["RoxEventHandler"]
        EventSender["RoxEventSender"]
    end

    NX --> Routing
    NX --> Signals
    NX --> Points
    NX --> TrackCircuits

    OCS --> Routing
    OCS --> Signals
    OCS --> Points
    OCS --> TrackCircuits

    IFS --> Routing
    IFS --> Signals
    IFS --> Points
    IFS --> TrackCircuits

    Routing --> Signals
    Routing --> Points
    Routing --> TrackCircuits

    Routing --> RoutingListener
    Points --> PointsListener
    Signals --> SignalsListener

    NX -. implements .-> RoutingListener
    OCS -. implements .-> RoutingListener
    IFS -. implements .-> RoutingListener

    NX -. implements .-> PointsListener
    OCS -. implements .-> PointsListener
    IFS -. implements .-> PointsListener

    NX --> EventHandler
    OCS --> EventHandler
    IFS --> EventHandler

    EventHandler --> EventSender

 




</div>