﻿# Train Movement Measurer - The Serial Port

The serial port runs at 9600 baud, 8 data bits, no parity, 1 stop bit.

## Input

No input is expected or checked for.

## Output

Each output line follows the format ```<TYPE>: <MESSAGE>```.

### READY
Denotes that the unit is setup and ready for use, lists the configuration of the unit in a space delimited list of ```<DESCRIPTION>:<VALUE>``` fields.

### ERROR
An error condition has occurred, see the message for more details.
e.g. if something is in the tunnel on start up

### STATUS
Mainly for debugging, the message cycles between:
* Waiting for train.
* Timing train.
* Calculating.

Additionally when a test mode is used you'll get something like "Testing triggers.".

### VA_DATA
A list of the configured, measured and calculated data, it's space delimited and units are included, in order the fields are:
* scale (e.g. 1:148)
* distance of the first section (millimetres)
* distance of the second section (millimetres)
* total time (milliseconds)
* time taken in first section (milliseconds)
* time taken in second section (milliseconds)
* velocity over whole distance (meters per second)
* velocity over first section (meters per second)
* velocity over second section (meters per second)
* acceleration (meters per second per second)
* scale velocity (kilometres per hour)
* scale acceleration (kilometres per hour per second)
* scale velocity (miles per hour)
* scale acceleration (miles per hour per second)

Where first and second are determined by the order the train triggered them not their order on the track.

### V_DATA
A list of the configured, measured and calculated data, it's space delimited and units are included, in order the fields are:
* scale (e.g. 1:148)
* distance travelled (millimetres)
* time taken (milliseconds)
* velocity (meters per second)
* scale velocity (kilometres per hour)
* scale velocity (miles per hour)
