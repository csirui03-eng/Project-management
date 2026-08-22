---
apdl: "/UI"
method: ui
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.ui
generated: 2026-08-22
tags: [mapdl-command]
---

# /UI

PyMAPDL: `mapdl.ui(func='', type_='', format_='', screen='', color='', krev='', orient='', compress='', quality='', **kwargs)`

Activates specified GUI dialog boxes.

## Parameters

**func**

Label identifying the dialog box to be activated:

- `HELP` - Activates the online help system.
- `VIEW` - Activates the Pan, Zoom, Rotate dialog box
- `WPSE` - Activates the Working Plane Settings dialog box.
- `WPVI` - Activates the Offset Working Plane dialog box.
- `RESULT` - Activates the Query Picking Menu for reviewing results.
- `QUERY` - Activates the Query Picked Entities (preprocess) dialog box.
- `COPY` - Activates the Hard Copy dialog box.
- `ANNO` - Activates the 2D Annotation dialog box.
- `AN3D` - Activates the 3D Annotation dialog box.
- `SELECT` - Activates the Select Entities dialog box.
- `NSEL` - Activates a picking menu to select nodes.
- `ESEL` - Activates a picking menu to select elements.
- `KSEL` - Activates a picking menu to select keypoints.
- `LSEL` - Activates a picking menu to select lines.
- `ASEL` - Activates a picking menu to select areas.
- `VSEL` - Activates a picking menu to select volumes.
- `REFRESH` - Refreshes the graphics window (non-UI mode only).
- `COLL` - Controls the collapse of the Mechanical APDL main menu when a [[finish|FINISH]] command is issued. See Type below for a discussion of the arguments.

**type_**

Label identifying the type of select operation. Valid only for the following `Func` labels; NSEL, ESEL, KSEL, LSEL, ASEL, and VSEL:

- `S` - Select a new set.
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.

Label identifying the type of results data to be queried. Valid only for `Func` = RESULT:

- `NODE` - Nodal solution data (h-elements only).
- `ELEMENT` - Element solution data.

Label specifying the behavior of the Mechanical APDL main menu after a [[finish|FINISH]] command is issued. User interaction with the main menu is unaffected. Valid only for `Func` = COLL:

- `YES, 1 or blank` - Allows the Main Menu to collapse after [[finish|FINISH]] command.
- `NO or 0` - Prevents Main Menu collapse after [[finish|FINISH]] command.

**format_**

- `TIFF` - Tagged Image File Format.
- `BMP` - (PC only) Bitmap (Windows) file format.
- `WMF` - (PC only) Windows Metafile format.
- `EMF` - (PC only) Enhanced Metafile format.
- `JPEG` - JPEG (Joint Photographic Experts Group) file format.

**screen**

- `FULL` - Saves the entire screen in the specified format.
- `GRAPH` - Saves only the Mechanical APDL graphic window.

**color**

- `MONO` - A two color (black and white) file is saved.
- `GRAY` - The specified file format is saved in gray scale.
- `COLOR` - The file is saved at the specified color depth.

**krev**

- `NORM` - Saves file as shown on the screen.
- `REVERSE` - Saves file with the background color reversed.

**orient**

- `LANDSCAPE` - Saves file in landscape mode.
- `PORTRAIT` - Saves file in portrait mode.

**compress**

- `YES` - Compresses TIFF files and EPS files with TIFF preview (default).
- `NO` - Saves files with no compression.

**quality**: - `1,2,,,100` - JPEG quality index, with 100 being the maximum quality level.

## Notes

Allows you to activate specified GUI dialog boxes directly in either GUI or non-GUI mode.

The **/UI** command itself is valid in any processor, however certain dialog boxes are accessible only in a particular processor (for example, **/UI**,RESULT,... is valid only in the General Postprocessor).

Mechanical APDL JPEG software is based in part on the work of the Independent JPEG Group, Copyright 1998, Thomas G. Lane.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_UI.html
