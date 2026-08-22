---
apdl: "/COLOR"
method: color
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.color
generated: 2026-08-22
tags: [mapdl-command]
---

# /COLOR

PyMAPDL: `mapdl.color(lab='', clab='', n1='', n2='', ninc='', **kwargs)`

Specifies the color mapping for various items.

**Command default:**

Use the default color mapping.

## Parameters

**lab**

Apply color to the items specified by the following labels:

- `AXES` - Determines the color (specified in next argument, `Clab` ) that the axes of a graph will be plotted in.
- `AXNUM` - Determines the color (specified in next argument, `Clab` ) that the numbering on the axes of a graph will be plotted in.
- `NUM` - Discretely numbered items (such as element types, element materials, etc., as shown on the [[pnum|/PNUM]] command). Also specify number (1 to 11) in the `N1` field. For example, **/COLOR**,NUM,RED,3 will assign the color red to all items having the discrete number 3 (material displays would show elements having material 3 as red).
- `OUTL` - Outline of elements, areas, and volumes. Ex: **/COLOR**,OUTL,BLUE.
- `ELEM` - Elements. Use `N1`, `N2`, `NINC` fields for element numbers.
- `LINE` - Solid model lines. Use `N1`, `N2`, `NINC` fields for line numbers.
- `AREA` - Solid model areas. Use `N1`, `N2`, `NINC` fields for area numbers.
- `VOLU` - Solid model volumes. Use `N1`, `N2`, `NINC` fields for volume numbers.
- `ISURF` - Isosurfaces (surfaces of constant stress, etc.). This option is particularly useful when capturing frames for animating a single isosurface value.
- `WBAK` - Window background. Use `N1`, `N2`, `NINC` fields for window numbers. The options that you select using `Lab` = PBAK will supersede those applied using `Lab` = WBAK.
- `b.c.label` - Boundary condition label. Enter U, ROT, TEMP, PRES, V, VOLT, MAG, A, EMF, CURR, F, M, HEAT, FLOW, VF, AMPS, FLUX, CSG, CURT, MAST, CP, CE, NFOR, NMOM, RFOR, RMOM, PATH. See the [[pbc|/PBC]] command for boundary condition label definitions.
- `GRBAK` - Graph background.
- `GRID` - Graph grid lines.
- `AXLAB` - Graph X and Y axis labels.
- `CURVE` - Graph curves (identify curve numbers (1-10) in `N1`, `N2`, `NINC` fields).
- `CM` - Component group. Use `N1` field for component name, ignore `N2` and `NINC`.
- `CNTR` - Mechanical APDL contour stress colors. The maximum number of contours available is 128. The number of colors that can be specified interactively (GUI) is 9. ( [[contour|/CONTOUR]], 9). Any other setting will yield inconsistent results.
- `SMAX` - Specifies that all stress values above the maximum value entered in [[contour|/CONTOUR]] will be displayed in the color designated in the `Clab` field. Defaults to dark grey.
- `SMIN` - Specifies that all stress values below the minimum value entered in [[contour|/CONTOUR]] will be displayed in the color designated in the `Clab` field. Defaults to dark grey.
- `PBAK` - Activates background shading options (see command syntax at end of argument descriptions below). The options that you select using `Lab` = PBAK will supersede those applied using `Lab` = WBAK.

**clab**

Valid color labels are:

- `BLAC (0)` - Black
- `MRED (1)` - Magenta-Red
- `MAGE (2)` - Magenta
- `BMAG (3)` - Blue-Magenta
- `BLUE (4)` - Blue
- `CBLU (5)` - Cyan-Blue
- `CYAN (6)` - Cyan
- `GCYA ((7)` - Green-Cyan
- `GREE (8)` - Green
- `YGRE (9)` - Yellow-Green
- `YELL (10)` - Yellow
- `ORAN (11)` - Orange
- `RED (12)` - Red
- `DGRA (13)` - Dark Gray
- `LGRA (14)` - Light Gray
- `WHIT (15)` - White

**n1**, **n2**, **ninc**: Apply color to `Lab` items numbered `N1` to `N2` (defaults to `N1` ) in steps of `NINC` (defaults to 1). If `N1` is blank, apply color to entire selected range. If `Lab` is CM, use component name for `N1` and ignore `N2` and `NINC`. If `N1` = P, graphical picking of elements, lines, areas and volumes is enabled; your can assign colors to the entities via the picker. When picking is enabled, the `Lab` and `Clab` fields are ignored.

## Notes

Issue **/COLOR**,STAT to display the current color mapping. Issue **/COLOR**,DEFA to reset the default color mapping. Color labels may also be reassigned any "color" with the [[cmap|/CMAP]] command.

This command is valid anywhere.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_COLOR.html
