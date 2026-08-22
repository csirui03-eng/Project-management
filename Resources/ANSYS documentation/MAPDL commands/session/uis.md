---
apdl: "/UIS"
method: uis
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.uis
generated: 2026-08-22
tags: [mapdl-command]
---

# /UIS

PyMAPDL: `mapdl.uis(label='', value='', **kwargs)`

Controls the GUI behavior.

## Parameters

**label**

Behavior control key:

- `BORD` - Controls the functionality of the mouse buttons for dynamic viewing mode only. When `Label` = BORD, the three values that follow control the functionality of the LEFT, MIDDLE and RIGHT buttons, respectively (see below).
- `MSGPOP` - Controls which messages from the Mechanical APDL error-message subroutine are displayed in a message dialog box.
- `REPLOT` - Controls whether or not an automatic replot occurs after functions affecting the model are executed.
- `ABORT` - Controls whether or not the program displays dialog boxes to show the status of an operation in progress and to cancel that operation.
- `DYNA` - Controls whether the dynamic mode preview is a bounding box or the edge outline of the model. This label only applies to 2D display devices (that is, [[show|/SHOW]],XII or [[show|/SHOW]],WIN32). This "model edge outline" mode is only supported in PowerGraphics ( [[graphics|/GRAPHICS]],POWER) and is intended for element, line, results, area, or volume displays.
- `PICK` - Controls how graphical entities are highlighted from within the the Select menu.
- `POWER` - Controls whether or not PowerGraphics is active when the GUI is initiated. Mechanical APDL default status is PowerGraphics "ON"; this command is used (placed in the `start.ans` file) when full graphics is desired on start up.
- `DPRO` - Controls whether or not the input window displays a dynamic prompt. The dynamic prompt shows the correct command syntax for the command, as you are entering it.
- `UNDO` - Controls whether or not the session editor includes nonessential commands or comments in the file it creates. You can use this option to include comments and other materials in the session editor file.
- `LEGE` - Controls whether or not the multi-legend is activated when you start the GUI. The multi-legend enables you to specify the location of your legend items in each of the five graphics windows. You can place this option in your `start.ans` file and have the GUI start with the legend items in a pre-specified location.
- `PBAK` - Controls whether or not the background shading is activated when you start the GUI. You can place this option in your `start.ans` file.
- `ZPIC` - Controls the sorting order for entities that are coincident (directly in front of or behind each other) to a picked spot on your model. When you pick a spot on your model that could indicate two or more entities, a message warns you of this condition, and a list of the coincident entities can be generated. The `VALUE` term (below) will determine the sort order.
- `HPOP` - Controls the prioritization of your GUI windows when the contents are ported to a plot or print file ( [[ui|/UI]],COPY,SAVE). OpenGL (3D) graphics devices require that the Mechanical APDL graphics window contents be set in front of all overlying windows in order to port them to a printer or a file. This operation can sometimes conflict with [[noerase|/NOERASE]] settings. See the `VALUE` term (below) to determine the available control options.

**value**

Values controlling behavior if `Label` = BORD:

(These values control the operation according to syntax : **/UIS**,BORD, LEFT, MIDDLE, RIGHT )

- `1` - PAN, controls dynamic translations.

- `2` - ZOOM, controls zoom, and dynamic rotation about the view vector.

- `3` - ROTATE, controls dynamic rotation about the screen X and Y axes.

  You can designate any value for any button, or designate the same value for all three buttons. If no value is specified, default is LEFT = PAN, MIDDLE = ZOOM and RIGHT = ROTATE.

Values controlling behavior if `Label` = MSGPOP:

- `0` - All messages displayed.
- `1` - Only notes, warnings, and errors displayed.
- `2` - Only warnings and errors displayed (default).
- `3` - Only errors displayed.

Values controlling behavior if `Label` = REPLOT:

- `0` - No automatic replot.
- `1` - Automatic replot (default).

Values controlling behavior if `Label` = ABORT:

- `ON` - Display status and cancellation dialog boxes (default).
- `OFF` - Do not display status and cancellation dialog boxes.
- `1` - Same as ON.
- `0` - Same as OFF.

Values controlling behavior if `Label` = DYNA:

- `0` - Use model edge outline when possible (default).
- `1` - Use bounding box preview.

Values controlling behavior if `Label` = PICK:

- `0` - Picked keypoints and nodes are enclosed by a square. Picked lines are overlaid by a thicker line. Picked areas, volumes, and elements (non-point/non-line) are redrawn with highlighting colors. However, if the pick is a box, circle, or polygon pick, the highlighting for all entitles consists only of a square placed around the entity's centroid.
- `1` - Picked entities are not highlighted.
- `2` - 5.1 highlighting (that is, no XOR).
- `3` - Picked entities are highlighted as in `VALUE` = 0, except that, for a box, circle, or polygon pick, the picked areas, volumes, and elements (non-point/non-line) are redrawn with highlighting colors. This technique is slower than the `VALUE` = 0 technique.

Values controlling behavior if `Label` = POWER:

- `0` - Start GUI in Full Graphics mode.
- `1` - Start GUI in PowerGraphics mode (default).

Values controlling behavior if `Label` = DPRO:

- `0 or OFF` - Do not display the dynamic prompt.
- `1 or ON` - Display the dynamic prompt (default).

Values controlling behavior if `Label` = UNDO:

- `0 or None` - Do not suppress any commands (default).
- `1 or Comment` - Write the nonessential commands to the session editor file as comments (with a ! at the beginning).
- `2 or Remove` - Do not write nonessential commands or comments.

Values controlling behavior if `Label` = LEGE:

- `0 or OFF` - Start GUI with the enhanced legend off (default).
- `1 or ON` - Start GUI with the enhanced legend capability activated.

Values controlling behavior if `Label` = PBAK:

- `0 or OFF` - Start the GUI with the no background shading (default).
- `1 or ON` - Start the GUI with background shading activated.

Values controlling behavior if `Label` = HPOP:

- `0 or OFF` - No rewrite operations are performed to compensate for items that obscure or overlay the graphics window (default).
- `1 or ON` - The Graphics screen contents are replotted to ensure that they are situated in front of all other windows. If [[noerase|/NOERASE]] is detected, this operation is suppressed.

## Notes

Controls certain features of the Graphical User Interface (GUI), including whether Mechanical APDL displays dialog boxes to show you the status of an operation (such as meshing or solution) in progress and to enable you to cancel that operation. Issue **/UIS**,STAT for current status. Issue **/UIS** ,DEFA to reset default values for all labels. Issue **/UIS**, `Label`,STAT and **/UIS**, `Label`,DEFA for status and to reset a specific `Label` item.

A **/UIS**,HPOP,1 command employs a fast redraw method which does not allow entering the legend logic for a [[plopts|/PLOPTS]],INFO,1 or [[plopts|/PLOPTS]],INFO,2 command. However, the legend is redrawn for [[plopts|/PLOPTS]],INFO,3 because that command also allows a fast redraw.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_UIS.html
