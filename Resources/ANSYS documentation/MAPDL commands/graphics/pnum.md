---
apdl: "/PNUM"
method: pnum
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.pnum
generated: 2026-08-22
tags: [mapdl-command]
---

# /PNUM

PyMAPDL: `mapdl.pnum(label='', key='', **kwargs)`

Controls entity numbering/coloring on plots.

## Parameters

**label**

Type of numbering/coloring:

- `NODE` - Node numbers on node and element plots.

- `ELEM` - Element numbers and colors on element plots.

- `SEC` - Section numbers and colors on element and solid model plots (see [[pnum#Notes|/PNUM]] ).

- `MAT` - Material set numbers and colors on element and solid model plots (see [[pnum#Notes|/PNUM]] ).

- `TYPE` - Element type reference numbers and colors on element and solid model plots (see [[pnum#Notes|/PNUM]] ).

- `REAL` - Real constant set numbers and colors on element and solid model plots (see [[pnum#Notes|/PNUM]] ).

- `ESYS` - Element coordinate system numbers on element and solid model plots (see [[pnum#Notes|/PNUM]] ).

- `LOC` - Location numbers/colors of the element in matrix assembly order on element plots.

  LOC and ELEM numbers will be the same unless the model has been reordered.

- `KP` - Keypoint numbers on solid model plots.

- `LINE` - Line numbers on solid model plots (both numbers and colors on line plots).

- `AREA` - Area numbers on solid model plots (both numbers and colors on area plots).

- `VOLU` - Volume numbers on solid model plots (both numbers and colors on volume plots).

- `SVAL` - Stress (or any contour) values on postprocessing plots, and surface load values and colors on model plots when surface load symbols are on ( [[psf|/PSF]] ). For tabular boundary conditions, the table- evaluated values will be displayed on node, element, or contour displays in POST1 when load symbols ( [[pbf|/PBF]], [[psf|/PSF]], [[pbc|/PBC]] ) are on and TABNAM is OFF.

- `TABNAM` - Table names for tabular boundary conditions. If this label is turned on, the table name appears next to the appropriate symbol, arrow, face outline, or contour as dictated by the [[psf|/PSF]], [[pbc|/PBC]], and [[pbf|/PBF]] commands.

- `STAT` - Shows current settings for **/PNUM**.

- `DEFA` - Resets all **/PNUM** specifications back to default.

**key**

Switch:

- `0` - Turns OFF numbers/colors for specified label.
- `1` - Turns ON numbers/colors for specified label.

## Notes

This command specifies entity numbering and coloring for subsequent plots.

The MAT, TYPE, REAL, and ESYS labels activate both the numbering and coloring of the corresponding attributes for [[eplot|EPLOT]], [[kplot|KPLOT]], [[lplot|LPLOT]], [[aplot|APLOT]], and [[vplot|VPLOT]]. The ELEM, MAT, TYPE, REAL, ESYS, and LOC labels are mutually exclusive, that is, only one can be specified at a time. Also, turning on a LINE, AREA, or VOLU label will turn off the MAT, TYPE, and REAL labels.

PowerGraphics ( [[graphics|/GRAPHICS]],POWER) displays for **/PNUM** can be problematic. **/PNUM** ,ELEM will display erratically depending on other display command specifications, while **/PNUM** ,LOC and **/PNUM**,ESYS are not supported.

Element and volume numbers are not visible for 3D elements and volumes when Z-buffering is turned on ( [[slashtype|/TYPE]],,\[6,7, or 8\]).

Use [[pstatus|/PSTATUS]] or **/PNUM**,STAT to show settings. Use **/PNUM**,DEFA to reset all specifications back to default. Use the [[number|/NUMBER]] command to control whether numbers and colors are displayed together.

This command is valid in any processor

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PNUM.html
