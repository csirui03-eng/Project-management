---
apdl: "TALLOW"
method: tallow
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.tallow
generated: 2026-08-22
tags: [mapdl-command]
---

# TALLOW

PyMAPDL: `mapdl.tallow(temp1='', temp2='', temp3='', temp4='', temp5='', temp6='', **kwargs)`

Defines the temperature table for safety factor calculations.

## Parameters

**temp1**, **temp2**, **temp3**, **temp4**, **temp5**, **temp6**: Input up to six temperatures covering the range of nodal temperatures. Temperatures must be input in ascending order.

## Notes

Defines the temperature table for safety factor calculations ( [[sfact|SFACT]], [[sallow|SALLOW]] ). Use [[stat|STAT]] command to list current temperature table. Repeat **TALLOW** command to zero table and redefine points (6 maximum).

Safety factor calculations are not supported by PowerGraphics. Both the [[sallow|SALLOW]] and **TALLOW** commands must be used with the Full Model Graphics display method active.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TALLOW.html
