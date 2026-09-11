---
---
# Arduino Libraries

The Roxeter code has been structured into reusable libraries to allow sharing between the different types of control panel, avoiding the need for code to be written (or copied) multiple times.

The following libraries have either been written or are envisaged.

<div class="mermaid">
classDiagram
  class Clock
  class FastClock
  class RealTimeClockclass RTC_DS3231
  Clock <|-- FastClock
  Clock <|-- RealTimeClock
  RealTimeClock <|-- RTC_DS3231
</div>

V3