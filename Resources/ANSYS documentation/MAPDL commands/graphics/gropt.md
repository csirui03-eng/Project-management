---
apdl: "/GROPT"
method: gropt
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.graphs.Graphs.gropt
generated: 2026-08-22
tags: [mapdl-command]
---

# /GROPT

PyMAPDL: `mapdl.gropt(lab='', key='', **kwargs)`

Sets various line graph display options.

## Parameters

**lab**

Apply display style as selected from the following labels:

- `AXDV` - Axis division (tick) marks (defaults to `KEY` = ON).
- `AXNM` - Axis scale numbers (defaults to `KEY` = ON, which puts numbers at the back plane of the graph). If `KEY` = FRONT, numbers are on the front plane of the graph.
- `AXNSC` - Axis number size scale factor. Input the scale value for `KEY` (defaults to 1.0).
- `ASCAL` - Automatic scaling of additional Y-axes for multi-curve ( [[grtyp|/GRTYP]], 2 or 3) graphs (defaults to `KEY` = ON). If `KEY` = OFF, use base Y-axis scaling (see the [[yrange|/YRANGE]] command).
- `LOGX` - Log X scale (defaults to `KEY` = OFF (linear)).
- `LOGY` - Log Y scale (applies only to the base Y axis) (defaults to `KEY` = OFF (linear)).
- `FILL` - Color fill areas under curves (defaults to `KEY` = OFF).
- `CGRID` - Superimpose background grid ( [[grid|/GRID]] ) over areas under filled curves (defaults to `KEY` = OFF).
- `DIG1` - Number of significant digits before decimal point for axis values. Input the value for `KEY` (defaults to 4).
- `DIG2` - Number of significant digits after decimal point for axis values. Input the value for `KEY` (defaults to 3).
- `VIEW` - View key for graph displays (defaults to `KEY` = OFF, in which case the view is (0,0,1) for 2D graph displays or (1,2,3) for 3D graph displays). If `KEY` = ON, the view settings for graph displays are the same as the view settings for the model.
- `REVX` - Plots the values on the X-axis in reverse order.
- `REVY` - Plots the values on the Y-axis in reverse order.
- `DIVX` - Determines the number of divisions (grid markers) that will be plotted on the X axis.
- `DIVY` - Determines the number of divisions (grid markers) that will be plotted on the Y axis.
- `LTYP` - Specifies whether program-generated ( `KEY` = 1) or system-derived ( `KEY` = 0) fonts are used for the axis labels.
- `CURL` - Determines the position of the curve labels. If ( `KEY` = 1), the curve label will be plotted in the legend column, and the label will be displayed in the same color as the curve. If ( `KEY` = 0) the curve labels will be plotted near the curve. (default).
- `XAXO` - When you use this label, the subsequent `KEY` value will determine an offset amount from the default (along the bottom) location for the X axis. If `KEY` = 1.0, a full offset occurs (the X axis is moved to the top of the graph). If `KEY` = 0.5, the axis is offset to the midpoint of the graph, and if `KEY` = 0 the axis remains in the original position, along the bottom of the graph. For any offset, a grey copy of the original axis (containing the axis numbering) remains at the original location.
- `YAXO` - When you use this label, the subsequent `KEY` value will determine an offset amount from the default (along the left side of the graph) location for the Y axis. If `KEY` = 1.0, a full offset occurs (the Y axis is moved to the right side of the graph). If `KEY` = 0.5, the axis is offset to the midpoint of the graph, and if `KEY` = 0 the axis remains in the original position, along the left side of the graph. For any offset, a gray copy of the original axis (containing the axis numbering) remains at the original location.

**key**

Option values:

- `OFF (0)` - Do not apply selected style.
- `ON (1)` - Apply selected style.
- `nnnn` - If `Lab` is DIG1 or DIG2, input the number of digits.
- `nn` - If `Lab` is AXNSC, input the scale factor.
- `FRONT` - If `Lab` is AXNM, FRONT may also be input.
- `Ndiv` - If `Lab` is DIVX or DIVY, determines the number of divisions (1-99) that will be applied to the axis.
- `Kfont` - If `Lab` is LTYP, `Kfont` is ON (1) or OFF(0). ON uses program-generated fonts for the axis labels, while OFF uses SYSTEM (Windows, X-system, etc.) fonts. Default: `Kfont` = ON (Mechanical APDL fonts).

## Notes

Sets various line graph display options. Issue **/GROPT**,STAT to display the current settings.

Issue **/GROPT**,DEFA to reset default specifications.

Unless you issue **/GROPT**,VIEW,ON, the program indicates that graph-view manipulation is inactive.

See [[axlab|/AXLAB]], [[grtyp|/GRTYP]], [[grid|/GRID]], and [[gthk|/GTHK]] for other graph-control options.

Automatic scaling using the [[xrange|/XRANGE]] and [[yrange|/YRANGE]] commands often yields inappropriate range values for logarithmic scales ( **/GROPT**, LOGX or **/GROPT**, LOGY).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GROPT.html
