# Arduino Libraries

The Roxeter code has been structured into reusable libraries to allow sharing between the different types of control panel, avoiding the need for code to be written (or copied) multiple times.

The following libraries have either been written or are envisaged.

<div class="mermaid">
flowchart TB

    RoxeterPSB[Roxeter Power Signal Box]
    RoxeterLL[Roxeter Low Level Signal Box]
    CarvilJunction[CarvilJunctionSignalBox Signal Box]

    IFSpanel[Individual Function Switch Panel]
    OCSpanel[One Control Switch Panel]
    NXpanel[Entrance Exit Panel]

    RoxSignals[Signals Library]
    RoxPoints[Points Library]
    RoxEventSender[CBUS Events Sender]

    RoxeterPSB --> NXpanel
    RoxeterLL --> OCSpanel
    CarvilJunction --> IFSpanel

    NXpanel --> RoxSignals
    OCSpanel --> RoxSignals
    IFSpanel --> RoxSignals

    NXpanel --> RoxPoints
    OCSpanel --> RoxPoints
    IFSpanel --> RoxPoints

    RoxSignals --> RoxEventSender
    RoxPoints --> RoxEventSender
</div>