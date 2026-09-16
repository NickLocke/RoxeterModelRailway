# Roxeter Signals (RoxSignal)

This library is responsible for maintaining the status of all signals on the layout.  It has an internal table containing all of Roxeter's signals. However, any which are not controlled by the specific control panel running the software can be ignored.

The library works on the signal numbers which are displayed on the layout, as that makes configuration straightforward. Internally the event number used by the [Roxeter Event Sender](../RoxEventSender/) library is held to allow transaltion into the events that it will send.

There is some error checking of the calls made to ensure that they make sense. However, the checking is in the context of the single signal only. Any wider checking has to be the responsibility of the [Roxeter Interlocking](../RoxInterlocking/) library, as that knows the relationships between the various signals.

## Available Functions

### setSignalRed(uint16_t signalNumber)

This function will set a signal to red. It will be used for both main and shunt signals. 

The following issues will cause a False response to be returned:

- an invalid signal number is specified,
- the signal is located at a buffer stop,
- the signal has a fixed aspect,
- the [Roxeter Event Sender](../RoxEventSender/) library is unable to process the request. 

### setSignalYellow(uint16_t signalNumber)

This function will set a signal to yellow. It can only be used for main signals. 

The following issues will cause a False response to be returned:

- an invalid signal number is specified,
- the signal is located at a buffer stop,
- the signal has a fixed aspect,
- the signal is a shunt signal,
- the [Roxeter Event Sender](../RoxEventSender/) library is unable to process the request. 

### setSignalYellow(uint16_t signalNumber, FeatherPosition featherPosition)

This function will set a signal to yellow and display a feather indication. It can only be used for main signals. 

The following issues will cause a False response to be returned:

- an invalid signal number is specified,
- the signal is located at a buffer stop,
- the signal has a fixed aspect,
- the signal is a shunt signal,
- the signal does not have any feathers,
- the requested feather position does not exist on this signal,
- the [Roxeter Event Sender](../RoxEventSender/) library is unable to process the request. 

### setSignalGreen(uint16_t signalNumber)

This function will set a signal to green. It will be used for both main and shunt signals.  

The following issues will cause a False response to be returned:

- an invalid signal number is specified,
- the signal is located at a buffer stop,
- the signal has a fixed aspect,
- the [Roxeter Event Sender](../RoxEventSender/) library is unable to process the request. 

### setSignalGreen(uint16_t signalNumber, FeatherPosition featherPosition)

This function will set a signal to green and display a feather indication. It can only be used for main signals. 

The following issues will cause a False response to be returned:

- an invalid signal number is specified,
- the signal is located at a buffer stop,
- the signal has a fixed aspect,
- the signal is a shunt signal,
- the signal does not have any feathers,
- the requested feather position does not exist on this signal,
- the [Roxeter Event Sender](../RoxEventSender/) library is unable to process the request. 

### setSignalSubsidiaryOff(uint16_t signalNumber)

This function will set a signal's subsidiary aspect to clear. It can only be used for main signals which also have a subsidiary aspect. 

The following issues will cause a False response to be returned:

- an invalid signal number is specified,
- the signal is located at a buffer stop,
- the signal has a fixed aspect,
- the signal is not a main signal with a subsidiary aspect,
- the [Roxeter Event Sender](../RoxEventSender/) library is unable to process the request. 

### getSignalAspect(uint16_t signalNumber)

This function will obtain a signal's currently displayed aspect. It will return one of the values from the Signal Aspects section below.

### getFeatherPosition(uint16_t signalNumber)

This function will obtain a signal's currently shown feather indication. It will return one of the values from the Feather Positions section below.

#### Signal Aspects

Invalid Signal Number
Red
Yellow
Green
Subsidiary

#### Feather Positions

Invalid Signal Number
Signal does not have Feathers
None
Left One
Right One
Left Two
Right Two