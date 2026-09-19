# Event Flow

The general principle is that incoming events are handled as soon as possible, with any dependent processing happening in slower time. All events are received by the `RoxEventHandler` library and then passed to other libraries for action.

Events coming from the layout are relating to track occupancy and point detection.

## Track Occupancy

The `RoxTrackCircuits` library keeps track of status changes to track circuits. Whenever a track ciruit status is updated, a flag is set to indicate that the change has not yet been processed by the panel software. A function call allows the panel software to check whether any changes require processing. That call also resets the flag, so it is important that all changes identified are processed as they will not be identified a second time.

## Point Detection