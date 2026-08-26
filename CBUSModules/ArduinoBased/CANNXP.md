# CANNXP

Sven Rosvall's design, with some enhancements to control LEDs. Used as the basis for route setting on the Roxeter PSB panel.

Note that this module does not run on a Pi Pico. It uses the Arduino Nano implementation, originally designed for Phil Silver's CANGATE and supplied by Railway Modelling Experts (RME).

TODO: Description of operation.

## Consumed Events

Each route setting button on the panel is configured with a button number, a button type and a series of up to ten valid routings. The event variables are configured as follows:

- EV1 - The button number that this event refers to (used to correlate internally with the CANNXP).
- EV2 - The button type - entrance only / entrance and exit / exit only.
- EVs 3 & 13 through 12 & 22 - For each entrance (or combined) button defines a relevant exit button and the internal route number that is called for the combination of entrance and exit.




## Produced Events

Flash entrance button
Steady entrance button
Cancel entrance button
Call route
