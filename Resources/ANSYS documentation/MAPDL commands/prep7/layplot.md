---
apdl: "LAYPLOT"
method: layplot
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.layplot
generated: 2026-08-22
tags: [mapdl-command]
---

# LAYPLOT

PyMAPDL: `mapdl.layplot(iel='', layr1='', layr2='', **kwargs)`

Displays the layer stacking sequence for layered elements.

## Parameters

**iel**: Element number for the display. If blank and the current element type is a layered element type, display data from the current real constant table.

**layr1**, **layr2**: Range of layer numbers to be displayed. If `LAYR1` is greater than `LAYR2`, a reversed order display is produced. Up to 20 layers may be displayed at a time. `LAYR1` defaults to 1. `LAYR2` defaults to `LAYR1` if `LAYR1` is input or to the number of layers (or to 19+ `LAYR1`, if smaller) if `LAYR1` is not input.

## Notes

Displays the layer-stacking sequence as defined in the real constant table for layered shell and solid elements in a form where the layers are visible (like a sheared deck of cards).

The element x-axis is shown as 0.0 degrees.

Layers are cross-hatched and color-coded for clarity. The hatch lines indicate the layer angle (real constant THETA) and the color coding is for material identification (real constant MAT).

The actual orientation of a specific layer in three- dimensional space can be seen using [[psymb|/PSYMB]],LAYR. To use [[psymb|/PSYMB]],LAYR with smeared reinforcing elements ( `REINF265` ), first set the vector-mode graphics option ( [[device|/DEVICE]],VECTOR,1).

Layer thickness can be displayed using the [[eshape|/ESHAPE]] and [[eplot|EPLOT]] commands.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LAYPLOT.html
