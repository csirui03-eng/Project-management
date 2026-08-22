---
apdl: "PLF2D"
method: plf2d
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.magnetics_calculations.MagneticsCalculations.plf2d
generated: 2026-08-22
tags: [mapdl-command]
---

# PLF2D

PyMAPDL: `mapdl.plf2d(ncont='', olay='', anum='', win='', **kwargs)`

Generates a contour line plot of equipotentials.

## Parameters

**ncont**: Number of contour lines to display. Issue in multiples of 9 (that is, 9, 18, 27, etc.). Default is 27 contour lines.

**olay**

Overlay:

- `0` - Overlay edge outlines by material number.
- `1` - Overlay edge outlines by real constant number.

**anum**: Highest material or real constant attribute number. Command will cycle through `ANUM` element display overlays. Defaults to 10.

**win**: Window number to which command applies. Defaults to 1.

## Notes

**PLF2D** invokes a Mechanical APDL macro which plots equipotentials of the degree of freedom AZ. The equipotential lines are parallel to flux lines and thus give a good representation of flux patterns.

In the axisymmetric case, the display is actually r \* AZ where r is the node radius.

The macro overlays ( `OLAY` ) edge outlines by material number or real constant number ( `ANUM` ) and enables you to control the number of contour lines to display ( `NCONT` ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLF2D.html
