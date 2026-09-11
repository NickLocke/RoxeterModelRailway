# Arduino Libraries

The Roxeter code has been structured into reusable libraries to allow sharing between the different types of control panel, avoiding the need for code to be written (or copied) multiple times.

The following libraries have either been written or are envisaged.

<div class="mermaid">
flowchart LR

    Sketch[FastClock.ino]

    Config[Config]
    Clock[Clock]
    Display[Display]
    RTC[RTC]

    Sketch --> Config
    Sketch --> Clock
    Sketch --> Display

    Display --> RTC
    Clock --> RTC
</div>