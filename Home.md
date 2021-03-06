### A machine-like panel to control Grbl
Yes, another one. I needed more definite control over my CNC router. And I wanted it adaptable, configurable and understandable.
This panel treats the CNC machine as a generic device. The jog buttons are arranged in a way that reflects a fixed spindle milling machine. Many items are configurable and those changes persist when you close the Panel.
The code is VB.Net, created using Visual Studio 2015 Community Edition targeting .Net 4.5.2
![Main Panel](https://github.com/gerritv/Grbl-Panel/blob/master/Grbl-Panel-Example.JPG)
## Why Panel?
Grbl needs a separate application, something to feed it gcode from a file, provide a means of jogging to set up workpieces on the table, change tools etc. The Panel controls the setup, loading of a file, jogging, setting offsets for job to be run, the interface between human and machine. These are all functions that interface via serial interface to Grbl.  Many machines have a physical panel that has buttons and displays for these functions. For Grbl, we use a soft panel. Other implementations are Universal Code Sender, Grbl-Homing and Grbl Controller. The approach taken instead for this implementation has more in common with Fanuc, Haas and Mach3 and LinuxCNC.

### General Overview
A typical milling work setup requires jogging to where work 0 is located. This often requires 'touching off' on each axis in turn. Hence there are 0 buttons beside each Work axis. Once you are running a GCode file, you should not be able to jog or send manual commands. These are interlocked. When an Alarm condition is detected by Grbl, the Gcode file run is stopped.

Controls and displays are grouped into sub panels. These get enabled/disabled depending on what the Panel is doing. A Settings tab provides you with some editable fields that alter the operation of the panel or what it sends to Grbl. There are additional tabs, e.g. Tools which are presently not implemented.


### Grbl
Grbl is the basis for many CNC machines. It is the basis of many controllers. It's enhancements are managed in a controlled manner, leading Grbl to be a stable and predictable high performance GCode interpreter. its feature set is strictly limited, in part due to the constraints of the Atmel 328P that it runs on.  Currently maintained by Sonny Jeon (@chamnit). His support and feedback helped focus the development of Grbl-Panel. The excellent Grbl wiki also made the job of coding the interface much simpler. Others who helped are listed in the Help/About/Credits

### Why VB.Net and Visual Studio
Microsoft provides free, extremely well-documented professional quality tools. The visual development environment enabled me to build a fully functional Panel in less than a week of 9-5 effort. That is while learning the details of Delegates, cross thread calls from Serial IO to GUI, the many properties of the controls in use etc.

## Authors and Contributors
The author is Gerrit Visser (@gerritv), a retired computer professional (both hardware and software) who has many interests and hobbies. One of those is machining which inevitably leads to CNC.

## Support or Contact
Please use the Issues tracker to report problems or suggest enhancements.

## TODO
In no particular order this is a list of possible/probable enhancements:
* Allow jogging after a M0 (pause) or M6 (tool change) is to be sent to Grbl
* Tool Change, M06. This involves moving the tool to some location and then doing a G38.2 probe