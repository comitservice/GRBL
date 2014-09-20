This page is a work in progress, not complete yet (as of 19 Sept 2014)

# Machine Set up
Grbl works best if you have homing switches on all 3 axis. There is really no excuse not to, these are not complex or expensive to install.
Once you have your machine Homed, jog each axis off the limit switch by a few mm or 0.1". Then go to the Offsets screen and click Set on the G30 Offset. This enables you to use G30 to go to 'almost home' without the whole process of Homing.  More on G30 on another page.

# Workflow
A typical work flow helps to understand Grbl-Panel and CNC machining in general. Time spent learning some of these topics will save to ruined work pieces as well as time.

* If you have not Homed your machine since turning it on, do so now.
* Mount your work piece to the table. Do this in a way that the cutting tool will not interfere with clamps, etc.
* Jog X axis to where your Work 0 location is. Click 0 to right of Work X axis display.
* Repeat with Y and Z axes.
* You can now load and run your program, it should have a G54 near the top. If not, use MDI to enter it. This ensures that you are using the Work offsets set above. (Programs should generally be written relative to Work 0, not absolute positions.)

# Jogging
Jogging is a manual operation that moves the spindle (or the table relative to the spindle). You jog to set Work 0 before running a program.

Grbl-Panel has several features that assist you with jogging
* Configurable repeat rates for X, Y and Z buttons.
* Configurable Feed Rate and Distance increments
* Radio buttons to easily set Distance and Feed for jogging
* Extra large buttons, no need to 'hunt for the button'

# Setting your Work 0
Milling operations often require you to add features to an existing part. This means you need to 'touch off' each axis in turn to some known location on the work piece. A typical work flow for this is:
* Mount a rod or edge detector in the spindle
* Lower the spindle (Z-) so detector is below the surface of the work piece.
* Jog X or Y axis until the detector is close, then decrease the Distance increment, e.g. to 0.001". Keep moving toward the part until the detector touches.
* Go to the Offset screen, we will use G54, the default Work Offset
* In the appropriate axis text box, enter a value that is Machine Position for that axis plus 1/2 the diameter of the detector rod/edge detector. Double click to send it to Grbl
* Repeat with the other axis.
* Replace the detector with your cutting tool, touch it off to the top of work piece. Set that value into Z text box, double click to send to Grbl.
* To confirm your settings, click Retrieve to reload the Offsets screen with what Grbl knows. 

# Presetting Fixture Offsets
When you need to make more than 1 of something it is often easiest to create a fixture or at least a virtual layout of parts on your work piece. For PCB's this is called panelizing. This is where Grbl-Panel excels, it makes the Work Offsets visible to you without knowing G code to send them to Grbl.
* Use a pointed rod or an edge detector in the spindle so you can see when the spindle is above each work piece 0 location.
* Jog X or Y axis until the detector is close, then decrease the Distance increment, e.g. to 0.001". Keep moving toward the part until the detector touches or is directly above the 0 location.
* On the Offset screen, choose the Work Offset you want to use, e.g. G55.
* In the appropriate axis text box, enter a value that is Machine Position for that axis( plus 1/2 the diameter of the detector rod/edge detector if you are touching on an edge). Double click to send it to Grbl
* Repeat with the other axis.
* Replace the detector with your cutting tool, touch it off to the top of work piece. Set that value into Z text box, double click to send to Grbl.
* To confirm your settings, click Retrieve to reload the Offsets screen with what Grbl knows. 
* Repeat for the other work pieces.
* Run your program once for each location, set the appropriate Work Offset active, e.g. G55, then G56, then G57 etc.



