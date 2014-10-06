# The Settings Tab

This page has several logical groupings of settings that you can use to alter GrblPanel's or Grbl's behaviour.

## GrbL Settings
This section reflects Grbl's settings. GrblPanel populates this automatically after a successful connection to Grbl. You can change settings by clicking on a Value, altering the value and then double-click to send the value to Grbl.

For future proofing, there is a Last Grbl Param which should be set to the last Parameter value you expect to get from Grbl. This might change in the future with Grbl enhancements, hence the configuration option.

A refresh button lets you get the latest from Grbl

_In the next sections, you change values by editing a box and pressing Return key or double-clicking the text box. The Refresh buttons when clicked will ensure that your new settings take effect immediately. All these settings are saved on program exit in your User data directory. (They do not overwrite the GrblPanel.xml file in your program directory so your custom settings should survive program updates.)_

## Position

This section provides you with settings that alter what commands are used for the various Position related actions. 

You might want to modify the G28 and G30 commands by adding X, Y and/or Z parameters to indicate where you want the Controlled Point to move to before going to the final destination. 
* Be careful using Z0 for G28/G30 as it is often the point where the tip of the tool touches your work surface.

## Misc
This section provides various settings to control GrblPanel's behaviour.
* The default Poll Interval provides decent visual tracking of the work position changes while running a program. Setting this too small might interfere with Grbl's operation, slowing down the Controlled Point's motion.
* Left Handed GUI swaps the 2 main groups of controls on the Interface tab.

## Jogging
The 4 feed increment and rate values available on the Interface tab are set from here. The defaults were chosen to give good control while positioning the Controlled Point relative to a work piece.

The Repeat rate is set to a reasonable value to avoid overrunning your desired end position but still proving a repeat. Too fast and you will crash into limits (or wish you had limit switches :-)

The Enable Keyboard arrows option enables the use of the usual arrow keys as well as Pg Up and Pg Dn. These repeat at the standard Windows repeat rate, not affected by the repeat rate settings here.

## Offsets(2)

G28 and G30 are 2 location settings that are very useful. Typically G28 is set after you Home Cycle and back off from the Limit switches. Click Set and the absolute machine positions at the time are recorded in EEProm. In other words you don't need to do this every time you power up your machine.

G30 is similar, but it is typically used to set an absolute location for Tool Changes. Jog to that location, go back to Settings tab and click Set for G30.

Both G28 and G30 are executed from the Interface tab using Goto Spcl Posn1/2. These operations take place at high speed, unlike Homing Cycle. Think of Spcl Posn1 as a soft home operation. Please do consider carefully with both these commands that you need to send Z axis to somewhere safe, i.e. above your work piece and clamps. If you want, that value can be set in the Position block on this Settings page.


