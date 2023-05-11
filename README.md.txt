-----------------------------------------------------------------
Add the following to your config G before M98  P"/sys/Toffsets.g"

M98 P"/sys/Parameters.g"

M98 P"/sys/Parking position_0.g"
M98 P"/sys/Parking position_1.g"
M98 P"/sys/Parking position_2.g"
M98 P"/sys/Parking_position_3.g"
M98 P"/sys/Parking position_4.g"
M98 P"/sys/Parking_position_5.g"

-----------------------------------------------------------------

Replace X and Y offset coordinates in Toffsets.g, this makes sure the tools are picked up correctly

X{global.OffsetX_Tool0} Y{global.OffsetY_Tool0}
X{global.OffsetX_Tool1} Y{global.OffsetY_Tool1}
X{global.OffsetX_Tool2} Y{global.OffsetY_Tool2}
X{global.OffsetX_Tool3} Y{global.OffsetY_Tool3}
X{global.OffsetX_Tool4} Y{global.OffsetY_Tool4}
X{global.OffsetX_Tool5} Y{global.OffsetY_Tool5}

-----------------------------------------------------------------

Replace the X and Y coordinates in all the tpost files with the following

{global.DockX_Tool0 + global.OffsetX_Tool0}
{global.DockY_Tool0}

The number of the tool is the number corresponding with the file

-----------------------------------------------------------------

Replace all the X coordinates in all the tfree file with the following

{global.DockX_Tool0 + global.OffsetX_Tool0}

For the Y coordinates in the same file only replace the coordinate before the tool_unlock.g macro

{global.DockY_Tool0}

The number of the tool is the number corresponding with the file

-----------------------------------------------------------------

Upload the sys files to the duets system folder. These will get overwritting when the macro is run but do need to be added first.
	
-----------------------------------------------------------------

Upload the macro files to a new macro folder
In each macro file you need to change the distance to the bed coordinates for X and Y and change them from - to +
these coordinates cna be found in the config.g in M208 X<distance to bed 0 X>:316.5 Y<distance to bed 0m Y):357 Z-0.2:315 ;





