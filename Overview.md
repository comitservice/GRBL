The main tab of GrblPanel is Interface. This tab has everything you need for typical operation of a CNC controlled device attached to Grbl. Many of the buttons etc. have ToolTips that show if you hover over them for a moment.

GrblPanel helps you stay out of trouble by locking access to its various controls depending on the state of operation.

Connection to Grbl is initiated in the Grbl grouping. The drop-down will show the last port that you connected to successfully. If you happen to start the app before connecting to Grbl, use Rescan to find the new port. Once you press Connect, the app opens the serial port, blips DTR to hard reset Grbl and then waits 1.5 seconds for the controller to wake up from its slumber.

After the 1.5 second delay, GrblPanel sends $$ and $G commands to solicit the relevant information. $G response populates the State grouping which $$ populates the GrblSettings grouping on the Settings tab. The status poller also starts up, resulting in the Position display coming alive along with the Unlock button highlighted. Home Cycle is also made visible and highlighted if you have Homing enabled in Grbl ($22=1 in 0.9). The highlighting serves to remind you that you need to Home Cycle on power up of the controller.

The **Status view** generally has nothing in it unless you get errors, Alarms or enable Verbose. The Q and RX progress bars reflect the status of those 2 queues in Grbl. The Status display box will show the current status being reported in the poll ('?') responses.

The **Position display** shows the current Work Offset position in large font and the absolute machine position in smaller font. The 0 buttons to the right of each axis display is used to Zero that axis' position in the Active Work Offset. The Zero XYZ button sets all 3 axes to 0 in the Active WorkOffset. Typically this is G54, the default but it could be one of the others supported by Grbl. You can change to a different offset in the State panel on the RH of the screen. The units displayed are from Grbl's Report Inches settings.

The **Jogging grouping** is for doing just that, jogging. You can set the increment and feed rate using checkboxes as well as the Units, Metric or Inches. These settings are independent from/do not alter Grbl's Report option. The Jog buttons autorepeat based on fields on the Settings tab. The default is 2.5/sec. On the Settings tab you can also enable Keyboard arrows for jogging that way. (The keyboard repeat rate is not alterable, that rate applies to all Windows apps.)

The **State grouping ** reflects Grbl's response to $G initially. It subsequently follows gcode sent using MDI or from a gcode file. The dropdown boxes allow you to send the relevant setting to Grbl, e.g. useful when testing your Coolant mister. These parameters are usually found at the start of a Gcode file so they may change once you start a run. (FeedRate, Spindle RPM and Tool Number are presently settable via the MDI or Gcode file, not from these text boxes.)

The **Gcode grouping** provides controls to open a file, Run, Pause, or Stop a file. The # of lines is shown and each gcode line is numbered in the view. As a command is responded to by Grbl, the Sts field reflects that. The column can be resized to show the full error text. Gcode file execution stops on Alarm, and Pauses on errors (there is an option on the Settings tab for the latter case). A comment line in the file will populate the Message box, useful to give you feedback on what MOP you are presently cutting.

Lastly, the **MDI grouping** provides a means of manually entering and sending commands. You can use Return key to send or the Send button. Gcode entered here is reflected in the State grouping as well as in the Gcode view below.
