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

The SkyCam plugin is used to place a background image on the TGTS channel 
to monitor sky conditions. There is a drop-down menu with several sites 
to choose from.

Adding new cameras
------------------

If the camera you want to use is not on this list....

Set Channel Preferences
-----------------------

Say something about how to change the settings.

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

The image source can be selected from a list of optical, ultraviolet,  
infrared, and radio sky surveys. The image will be a square with the height 
and width set by the ``Size (arcmin)`` selection. Once the RA, DEC, and 
Equinox have been selected, the ``Find Image`` button will search for the 
requested survey image and will display it in the ``WS1_FIND`` window. The 
``Create Blank`` button will create an blank image.

.. note::   Images will fail to load if the pointing position is outside
            the surveyed regions. Details about each of the surveys including 
            survey coverage can be found in the links below.
                     
            | SkyView:      https://skyview.gsfc.nasa.gov/current/cgi/survey.pl
            | PanSTARRS:    https://outerspace.stsci.edu/display/PANSTARRS/
            | STScI:        https://gsss.stsci.edu/SkySurveys/Surveys.htm
            | SDSS 17:      https://www.sdss4.org/dr17/scope/

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

The Instrument FOV plugin is used to overlay the field of view of an 
instrument over a survey image in the Finding Chart channel. 

Selecting the Instrument
------------------------

The instrument can be selected from the drop down menu. A red outline 
of the instrument's field of view will appear in the Finding Chart 
channel. The position angle can be adjusted, rotating the survey 
image relative to the instrument overlay. The image can be flipped 
across the vertical axis by checking the ``Flip`` box.

The RA and DEC will be autofilled by the ``Find Image`` channel, but 
can also be adjusted manually by entering in the coordinates. The
RA and DEC can be specified as decimal values or sexigesimal notation.

.. image:: FOV.*


Loading Instruments 
-------------------
(Can the instrument list be edited?)




===========
HSC Planner
===========

HSCPlanner works according to the following steps:

1. establish the pointing of the telescope
2. create a blank field or DSS field from the established pointing
3. place one or more targets within the field
4. set the acquisition parameters and visualize
5. repeat 4. or from earlier steps as needed or desired

We will go over each of these steps in turn.

1. Establishing Pointing
------------------------

To establish pointing, you can type RA and DEC coordinates (sexigesimal)
into the corresponding boxes under the "Position" section of the GUI and
click "Set Pointing".

Another way that is fairly easy is to drag a FITS image that has a
reasonably accurate WCS with pointing for the desired field into the
main window. Click anywhere on the image to set the RA and DEC boxes,
and you can then click "Set Pointing".

You can use this image as the background image (and skip Step B) if
the FOV is wide enough to show your target of interest (HSC FOV is
approx 1.5 deg).


2. Create Field from Pointing
-----------------------------

Once pointing is established, we need to create a background field with
correct WCS to do the correct overplotting to visualize the acquisition.
You can either load your own background image (already discussed),
create a blank field, or download a DSS image of the field (if available).

To create a blank image click "Create Blank". To download a DSS field
click "Get DSS". To use the DSS function you will need a functioning
internet connection.


.. note::   The default location for DSS download is from ESO's web 
            site and it may take up to a minute to download and update 
            the background image. If you experience trouble acquiring a 
            DSS image it is recommended that you download your own 
            background FITS image and load it in step A.


3. Placing Targets within the Field
-----------------------------------

To place targets within the field, you can type RA and DEC coordinates
as in step A above or simply click in the field where you want a target
(as in step A the RA and DEC boxes will be filled when you click).
Press "Add Target" to add the current RA/DEC as a target. You can fine
tune the target position by simply moving it using the cursor.
To completely clear the target list, press "Clear All".

4. Set the Acquisition Parameters and Visualize
-----------------------------------------------

Now we are finally ready to set the acquisition parameters and visualize
the field throughout the dither. In the section labeled "Acquisition"
you can set any of the parameters normally used for HSC acquisition.

The parameters are:

Dither type:
    1 for a single shot, 5 for a 5-point box pattern, and N
    for an N-point circular pattern

Dither steps: 
    Only settable for N-type dither, set it to the number
    of dither positions

INSROT_PA: 
    This parameter will set up the instrument rotator to set
    the rotation of the field on the CCD plane--see the instrument
    documentation for details

RA Offset, DEC Offset: 
    Offsets in arc seconds from the pointing
    position in the center of the field

Dith1, Dith2 (Delta RA, Delta DEC or RDITH, TDITH): 
    The names of these parameters change according to the dither type selected.
    For Dither Type 1 they are not used.  For Dither Type 5, these
    parameters specify the offsets in arc seconds for Delta RA and Delta DEC
    to accomplish the dither between positions.  For Dither Type N they
    specify the offset in arc seconds (RDITH) and the angle offset in
    degrees (TDITH) for the circular dither.  See the instrument documentation
    for more information.

Skip: 
    The number of shots to skip from the beginning of a dither.
    Leave at the default for the full dither.

Stop: 
    Used to terminate a dither early after a certain number of shots.
    Leave at the default for the full dither.

Once you have set the parameters as desired, press the "Update Image"
button to update the overlays. You can then use the "Show Step" control
to step through your dither.

.. note::   It may be helpful to view the field first with the image 
            zoomed out, and then later to pan to your target (hint: 
            use Shift+click to set pan position) and zoom in to more 
            closely watch the detailed positioning of the target(s) on 
            the detector grid.

5. Repeat as Desired
--------------------

You can go back to any step and repeat from there as needed.  It may be
helpful when repositioning targets to press the "Clear Overlays" button,
which will remove the detector and dither position overlays.  Pressing
"Update Image" will bring them right back.