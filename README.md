# Euroscope Profiles for ZOB ARTCC

Contains Euroscope profiles and a modified sector file for use on the VATSIM network. Contains vSMR for asde-x simulation. Unofficial

## Installation

- Move the ZOB folder to the Euroscope folder
- Open the desired profile

# Information

Sector file © Cleveland ARTCC 2023


vSMR plugin thanks to pierr3, license found [here](https://github.com/pierr3/vSMR/blob/master/LICENSE). vSMR is distributed unmodified as part of the profiles.

AfV Euroscope Bridge thanks to Andy Ford, license found [here](https://github.com/AndyTWF/afv-euroscope-bridge/blob/master/LICENSE). AfV Euroscope is distributed unmodified as part of the profiles.

Profiles © 2023 Genau6502

# Sector file conversion

.SCT2 files require some modification prior to being usable with Euroscope.

### Airspace classes

The class of airspace associated with an airport must be added in the following line of the SCT:


Before: `<ICAO> <tower frequency>   <Nxxx.xx.xx.xxx Wyyy.yy.yy.yyy>  ; <name>`

After: `<ICAO> <tower frequency>   <Nxxx.xx.xx.xxx Wyyy.yy.yy.yyy> <Class of associated airspace (letter only eg. KCLE would be 'B')>  ; <name>`

### Runway definitions

The name of the airport along with its ICAO code must be added to the line for each runway, along with the airport name:


Before: `06L 24R 60 240 N041.23.59.539 W081.52.24.562 N041.24.56.750 W081.50.54.151 ;KCLE`

After: `<Runway ID 1> <Runway ID 2> <Runway heading 1> <Runway heading 2> <Nxxx.xx.xx.xxx Wyyy.yy.yy.yyy> <Nxxx.xx.xx.xxx Wyyy.yy.yy.yyy> <ICAO> <name>;<ICAO>`

Note that it is required to remove any preceeding zeroes from the runway numbers to ensure that the SID definitions work correctly

## ESE File

Euroscope also requires a working .ese file to go with the sector file. This must be of the same name as the sector file, just with the .ese extension. The original POF file requries some changes to work properly with Euroscope, listed below.

### SIDs & STARs

The following must be added to the bottom of the ESE:

`SID:<ICAO>:<Runway>:<SID>.<TRANSITION>:<waypoints>`

`STAR:<ICAO>:<RUNWAY>:<TRANSITION>.<STAR>:<waypoints>`
