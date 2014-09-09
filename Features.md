## Features
* Provides Jog using distance and feed settings via radio buttons
* Strips whitespace from Gcode blocks
* Provides configurable gcode blocks for Jog and Workspace 0
* Provides individual 0 set buttons for each Workspace Axis
* Sub panels and controls interlock to prevent inadvertent sending of commands
* Settings and preferences are persistent between executions
* Makes no changes to Gcode

## Limitations
* Does not change Gcode, e.g. no trimming of decimal places
* Does not remove unsupported Gcodes
* Does not yet support Grbl's Advanced Send protocol
* Jog buttons do not yet auto-repeat
* Jog buttons are yet not linked to keyboards keys
* No expansion yet of Canned Drill cycles or M06 Tool Change
* Built on .Net 4.5 which will potentially impact Mono users

The last 3 items above are planned, and are part of the reason for writing Grbl-Panel.


