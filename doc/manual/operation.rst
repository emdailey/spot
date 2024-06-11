+++++++++++++++++
General Operation
+++++++++++++++++

==================
Keyboard and Mouse
==================


=============
Site Selector
=============

The SiteSelector plugin is used to select the location from where you
are planning to observe, as well as the time of observation at that
location.

You will almost always want to start this plugin first, because it
controls many of the aspects of the other plugins visible on the workspace.

.. image:: SiteSelect.*


Setting the observing location
------------------------------
Use the "Site:" drop-down menu to select the observing location.  There
are a number of predefined sites available.

Adding your own custom observing location
-----------------------------------------
If your desired location is not available, you can easily add your own.
If you have the SPOT source code checked out, you can find the file
"sites.yml" in .../spot/spot/config/.  Copy this file to $HOME/.spot
and edit it to add your own site.  Be sure to set all of the keywords
for your site (latitude, longitude, elevation, etc).  Restart spot and
you should be able to see your new location.

Setting the time of observation
-------------------------------
The time can be set to the current time or a fixed time. To set to the
current time, chose "Now" from the "Time mode:" drop-down menu.

To set a fixed time, chose "Fixed"--this will enable the "Date time:"
and "UTC offset (min):" controls.  Enter the date/time in the first box
in the format YYYY-MM-DD HH:MM:SS and press "Set".

By default the UTC offset of the fixed time will be set to that of the
timezone of the observing location; but you can enter a custom offset
(in *minutes*) from UTC in the other box and press "Set" to indicate
a special offset for interpreting the time.

.. note:: this does NOT change the timezone of the observing location;
          it just sets the interpretation of the fixed time you are
          setting.

Updating of plugins
-------------------
Whenever you change the observing location or the time, the other plugins
should update automatically (if they subscribe for site and time changes,
which most are designed to do).

=========
Polar Sky
=========

Displays a polar sky grid on the sky window. Rings show 
15, 30, 50, 70, and 85 degrees elevation

.. image:: PolarSky.*

===========
Target List
===========

``Target List``, or ``Targets``, is normally used in conjunction with the 
plugins ``PolarSky`` and ``Visibility`` to show information about celestial 
objects that could be observed.  It allows you to load one or more files 
of targets and then plot them on the "<wsname>_TGTS" window, or show their 
visibility in the ``Visibility`` plugin UI.

Loading targets from a CSV file
-------------------------------
Targets can be loaded from a CSV file that contains a column header
containing the column titles "Name", "RA", "DEC", and "Equinox" (they
do not need to be in that order).  Other columns may be present but will
be ignored.  In this format, RA and DEC can be specified as decimal values
(in which case they are interpreted as degrees) or sexigesimal notation
(HH:MM:SS.SSS for RA, DD:MM:SS.SS for DEC).  Equinox can be specified
as e.g. J2000 or 2000.0.

.. note:: SPOT can also read targets from CSV files in "SOSS notation".
          See the section below on loading targets from an OPE file.

Press the "File" button and navigate to, and select, a CSV file with the
above format.  Or, type the path of the file in the box next to the "File"
button and press "Set" (the latter method can also be used to quickly
reload a file that you have edited).

The targets should populate the table.

Loading targets from an OPE file
--------------------------------
An OPE file is a special format of file used by Subaru Telescope.
Targets in this kind of file are specified in "SOSS notation"
(HHMMSS.SSS for RA, +|-DDMMSS.SS for DEC, NNNN.0 for Equinox).

Follow the instructions above for loading targets from a CSV file, but
choose an OPE file instead.

.. note::  In order to load this format you need to have installed the
           optional "oscript" package:
           (pip install git+https://github.com/naojsoft/oscript).

Table information
-----------------
The target table summarizes information about targets. There are columns
for static information like target name, RA, DEC, as well as dynamically
updating information for azimuth, altitude, a color-coded rise/set icon,
hour angle, airmass, atmospheric dispersion, parallactic angle and moon
separation.


===============
Visibility Plot
===============

Shows a visibility plot of the selected targets.

========
Sky Cams
========



==================
Telescope Position
==================



=============
Finding Chart
=============

The finding chart plugin is used to view a sky survey image of a requested 
region of the sky. This plugin is also used in conjuction with 
``Instrument FOV`` and should be opened first.

.. image:: FindingChart.*

Display an image of a specified region
--------------------------------------

The center coordinates of the image can be set by entering the RA, DEC, and 
Equinox under "Pointing". The RA and DEC can be 
specified as decimal values (in which case they are interpreted as degrees) 
or sexigesimal notation (HH:MM:SS.SSS for RA, DD:MM:SS.SS for DEC).  
Equinoxcan be specified as e.g. J2000 or 2000.0.

The image source can be selected from a list of optical, ultraviolet, and 
infrared sky surveys. The image will be a square with the height and width set by 
the ``Size (arcmin)`` selection. Once the RA, DEC, and Equinox have been 
selected, the ``Find Image`` button will search for the requested survey 
image and will display it in the ``WS1_FIND`` window. The ``Create Blank`` 
button will create an blank image.

.. note::   Images will fail to load if the pointing position is outside
            the surveyed regions. 

Finding a target by name
------------------------

An object can be selected by name using the ``Search name`` function under 
"Name Server". SPOT will check either the NASA/IPAC Extragalactic Database 
(NED) (https://ned.ipac.caltech.edu/) or the SIMBAD Astronomical Database 
(http://simbad.cds.unistra.fr/simbad/), and if the object is found the pointing 
information for the target will be automatically filled in. 


==============
Instrument FOV
==============




-------------------------



Selecting an Image source
-------------------------