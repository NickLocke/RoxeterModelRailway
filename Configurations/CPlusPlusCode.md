# C++ Code

## Anonymous Namespaces

Typically private functions are declared in the header file and then implemented in a CPP file. That can lead to a large list of definitions in the header file. As an alternative, functiosn which are used only within the context of a single CPP file can be declared in an anonymous namespace within that CPP file.

Functions declared in that way work in exactly the same way with one important exception. They do not have access to anything that has been declared as private in the header file. Typically that is only an issue for logging, where the `LOGGING` and `LOGGING_NAME` variables are not visible. The simple workaround for those, specifically, is to make them public.

## Friend

Where the header of a class exposes a lot of functions, it makes sense to group them into logically related classes - allowing shorter names and ading to readability. That does however mean that those extra classes are not visible from within the parent class.

To fix that, the `friend` modifier is used:

```c++
class RoxEventSender
{
public:
#include "PublicEnums.h"

  // Signals
  class Signal
  {
    friend class RoxEventSender;

  public:
    static bool setRed(uint8_t signalNumber);
    static bool setYellow(uint8_t signalNumber);
    static bool setYellowWithFeather(uint8_t signalNumber, SignalFeathers feather);
    static bool setGreen(uint8_t signalNumber);
    static bool setGreenWithFeather(uint8_t signalNumber, SignalFeathers feather);
    static bool setSubsidiary(uint8_t signalNumber);
    static bool allSignalsOn(uint8_t areaNumber);
    static void documentEvents();
    static const char *getTypeNameFromNumber(uint8_t eventType);
  };
  etc.
}
```

Access to those functions can then be obtained using, for example:

'''c++
RoxEventSender::Signal::setRed(uint8_t signalNumber);
'''

## Circular Dependencies

For example, RoxEventHandler needs to know about RoxOcsPanel and vice versa. Standard includes of the header files cause chaos. So forward declaratiuon is needed.  Essentially that means the header file does not do a full include, so no `#include`. Instead, it just forward declares the class with a simple mention towards the top of the header file:

```c++
#pragma once

#include <Streaming.h>
#include "RoxSignals.h"
#include "RoxPoints.h"
#include "RoxTrackCircuits.h"

class RoxEventHandler;
 
class RoxOcsPanel
{
public:
etc.
}
```

Then the full defintion is pulled in later, by including the header in the CPP file where the class is actually used.

## Instance vs Static

Where it is necessary to access the specific instance of an object, rather than just some static properties, it is necessary to gain access to that instance. Using RoxEventHandler as an example, a pointer to the instance is defined in the header:

```c++
static RoxEventHandler *instance;
```

An initial value of `nullptr` needs to be set. A sensible place to do this is in the CPP file which contains the constructor:

```c++
RoxEventHandler* RoxEventHandler::instance = nullptr;
```

Then, in the constructor, the value of instance is actually set:

```c++
RoxEventHandler::RoxEventHandler()
{
   instance = this;
}
```

From then on, `instance` can be used whenever it is necessary to refer to something non-static in the specific instance of the class. Typically, that is a requirement when access to member variables is needed. For example:

```c++
instance->processTrackOccupancyEvent(actionType, eventVariableType, eventVariableNumber);
```

## Public vs Private

?????

## Lists of Objects

?????