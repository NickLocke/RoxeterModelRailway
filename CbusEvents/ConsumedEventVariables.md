# Event Variables for Consumed Events

This section looks at the structure of the Event Variables which need to be passed into any of the Arduino modules which use the RoxEventHandler library.

Three Event Variables need to be supplied:

- Event Group
- Event Type
- Event Number

These are described in the following sections. A defintion file has been created for use within the Module Management Console (MMC) to simplify data entry and, hopefully, reduce the potential for errors.

## Event Group

The event group identifies a broad area of things which can produce events for consumption by the RoxEventHandler Library. The groups are listed below.

Group Name       | Identifier
----------       | ----------
Track Occupancy  | 1
Points           | 2
OCS Panel Inputs | 3
IFS Panel Inputs | 4
NX Panel Inputs  | 5

## Event Type

Event types are only valid within a specific event group and identify a more specific operation which is being reported. For example within the Points group, a type might indicate point movement being detected.

### Track Occupancy (Group 1)

Type Name         | Identifier
---------         | ----------
Occupation Status | 1

### Points (Group 2)

Type Name                | Identifier
---------                | ----------
Points Normal Detection  | 1
Points Reverse Detection | 2

### One Control Switch Panel Inputs (Group 3)

Type Name        | Identifier
---------        | ----------
Route Switch     | 1 
Automatic Switch | 2

### Individual Function Switch Panel Inputs (Group 4)

Type Name            | Identifier
---------            | ----------
Signal Switch        | 1
Point Switch Normal  | 2
Point Switch Reverse | 3

### Entrance Exit Panel Inputs (Group 5)

Type Name                 | Identifier
---------                 | ----------
Point Switch Normal       | 1
Point Switch Reverse      | 2
Entrance Exit Button Push | 3
Entrance Button Pull      | 4
Emergency Button Push     | 5
Emergency Button Pull     | 6
Describer Input Button    | 7
Describer Action Button   | 8
Telephone                 | 9
Alarm                     | 10

## Event Number

The event number identifies a specific instance of a thing within the group and type. For example, a specific point switch which has been moved. 