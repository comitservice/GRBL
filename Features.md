## Features
* Provides Jog using distance and feed settings via radio buttons
* Strips whitespace from Gcode blocks
* Provides configurable gcode blocks for Jog and Workspace 0
* Provides individual 0 set buttons for each WorkOffset Axis
* Sub panels and controls interlock to prevent inadvertent sending of commands
* Provides setting, retrieving (from Grbl), loading and saving Work Offsets
* Provides key repeat for Jogging with configurable repeat rate
* Settings and preferences are persistent between executions
* Makes no changes to Gcode
* Built on .Net 3.5 which will assist Mono users
* Live Status monitoring

## Limitations
* Does not change Gcode, e.g. no trimming of decimal places
* Does not remove unsupported Gcodes
* Does not yet support Grbl's Advanced Send protocol (this is In Progress with a rewrite of GrblGcode.vb)
* Mono requires GrblPanel to replace its serial receive code, this is planned
* No expansion yet of Canned Drill cycles or M06 Tool Change

The last item above is planned, and is part of the reason for writing Grbl-Panel.


