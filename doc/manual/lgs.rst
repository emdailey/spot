+++
LGS
+++

The LGS (Laser Guide Star) plugin, when used along with the :doc:`targetlist` and 
:doc:`visplot` plugins, is used to plan laser shoot windows. 
The plugin will automatically parse the PAM files from the United States Strategic 
Command Laser Clearinghouse and will display the laser shoot windows in the 
visibility window.

.. image:: figures/lgssample.*

=================
Loading PAM files
=================

To load one or more PAM files, enter the address of the folder containing the PAM 
files in the LGS window under "PAM Dir" and press "Set". If successful, the number of 
files and targets will be displayed beside "PAM Files". 

==================
Window information
==================

PAM Dir:
Fillable input which lets the user select which directory to search for PAM files. 
Once the address has been filled out, pressing the "Set" button on the right side will 
pull the laser shooting windows from the PAM files and match them with targets in 
the target list.

PAM Files: 
The number of loaded files and targets will be listed here.

Target: 
Displays the name of the target selected from the target list in 

Sat window: 
Displays the current laser shooting window and 

Time left: 
Displays the time until the next opening or closing event. 

===============
Enabling Plugin
===============

This plugin in not enabled by default. To enable it, first go to 
"PluginConfig", which may be found by pressing "Operation" at the bottom left 
and then going to "Debug" and then "PluginConfig". 
Find "LGS" from the list of plugins, then press "Edit" and then 
check the checkbox next to "Enabled". Press "Set", then close the window and 
press "Save". Restart SPOT and the plugin should appear on the control panel. 