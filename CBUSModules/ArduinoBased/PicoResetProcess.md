# Pico Reset Process

Firstly, as we can’t predict what the Pico board might have been used for previously, make sure the device has been reset to ‘factory default’ configuration, with no random data in non-volatile memory (EEPROM) that may cause confusion.

If the yellow FLiM LED is illuminated, hold down the CBUS switch for 8 seconds until it flashes and then release it. The green SLiM LED will illuminate.

Next, power off the board and hold down the CBUS switch whilst powering it back on (or reset the board whilst holding down the CBUS switch). Wait until both green and yellow LEDs start to flash and then release it. Then hold it for a further 5 seconds until they extinguish. The configuration will now be reset. This may take a while, after which the board will restart with the green LED illuminated. This convoluted process is to prevent accidental resets!
