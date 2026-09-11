<script type="module">
import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@11/dist/mermaid.esm.min.mjs';
mermaid.initialize({
startOnLoad: true
});
</script>

The Roxeter code has been structured into reusable libraries to allow sharing between the different types of control panel, avoiding the need for code to be written (or copied) multiple times.

The following libraries have either been written or are envisaged.

```mermaid
classDiagram
class Clock
class FastClock
class RealTimeClock
class RTC_DS3231
Clock <|-- FastClock
Clock <|-- RealTimeClock
RealTimeClock <|-- RTC_DS3231
```