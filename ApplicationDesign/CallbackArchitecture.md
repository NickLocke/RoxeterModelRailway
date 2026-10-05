# Callback Architecture

<div class="mermaid">
flowchart LR

    Routing["RoxRouting"]
    Points["RoxPoints"]
    Signals["RoxSignals"]

    RoutingListener["RoxRoutingListener\n«interface»"]
    PointsListener["RoxPointsListener\n«interface»"]
    SignalsListener["RoxSignalsListener\n«interface»"]

    NX["RoxNxPanel"]
    OCS["RoxOcsPanel"]
    IFS["RoxIfsPanel"]

    Routing --> RoutingListener
    Points --> PointsListener
    Signals --> SignalsListener

    NX -. implements .-> RoutingListener
    OCS -. implements .-> RoutingListener
    IFS -. implements .-> RoutingListener

    NX -. implements .-> PointsListener
    OCS -. implements .-> PointsListener
    IFS -. implements .-> PointsListener

    NX -. implements .-> SignalsListener
    OCS -. implements .-> SignalsListener
    IFS -. implements .-> SignalsListener

</div>