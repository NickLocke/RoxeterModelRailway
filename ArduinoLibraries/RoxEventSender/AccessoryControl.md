# Accessory Control

## Low byte values

    RAILWAY_LIGHTS = 0x0,
    GENERAL_LIGHTS = 0x1,
    SOUND_EFFECTS = 0x2,
    LONG_LINE_PA_CONTROL = 0x3,
    STATION_ANNOUNCEMENTS = 0x4,

## Available functions

### setRailwayLight(uint8_t lightNumber, bool state);

### setGeneralLight(uint8_t lightNumber, bool state);

### playSoundEffect(uint8_t effectNumber);

### selectLongLinePublicAddress(uint8_t publicAddressNumber);

### cancelLongLinePublicAddress();

### playStationAnnouncement(uint8_t announcementNumber);
