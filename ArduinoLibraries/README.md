# Arduino Libraries

The Roxeter code has been structured into reusable libraries to allow sharing between the different types of control panel, avoiding the need for code to be written (or copied) multiple times.

The following libraries have either been written or are envisaged.

<div class="mermaid">
flowchart LR

    subgraph "Signal Boxes"
      RoxeterPSB[Roxeter Power Signal Box]
      RoxeterLL[Roxeter Low Level Signal Box]
      CarvilJunction[Carvil Junction Signal Box]
    end

    subgraph "Signal Box Types"
      IFSpanel[Individual Function Switch Panel]
      OCSpanel[One Control Switch Panel]
      NXpanel[Entrance Exit Panel]
    end

    RoxSignals[Signals Operation]
    RoxPoints[Points Operation]
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