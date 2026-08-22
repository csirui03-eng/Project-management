---
apdl: "/PBF"
method: pbf
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.pbf
generated: 2026-08-22
tags: [mapdl-command]
---

# /PBF

PyMAPDL: `mapdl.pbf(item='', key='', **kwargs)`

Shows magnitude of body-force loads on displays.

**Command default:**

No body-force load contours displayed.

## Parameters

**item**

Label identifying the item:

- `TEMP` - Applied temperatures.
- `FLUE` - Applied fluences.
- `HGEN` - Applied heat generation rates.
- `JS` - Applied current density magnitude.
- `JSX` - X-component of current density.
- `JSY` - Y-component of current density.
- `JSZ` - Z-component of current density.
- `PHASE` - Phase angle of applied load.
- `MVDI` - Applied magnetic virtual displacements flag.
- `CHRGD` - Applied electric charge density.

**key**

Symbol key:

- `0` - Do not show body-force load contours.
- `1` - Show body-force load contours.
- `2` - Show current density as a vector (not a contour).

## Notes

Shows body-force loads as contours on displays for the selected elements.

The effects of the **/PBF** command are not cumulative (that is, the command does not modify an existing setting from a previously issued **/PBF** command). If you issue multiple **/PBF** commands during an analysis, only the setting specified by the most recent **/PBF** command applies.

Use [[pstatus|/PSTATUS]] or **/PBF**,STAT to display settings. Use **/PBF**,DEFA to reset all specifications back to default. See also the [[psf|/PSF]] and [[pbc|/PBC]] command for other display contours.

Portions of this command are not supported by PowerGraphics ( [[graphics|/GRAPHICS]],POWER).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PBF.html
