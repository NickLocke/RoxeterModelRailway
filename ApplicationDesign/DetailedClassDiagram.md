# Detailed Class Diagram

<div class="mermaid">
classDiagram

    class RoxRoutingListener {
        <<interface>>
        +routeEvent(fromSignal, toSignal, event, sequence)
    }

    class RoxOcsPanel {
        -RoxSignals roxSignals
        -RoxPoints roxPoints
        -RoxTrackCircuits roxTrackCircuits
        -RoxEventHandler roxEventHandler
        -RoxRouting roxRouting

        +doVlcbProcessing()
        +doPanelProcessing()
        +routeSwitchOperation()
        +automaticSwitchOperation()
        +setRoute()
    }

    class RoxRouting {
        -RoxSignals* roxSignals
        -RoxPoints* roxPoints
        -RoxTrackCircuits* roxTrackCircuits
        -RoxRoutingListener* listener

        +requestSetRoute()
        +process()
    }

    class RoxSignals {
        +getSignalFromNumber()
        +setSignalAspect()
        +processSignalInRear()
    }

    class RoxPoints {
        +requestPointOperation()
        +process()
    }

    class RoxTrackCircuits {
        +detected()
        +getChangedStatus()
    }

    class RoxEventHandler {
        -RoxSignals* signals
        -RoxPoints* points
        -RoxTrackCircuits* trackCircuits
        -RoxOcsPanel* ocsPanel

        +eventProcessor()
        +processOcsPanelEvent()
    }

    class RoxEventSender {
        +sendSignalEvent()
        +sendTrackCircuitEvent()
    }

    RoxOcsPanel ..|> RoxRoutingListener

    RoxOcsPanel *-- RoxSignals
    RoxOcsPanel *-- RoxPoints
    RoxOcsPanel *-- RoxTrackCircuits
    RoxOcsPanel *-- RoxEventHandler
    RoxOcsPanel *-- RoxRouting

    RoxRouting --> RoxSignals
    RoxRouting --> RoxPoints
    RoxRouting --> RoxTrackCircuits
    RoxRouting --> RoxRoutingListener

    RoxEventHandler --> RoxSignals
    RoxEventHandler --> RoxPoints
    RoxEventHandler --> RoxTrackCircuits
    RoxEventHandler --> RoxOcsPanel

    RoxEventSender --> RoxSignals
    RoxEventSender --> RoxTrackCircuits

</div>