---
apdl: "LAYLIST"
method: laylist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.laylist
generated: 2026-08-22
tags: [mapdl-command]
---

# LAYLIST

PyMAPDL: `mapdl.laylist(iel='', layr1='', layr2='', mplab1='', mplab2='', **kwargs)`

Lists real constants material properties for layered elements.

## Parameters

**iel**: Element number to be listed. If ALL, list all selected elements ( [[esel|ESEL]] ) of the appropriate type. If blank and the current element type is a layered element type, list data from the current real constant table in the layered format.

**layr1**, **layr2**: Range of layer numbers to be listed. If `LAYR1` is greater than `LAYR2`, a reverse order list is produced. `LAYR1` defaults to 1. `LAYR2` defaults to `LAYR1` if `LAYR1` is input or to the number of layers if `LAYR1` is not input.

**mplab1**, **mplab2**: Material property labels (for example, EX) to be listed along with the layer real constants.

## Notes

Lists real constants and any two material properties for layered shell and solid elements.

If matrix input is selected (KEYOPT(2) = 2 or 3), `LAYR1`, `LAYR2`, `Mplab1`, and `Mplab2` are not used.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LAYLIST.html
