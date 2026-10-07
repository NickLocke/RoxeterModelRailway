# High Level Architecture

<div class="mermaid">

flowchart TB

    subgraph Panels["Signal Box Types (IFS / OCS / NX)"]
        XXX["RoxXXXPanel"]
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
        TrackCircuitsRoutingListener["TrackCircuitsRoutingListener"]
        TrackCircuitsSignalsListener["TrackCircuitsSignalsListener"]
    end

    subgraph Hardware["Hardware / Event Handling"]
        EventHandler["RoxEventHandler"]
        EventSender["RoxEventSender"]
    end

    XXX --> Routing
    XXX --> Signals
    XXX --> Points
    XXX --> TrackCircuits

    Signals --> Routing
    Points --> Routing
    TrackCircuits --> Routing

    Routing --> RoutingListener
    Points --> PointsListener
    TrackCircuits --> TrackCircuitsRoutingListener
    TrackCircuits --> TrackCircuitsSignalsListener


    Routing --> EventSender
    Signals --> EventSender
    Points --> EventSender
    TrackCircuits --> EventSender
    XXX --> EventSender


    XXX -. implements .-> RoutingListener

    XXX -. implements .-> PointsListener

    EventHandler --> XXX
    EventHandler --> Signals
    EventHandler --> Points
    EventHandler --> TrackCircuits

    

</div>