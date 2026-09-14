# Accessory Control

## Low byte values

    RAILWAY_LIGHTS = 0x0,
    GENERAL_LIGHTS = 0x1,
    SOUND_EFFECTS = 0x2,
    LONG_LINE_PA_CONTROL = 0x3,
    STATION_ANNOUNCEMENTS = 0x4,

## Available functions

### setRailwayLight(uint8_t lightNumber, bool state)

This function in intended to control lights in the railway environment, for example station lights. It will send a single ACON or ACOF event numbered 16384 plus the specific light number. The state should be set to `true` for On and `false` for Off. The consuming module should be configured to switch the selected output on or off accordingly.

### setGeneralLight(uint8_t lightNumber, bool state)

This function in intended to control general lighting, such as building lights. It can also operate other accessories as necessary. It will send a single ACON or ACOF event numbered 16640 plus the specific light number. The state should be set to `true` for On and `false` for Off. The consuming module should be configured to switch the selected output on or off accordingly.

### playSoundEffect(uint8_t effectNumber)

This function is intended to trigger sound effects around the layout. It will send a single ACON event numbered 16896 plus the specific effect number. The state should be set to `true` for On and `false` for Off. The consuming module should be configured to switch the selected output on as necessary - and that may well be a pulse output to trigger an effect.

### selectLongLinePublicAddress(uint8_t publicAddressNumber)

This function will select a remote public address system, typically at a station, to allow an announcement to be played. It will send a single ACON event numbered 17152 plus the specific PA system number. The consuming model should switch on the relevant output, allowing audio to be sent to the local amplifier.

If the same announcement is to be sent to more than one destination simultaneously, then this function may be called multiple times.

### cancelLongLinePublicAddress()

This function is intended to deselect all locations from the remote public address system. It will send a single ACOF event numbered 17152. All consuming modules shoudl be configured to turn of the relevant output when the event is received.

### playStationAnnouncement(uint8_t announcementNumber)

This function works in collaboration with the `selectLongLinePublicAddress` function. Once one or more destinations for an announcement have been selected, this function is used to trigger a specific announcement. It will send a single ACON event numbered 17408 plus the specific announcement number. 

Once implemented, the consuming module should then play out the selected announcement onto the long line public address system.
