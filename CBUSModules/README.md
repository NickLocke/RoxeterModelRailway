# CBUS Modules
The layout relies heavily on CBUS modules for its operation.

There are two types of module employed on the layout:

- [PIC-based](PICBased/README.md) standard CBUS modules
- [Arduino-based](ArduinoBased/README.md) custom modules

Whilst there are many CBUS OpCodes, only a few are in general use within the Roxeter environment. This table is a quick reference guide to the most commonly used OpCodes:

Mnemonic | Description | Hex Value | Decimal Value
--------:|:----------- | ---------:| -------------:
ACON     | xx          | 0x90      | 144
ACOF     | xx          | 0x91      | 145
AREQ     | xx          | 0x92      | 146
ARON     | xx          | 0x93      | 147
AROF     | xx          | 0x94      | 148
