++++++++++++++++
Target Generator
++++++++++++++++

The target generator plugin adds a target to the target 
list at a specified azimuth and elevation. The generated 
target will be locked its initial Right Ascension and 
Declination and will move across the sky as time passes. 

.. image:: figures/TargetGen.*

To create a target, enter the desired Azimuth and Elevation 
in the target generator plugin window, choose a name and then 
press "Gen Target". 

Targets created using this plugin will appear in the 
:doc:`targetlist` plugin window in the "Targets" group. If the 
target does not appear, you may need to press the "List 
All Targets" button. 

Each target must have a unique name. To edit an existing target, 
enter the new coordinates into the target generator and add 
the name of the target to be edited in the "Name" field, then 
press "Gen Target". 

Requirements
============

naojsoft packages
-----------------
- g2cam
- ginga