The structure.

<div class="mermaid">
classDiagram
  class Clock
  class FastClock
  class RealTimeClockclass RTC_DS3231
  Clock <|-- FastClock
  Clock <|-- RealTimeClock
  RealTimeClock <|-- RTC_DS3231
</div>